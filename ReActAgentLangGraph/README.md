# ReAct: Build Reasoning and Acting AI Agents with LangGraph

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

An AI agent that doesn't just respond — it **reasons**, then **acts**. Built on the **ReAct**
(Reasoning + Acting) framework with LangGraph, the agent thinks a problem through, calls tools when
it needs outside information, observes what comes back, and adapts until it can answer.

The graph cycles between an *agent* node that decides what to do next and a *tools* node that
executes, ending only when the model stops requesting tools. The worked example answers questions
that knowledge alone can't solve — *"what's the weather in Zurich, and what should I wear?"* — which
needs live data plus reasoning over it.

## How it works

```
        ┌─────────┐   needs a tool    ┌───────┐
  ──▶   │  agent  │ ────────────────▶ │ tools │
        └─────────┘ ◀──────────────── └───────┘
             │         observations
             ▼  no tool calls left
            END
```

`should_continue` inspects the last message: if it carries tool calls, the graph routes to the
tools node and loops back; otherwise it ends.

## Tools

| Tool | What it does |
|------|--------------|
| `search_tool` | Web search for current information (Tavily, or Serper as fallback) |
| `recommend_clothing` | Maps a weather description to practical clothing advice |
| `calculator_tool` | Evaluates math expressions safely via `ast` — no `eval()` |
| `news_summarizer_tool` | Condenses search results into headline / source / key point |

The calculator parses expressions into an AST and walks it, permitting only known-safe operators and
functions, so a prompt-injected `__import__('os')` is rejected rather than executed.

## Techniques

- The ReAct loop: reason → act → observe → repeat
- Cyclical agent/tools graphs in LangGraph with conditional edges
- Custom tools via the `@tool` decorator, where the docstring is the model-facing spec
- Accumulating conversation state with an `add_messages` reducer
- Streaming intermediate steps to watch the reasoning unfold
- Safe expression evaluation as an alternative to `eval()`

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other
projects.

```bash
cd ReActAgentLangGraph
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langgraph langchain langchain-groq langchain-community python-dotenv jupyter ipykernel
pip install langchain-tavily         # optional: only if you use Tavily for search
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name ReActAgentLangGraph --display-name "Python (ReActAgentLangGraph)"
jupyter notebook "ReActAgentLangGraph.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (ReActAgentLangGraph)**. Run `deactivate`
when you're finished.

### API keys

This project needs an LLM key and **one** search key — all have free tiers. Create a `.env` file in
this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
TAVILY_API_KEY=your_key_here     # preferred for search
SERPER_API_KEY=your_key_here     # used only if no Tavily key is set
```

Get them at [console.groq.com/keys](https://console.groq.com/keys),
[tavily.com](https://app.tavily.com/sign-in), and [serper.dev](https://serper.dev). `.env` is
git-ignored — never commit it.

## Notes on model choice

Tool calling is where hosted models differ most, and a ReAct agent has to emit a well-formed tool
call on every turn. The default is **`llama-3.1-8b-instant`**, which runs this notebook end to end
cleanly. Two alternatives, with caveats:

| Model | Notes |
|-------|-------|
| `llama-3.1-8b-instant` | Default. Fast, and reliable at tool calling here. |
| `openai/gpt-oss-120b` | Reasons better, but a much tighter rate limit on the free tier. |
| `llama-3.3-70b-versatile` | Avoid for this notebook — on multi-step queries it writes the tool call out as text, which the API rejects with `tool_use_failed`. |

If you swap models, re-run the weather example first: it's the query that chains two tool calls and
so surfaces tool-calling problems immediately.

**Keep tool arguments small.** `news_summarizer_tool` takes a short *topic* and does its own search,
rather than accepting article text. Passing large blobs through a tool-call argument makes models
emit malformed JSON and the request fails — a failure mode worth knowing when designing your own
tools.

## Customizing

- **Add a tool** — write a function, decorate it with `@tool`, add it to `tools`, then rebuild
  `model_react` and the graph so the binding picks it up.
- **Change the question** — edit the `inputs` dict passed to `graph.stream(...)`.
- **Swap the search provider** — replace the `_run_search` helper; everything downstream consumes
  the same `{title, link, snippet}` shape.

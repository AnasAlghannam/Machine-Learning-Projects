# Building a Reflexion Agent with External Knowledge Integration

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A research agent built on the **Reflexion** pattern. Instead of answering once, the agent drafts an
answer, critiques its own draft to find what's missing or superfluous, proposes its own search
queries, retrieves real evidence from the web, and revises the answer with citations — looping until
it reaches an iteration limit.

The point is grounding: the final answer cites sources the agent actually retrieved, rather than
relying only on what the model already knows. The worked example researches nutrition questions, but
the graph is task-agnostic — swap the prompts and the question and it researches anything.

## How it works

```
             ┌───────────┐
   ──▶       │  respond  │  draft + self-critique + search queries
             └───────────┘
                   │
                   ▼
            ┌──────────────┐
            │ execute_tools│  run each query through web search
            └──────────────┘
                   │
                   ▼
             ┌───────────┐
             │  revisor  │  rewrite using retrieved evidence + citations
             └───────────┘
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
  execute_tools            END  (iteration limit reached)
```

Structured output is enforced with Pydantic models bound as tools — `AnswerQuestion` (answer,
reflection, search queries) and `ReviseAnswer`, which adds a `references` list. That's what makes
the critique and the search queries machine-readable instead of buried in prose.

## Techniques

- The Reflexion framework: answer → self-critique → retrieve → revise
- Cyclical agent workflows with LangGraph's `MessageGraph` and conditional edges
- Structured agent output via Pydantic schemas bound as tools
- Integrating a live web-search tool so answers are grounded in retrieved sources
- Layered prompt construction (a shared template specialized for responder and revisor)
- Iteration control by counting tool visits

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other
projects.

```bash
cd ReflexionAgentExternalKnowledge
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langchain langchain-groq langchain-community langgraph pydantic python-dotenv jupyter ipykernel
pip install langchain-tavily      # optional: only if you use Tavily for search
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name ReflexionAgentExternalKnowledge --display-name "Python (ReflexionAgentExternalKnowledge)"
jupyter notebook "ReflexionAgentExternalKnowledge.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (ReflexionAgentExternalKnowledge)**. Run
`deactivate` when you're finished.

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

> **Search provider.** The notebook uses Tavily when `TAVILY_API_KEY` is present — it is built for
> agent retrieval and returns cleaner page content — and falls back to Serper (Google) otherwise.
> Both are normalized to the same `{title, link, snippet}` shape, so to plug in a different provider
> (Brave, DuckDuckGo) you only need to replace the `web_search` helper.

## Customizing

- **Change the question** — edit the string passed to `app.invoke(...)` at the end.
- **Change the number of loops** — `MAX_ITERATIONS` caps how many search/revise rounds run.
- **Change the domain** — rewrite the system prompt and `revise_instructions`; the graph is unchanged.
- **Change what's returned** — add fields to the `AnswerQuestion` / `ReviseAnswer` models.

## Disclaimer

This is a demonstration of an agent architecture, not a source of professional advice. The example
topic is nutrition, but the output is LLM-generated and may be wrong, incomplete, or misleading —
always verify claims against the cited sources.

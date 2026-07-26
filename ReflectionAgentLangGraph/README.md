# Building a Reflection Agent with LangGraph

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A **reflection agent** built with LangGraph — a self-improving workflow where the model drafts an
answer, critiques its own work, and rewrites it over several passes. A *generation* node produces
content, a *reflection* node reviews it, and a conditional edge loops between the two until an
iteration limit is reached.

The worked example turns a throwaway first draft of a LinkedIn post into a polished one, but the
pattern applies to anything that benefits from review — writing code, drafting emails, or
summarizing documents. Swap the prompts and the same graph works for a different task.

## How it works

```
        ┌──────────┐   critique    ┌─────────┐
  ──▶   │ generate │ ────────────▶ │ reflect │
        └──────────┘ ◀──────────── └─────────┘
              │        feedback
              ▼  (message limit reached)
             END
```

The reflector sees the draft with its roles flipped — the generated post is handed to the critic as
user input — so it reliably produces a critique instead of treating the conversation as finished.

## Techniques

- Graph-based agent workflows with LangGraph's `MessageGraph`
- Generate → critique → refine loop driven by conditional edges
- Message-state management for context retention across iterations
- Router logic (`should_continue`) that ends the run after a set number of passes
- Prompt design for a generator and an independent critic
- Visualizing the compiled graph

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other
projects.

```bash
cd ReflectionAgentLangGraph
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langgraph langchain langchain-groq python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name ReflectionAgentLangGraph --display-name "Python (ReflectionAgentLangGraph)"
jupyter notebook "ReflectionAgentLangGraph.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (ReflectionAgentLangGraph)**. Run
`deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered
automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get a free key at [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored —
never commit it.

## Customizing

- **Change the task** — edit the `inputs` message near the end of the notebook.
- **Change the number of passes** — `should_continue` ends the run once the message history grows
  past 6; each generate/reflect round adds two messages.
- **Change the domain** — rewrite `generation_prompt` and `reflection_prompt`; the graph is
  unchanged.

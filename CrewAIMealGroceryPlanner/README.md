# Structured Meal & Grocery Planner with CrewAI

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A four-agent planner that turns a few meal ideas into a structured weekly grocery run. A meal planner designs the meals, a shopping organizer groups ingredients by store section, a budget advisor estimates cost, and a leftover specialist suggests ways to use what's left. Output is typed with Pydantic models, so the plan comes back as structured data rather than prose.

## Techniques
- Four specialized agents in a sequential crew
- Pydantic models for structured, typed crew output
- Config-driven agents via `@CrewBase` and YAML (`config/agents.yaml`, `config/tasks.yaml`)
- Serper-backed web search for recipes and prices
- Composing crews incrementally, testing each stage

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

> **Note:** use a fresh virtual environment as shown below, not a base Anaconda environment. Installing crewAI into base Anaconda can break its `protobuf` and cause a `libprotobuf` load error.

```bash
cd CrewAIMealGroceryPlanner
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install crewai crewai-tools langchain langchain-community python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name CrewAIMealGroceryPlanner --display-name "Python (CrewAIMealGroceryPlanner)"
jupyter notebook "CrewAIMealGroceryPlanner.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (CrewAIMealGroceryPlanner)**. Run `deactivate` when you're finished.

### API keys

Create a `.env` file in this folder (or the repo root — it is discovered automatically):

```
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

Get them at [console.groq.com/keys](https://console.groq.com/keys), [serper.dev](https://serper.dev). `.env` is git-ignored — never commit it.

## Included files

`leftover.py` and `config/*.yaml` ship with the project — the notebook imports them directly, so there is nothing to download.

## Notes

The model is reached through Groq's OpenAI-compatible endpoint (`LLM(model="openai/...", base_url="https://api.groq.com/openai/v1")`). CrewAI's `groq/` prefix routes through litellm, which currently sends a field Groq rejects.

# CrewAI: Building Multi-Agent AI Systems

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A content-creation pipeline built with **CrewAI**. A research agent gathers current information using a live web-search tool, then a writer agent turns those findings into an article, with a social-media strategist added as a third specialist. Covers the core building blocks — agents, tasks, crews, and tools — and how to read back per-task outputs and token usage.

## Techniques
- Agents defined by role, goal, and backstory
- Tasks with expected outputs, assigned to agents
- Sequential crews passing work between agents
- Serper-backed web search as an agent tool
- Inspecting `CrewOutput`: raw text, per-task results, and token usage

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

> **Note:** use a fresh virtual environment as shown below, not a base Anaconda environment. Installing crewAI into base Anaconda can break its `protobuf` and cause a `libprotobuf` load error.

```bash
cd CrewAIMultiAgentBasics
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install crewai crewai-tools python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name CrewAIMultiAgentBasics --display-name "Python (CrewAIMultiAgentBasics)"
jupyter notebook "CrewAIMultiAgentBasics.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (CrewAIMultiAgentBasics)**. Run `deactivate` when you're finished.

### API keys

Create a `.env` file in this folder (or the repo root — it is discovered automatically):

```
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

Get them at [console.groq.com/keys](https://console.groq.com/keys), [serper.dev](https://serper.dev). `.env` is git-ignored — never commit it.

## Notes

The model is reached through Groq's OpenAI-compatible endpoint (`LLM(model="openai/...", base_url="https://api.groq.com/openai/v1")`). CrewAI's `groq/` prefix routes through litellm, which currently sends a field Groq rejects.

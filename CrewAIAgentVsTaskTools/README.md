# Agents with Tools vs. Tasks with Tools in CrewAI

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Two ways to attach tools in CrewAI, built side by side so the difference is visible. In the **agent-centric** approach the agent owns every tool and chooses per task; in the **task-centric** approach each task carries only the tool it needs. Both power the same restaurant FAQ chatbot, backed by PDF search and live web search.

## Techniques
- Agent-centric vs. task-centric tool attachment
- PDF search with locally-computed embeddings (no embedding API key)
- Serper-backed web search
- Building custom tools with the `@tool` decorator
- A calculator agent that routes to the right custom tool

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

> **Note:** use a fresh virtual environment as shown below, not a base Anaconda environment. Installing crewAI into base Anaconda can break its `protobuf` and cause a `libprotobuf` load error.

```bash
cd CrewAIAgentVsTaskTools
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install crewai crewai-tools langchain-community langchain-huggingface sentence-transformers python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name CrewAIAgentVsTaskTools --display-name "Python (CrewAIAgentVsTaskTools)"
jupyter notebook "CrewAIAgentVsTaskTools.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (CrewAIAgentVsTaskTools)**. Run `deactivate` when you're finished.

### API keys

Create a `.env` file in this folder (or the repo root — it is discovered automatically):

```
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

Get them at [console.groq.com/keys](https://console.groq.com/keys), [serper.dev](https://serper.dev). `.env` is git-ignored — never commit it.

## Included files

`The-Daily-Dish-FAQ.pdf` is the sample document the PDF search tool reads. It ships with the project.

## Notes

The model is reached through Groq's OpenAI-compatible endpoint (`LLM(model="openai/...", base_url="https://api.groq.com/openai/v1")`). CrewAI's `groq/` prefix routes through litellm, which currently sends a field Groq rejects.

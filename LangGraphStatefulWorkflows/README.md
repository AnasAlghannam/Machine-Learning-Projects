# LangGraph: Building Stateful AI Workflows

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A hands-on tour of **LangGraph** for building stateful, graph-based AI workflows. It builds three examples: an authentication workflow with validation and error handling, an LLM-backed question-answering workflow, and a cyclical counter that loops until a stop condition is met.

## Techniques
- States, nodes, edges, and conditional edges in LangGraph
- Linear and cyclical (looping) workflows
- Routing with conditional edges and a stop condition
- Integrating a Groq-hosted LLM as a graph node

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd LangGraphStatefulWorkflows
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langgraph langchain-groq python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name LangGraphStatefulWorkflows --display-name "Python (LangGraphStatefulWorkflows)"
jupyter notebook "LangGraphStatefulWorkflows.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (LangGraphStatefulWorkflows)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored — never commit it.

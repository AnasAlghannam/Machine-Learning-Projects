# DataWizard: AI-Powered Data Analysis

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

An LLM agent that lets non-technical users run data-science tasks through natural language. It exposes LangChain tools for listing datasets, loading and summarizing CSVs, and training/evaluating models, then wires them into a tool-calling agent and an `AgentExecutor` that runs multi-step analysis workflows.

## Techniques
- Custom LangChain tools for data-science tasks
- In-memory dataframe caching across queries
- Tool-calling agent + `AgentExecutor` (ReAct-style loop)
- Natural-language interface over pandas / scikit-learn

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd LLMDataScienceAgentLCEL
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langchain langchain-classic langchain-groq python-dotenv pandas numpy matplotlib seaborn scikit-learn jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name LLMDataScienceAgentLCEL --display-name "Python (LLMDataScienceAgentLCEL)"
jupyter notebook "LLMDataScienceAgentLCEL.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (LLMDataScienceAgentLCEL)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored — never commit it.

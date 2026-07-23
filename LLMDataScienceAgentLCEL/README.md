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
```bash
pip install langchain langchain-groq python-dotenv pandas numpy matplotlib seaborn scikit-learn
```

Create a `.env` file (in this folder or a parent) with your Groq API key:
```
GROQ_API_KEY=your_key_here
```
Get a free key at [console.groq.com](https://console.groq.com/keys). Then run:
```bash
jupyter notebook "LLMDataScienceAgentLCEL.ipynb"
```

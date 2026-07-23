# Multi-Agent Collaboration for Financial Analysis

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A crewAI multi-agent system for financial analysis. Data-analyst, trading-strategy, execution, and risk-management agents collaborate under a hierarchical manager to analyze a stock and propose a trading approach.

## Techniques
- Hierarchical multi-agent process with a manager LLM
- Specialized agents for analysis, strategy, execution, and risk
- Web search & scraping tools
- Structured multi-step financial workflow

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

> **Note:** use a fresh virtual environment as shown below (not a base Anaconda environment). Installing crewAI into base Anaconda can break its `protobuf` and cause a `libprotobuf` load error.

```bash
cd MultiAgentFinancialAnalysis
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install crewai crewai-tools langchain-community python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name MultiAgentFinancialAnalysis --display-name "Python (MultiAgentFinancialAnalysis)"
jupyter notebook "MultiAgentFinancialAnalysis.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (MultiAgentFinancialAnalysis)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq and Serper (web search). Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys), [serper.dev](https://serper.dev). `.env` is git-ignored — never commit it.

# Use Natural Language to Create Charts and Graphs

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A conversational data-visualization agent built on LangChain's `create_pandas_dataframe_agent`. Ask questions about a CSV in plain English and the Groq-hosted LLM answers them and generates the matching charts (bar, pie, box, scatter) — and can show the exact code it used.

## Techniques
- `create_pandas_dataframe_agent` over a CSV dataframe
- Natural-language querying and chart generation
- Inspecting the model's generated plotting code via intermediate steps
- matplotlib / seaborn visualizations

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd TextToChartVisualizationAgent
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langchain langchain-experimental langchain-groq python-dotenv matplotlib seaborn jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name TextToChartVisualizationAgent --display-name "Python (TextToChartVisualizationAgent)"
jupyter notebook "TextToChartVisualizationAgent.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (TextToChartVisualizationAgent)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored — never commit it.

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
```bash
pip install langchain langchain-experimental langchain-groq python-dotenv matplotlib seaborn
```

Create a `.env` file (in this folder or a parent) with your Groq API key:
```
GROQ_API_KEY=your_key_here
```
Get a free key at [console.groq.com](https://console.groq.com/keys). Then run:
```bash
jupyter notebook "TextToChartVisualizationAgent.ipynb"
```

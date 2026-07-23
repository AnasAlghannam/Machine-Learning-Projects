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
```bash
pip install crewai crewai-tools langchain-community python-dotenv
```

Create a `.env` file (in this folder or a parent) with your API keys:
```
GROQ_API_KEY=your_groq_key_here
SERPER_API_KEY=your_serper_key_here
```
Get a free Groq key at [console.groq.com](https://console.groq.com/keys) and a Serper (web search) key at [serper.dev](https://serper.dev). Then run:
```bash
jupyter notebook "MultiAgentFinancialAnalysis.ipynb"
```

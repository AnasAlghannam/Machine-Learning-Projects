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
```bash
pip install langgraph langchain-groq python-dotenv
```

Create a `.env` file (in this folder or a parent) with your Groq API key:
```
GROQ_API_KEY=your_key_here
```
Get a free key at [console.groq.com](https://console.groq.com/keys). Then run:
```bash
jupyter notebook "LangGraphStatefulWorkflows.ipynb"
```

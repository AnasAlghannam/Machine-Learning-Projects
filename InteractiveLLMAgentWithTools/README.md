# Build Interactive LLM Agents with Tools

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

An introduction to **tool calling** with LangChain: define custom tools, bind them to a Groq-hosted LLM, parse the model's tool calls, execute them, and feed the results back to produce a final answer — first step by step, then wrapped in a reusable agent class. Includes a tip-calculator agent as a worked extension.

## Techniques
- Custom LangChain tools with the `@tool` decorator
- Binding tools to an LLM with `bind_tools`
- Parsing and routing tool calls via a `tool_map`
- Building an agent class that manages the tool-calling loop

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd InteractiveLLMAgentWithTools
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install langchain langchain-groq python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name InteractiveLLMAgentWithTools --display-name "Python (InteractiveLLMAgentWithTools)"
jupyter notebook "InteractiveLLMAgentWithTools.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (InteractiveLLMAgentWithTools)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored — never commit it.

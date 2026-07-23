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
```bash
pip install langchain langchain-groq python-dotenv
```

Create a `.env` file (in this folder or a parent) with your Groq API key:
```
GROQ_API_KEY=your_key_here
```
Get a free key at [console.groq.com](https://console.groq.com/keys). Then run:
```bash
jupyter notebook "InteractiveLLMAgentWithTools.ipynb"
```

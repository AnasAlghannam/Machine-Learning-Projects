# Multi-Agent Customer Support Automation

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A crewAI multi-agent customer-support workflow. A support agent answers a customer inquiry and a quality-assurance agent reviews the response for accuracy and completeness.

## Techniques
- Multi-agent collaboration with crewAI
- Support + quality-assurance agent roles
- Documentation scraping tool for grounded answers
- Memory for context-aware responses

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

> **Note:** use a fresh virtual environment as shown below (not a base Anaconda environment). Installing crewAI into base Anaconda can break its `protobuf` and cause a `libprotobuf` load error.

```bash
cd MultiAgentCustomerSupport
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install crewai crewai-tools langchain-community python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name MultiAgentCustomerSupport --display-name "Python (MultiAgentCustomerSupport)"
jupyter notebook "MultiAgentCustomerSupport.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (MultiAgentCustomerSupport)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored — never commit it.

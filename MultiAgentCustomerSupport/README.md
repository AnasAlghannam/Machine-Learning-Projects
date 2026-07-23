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
```bash
pip install crewai crewai-tools langchain-community python-dotenv
```

Create a `.env` file (in this folder or a parent) with your API keys:
```
GROQ_API_KEY=your_groq_key_here
```
Get a free Groq key at [console.groq.com](https://console.groq.com/keys). Then run:
```bash
jupyter notebook "MultiAgentCustomerSupport.ipynb"
```

# Create Agents to Research and Write an Article

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A crewAI crew of three agents — a content planner, a writer, and an editor — that collaborate to research a topic and produce a polished article.

## Techniques
- Multi-agent collaboration with crewAI
- Sequential planner → writer → editor workflow
- Role, goal, and backstory agent design
- Task dependencies and context passing

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
jupyter notebook "ResearchAndWriteArticle.ipynb"
```

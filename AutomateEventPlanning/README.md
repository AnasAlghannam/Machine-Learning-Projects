# Automate Event Planning

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A crewAI multi-agent system that automates event planning. A venue coordinator, a logistics manager, and a marketing agent collaborate to find a venue, arrange catering and logistics, and produce marketing materials for an event.

## Techniques
- Multi-agent collaboration with crewAI
- Tasks with structured (Pydantic) outputs
- Asynchronous task execution
- Web search & scraping tools (SerperDevTool, ScrapeWebsiteTool)

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
jupyter notebook "AutomateEventPlanning.ipynb"
```

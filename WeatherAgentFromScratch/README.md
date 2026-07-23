# Building AI Agents from Scratch with Python

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

AI agents built from scratch in pure Python: a Weather AI Agent that fetches real-time weather data, and The Daily Dish, a customer-service chatbot answering questions from a PDF knowledge base — with shared memory and intelligent query routing.

## Techniques
- Agent classes built from scratch (no framework)
- Tool use via the OpenWeather API
- PDF knowledge base with TF-IDF retrieval (scikit-learn)
- Shared memory and query routing between agents

## Setup
```bash
pip install nltk PyPDF2 scikit-learn requests numpy python-dotenv
```

Create a `.env` file (in this folder or a parent) with your OpenWeather API key:
```
OPENWEATHER_API_KEY=your_key_here
```
Get a free key at [openweathermap.org](https://home.openweathermap.org/api_keys). Then run:
```bash
jupyter notebook "WeatherAgentFromScratch.ipynb"
```

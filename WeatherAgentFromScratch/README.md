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

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd WeatherAgentFromScratch
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install nltk PyPDF2 scikit-learn requests numpy python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name WeatherAgentFromScratch --display-name "Python (WeatherAgentFromScratch)"
jupyter notebook "WeatherAgentFromScratch.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (WeatherAgentFromScratch)**. Run `deactivate` when you're finished.

### API keys

This project calls OpenWeather. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
OPENWEATHER_API_KEY=your_key_here
```

Get keys at: [openweathermap.org/api_keys](https://home.openweathermap.org/api_keys). `.env` is git-ignored — never commit it.

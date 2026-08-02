# Structuring Restaurant Data with an LLM

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Turns unstructured restaurant write-ups into validated JSON records. An LLM extracts the fields, a Pydantic schema validates the result, and a second LLM pass repairs anything that fails validation — so the output is machine-readable rather than merely plausible.

## What it covers
- Prompt design with a worked example to anchor the output format
- Pydantic schemas as the contract for extracted records
- An automatic repair loop that feeds validation errors back to the model
- An iteration cap so an unfixable record cannot loop forever
- Batch processing over a full text corpus

## Setup

```bash
cd RestaurantDataStructuring
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install openai pydantic python-dotenv jupyter ipykernel
```

### API key

```bash
cp .env.example .env
```

Set `GROQ_API_KEY` — free at [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored.

## Run it

```bash
python -m ipykernel install --user --name RestaurantDataStructuring --display-name "Python (RestaurantDataStructuring)"
jupyter notebook "RestaurantDataStructuring.ipynb"
```

Select **Kernel → Change kernel → Python (RestaurantDataStructuring)**.

## Configuration

| Variable | Default | Meaning |
|---|---|---|
| `GROQ_API_KEY` | — | Required. |
| `MODEL_ID` | `llama-3.3-70b-versatile` | Text model. |
| `BASE_URL` | `https://api.groq.com/openai/v1` | Any OpenAI-compatible endpoint. |

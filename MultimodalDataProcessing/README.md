# Processing Multimodal Data with LLMs

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Adds image understanding to a text dataset. A vision model captions food photographs and review images, and those captions are folded back into the existing JSON records — producing one dataset carrying both textual and visual information.

## What it covers
- Sending images to a model as base64 data URIs
- Prompt design that keeps captions descriptive rather than speculative
- Captioning with surrounding text as context
- Fetching remote images with retry and backoff
- Augmenting structured records with generated fields

## Setup

```bash
cd MultimodalDataProcessing
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install openai pillow matplotlib requests tenacity python-dotenv jupyter ipykernel
```

### API key

```bash
cp .env.example .env
```

Set `GROQ_API_KEY` — free at [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored.

Image captioning additionally needs a **vision-capable** model. Set `VISION_MODEL` in `.env` to one your account offers; not every provider exposes one. The text-only steps run without it.

## Run it

```bash
python -m ipykernel install --user --name MultimodalDataProcessing --display-name "Python (MultimodalDataProcessing)"
jupyter notebook "MultimodalDataProcessing.ipynb"
```

Select **Kernel → Change kernel → Python (MultimodalDataProcessing)**.

## Configuration

| Variable | Default | Meaning |
|---|---|---|
| `GROQ_API_KEY` | — | Required. |
| `MODEL_ID` | `llama-3.3-70b-versatile` | Text model. |
| `BASE_URL` | `https://api.groq.com/openai/v1` | Any OpenAI-compatible endpoint. |
| `VISION_MODEL` | *(blank)* | Multimodal model for image captioning. |

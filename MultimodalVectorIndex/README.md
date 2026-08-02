# Building a Multimodal Vector Index

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Builds a searchable index over two modalities at once. Restaurant articles are embedded with a sentence-transformer and food images with CLIP, then stored in separate Chroma collections so each can be queried in its own vector space.

## What it covers
- Text embeddings with sentence-transformers (384-d)
- Image embeddings with CLIP (512-d)
- Normalized vectors for cosine similarity
- Separate Chroma collections per modality
- Metadata attached at index time to enable later filtering

## Setup

```bash
cd MultimodalVectorIndex
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install chromadb sentence-transformers transformers torch pillow jupyter ipykernel
```

No API key needed — embeddings run locally on your machine.

## Run it

```bash
python -m ipykernel install --user --name MultimodalVectorIndex --display-name "Python (MultimodalVectorIndex)"
jupyter notebook "MultimodalVectorIndex.ipynb"
```

Select **Kernel → Change kernel → Python (MultimodalVectorIndex)**.

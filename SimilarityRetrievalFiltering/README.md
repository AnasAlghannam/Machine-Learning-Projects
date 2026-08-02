# Similarity Retrieval with Metadata Filtering

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Querying the multimodal index three ways: text→text over articles, the same with a metadata constraint applied, and image→image visual similarity. Shows how metadata filters narrow a vector search without changing the embedding.

## What it covers
- Text-to-text similarity search
- Metadata `where` filters layered on vector search
- Image-to-image retrieval using a stored image as the query
- Reading Chroma's nested result structure
- Handling empty result sets from over-narrow filters

## Setup

```bash
cd SimilarityRetrievalFiltering
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install chromadb sentence-transformers transformers torch pillow jupyter ipykernel
```

> Run **MultimodalVectorIndex** first — this project queries the Chroma index it builds at `~/chroma_multimodal`.

No API key needed — embeddings run locally on your machine.

## Run it

```bash
python -m ipykernel install --user --name SimilarityRetrievalFiltering --display-name "Python (SimilarityRetrievalFiltering)"
jupyter notebook "SimilarityRetrievalFiltering.ipynb"
```

Select **Kernel → Change kernel → Python (SimilarityRetrievalFiltering)**.

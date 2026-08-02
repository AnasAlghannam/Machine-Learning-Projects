# Multimodal Similarity Fusion and Ranking

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Combines text and image retrieval into a single ranked list. Scores from each modality are normalized independently, then blended with tunable weights — so you can shift the ranking toward articles or toward images and watch the ordering change.

## What it covers
- Min-max normalization within each modality before blending
- Weighted score fusion across text and image results
- Building one candidate pool from two vector spaces
- Weight tuning and its effect on the final ranking
- Retrieving more candidates than you display

## Setup

```bash
cd MultimodalFusionRanking
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install chromadb sentence-transformers transformers torch pillow jupyter ipykernel
```

> Run **MultimodalVectorIndex** first — this project queries the Chroma index it builds at `~/chroma_multimodal`.

No API key needed — embeddings run locally on your machine.

## Run it

```bash
python -m ipykernel install --user --name MultimodalFusionRanking --display-name "Python (MultimodalFusionRanking)"
jupyter notebook "MultimodalFusionRanking.ipynb"
```

Select **Kernel → Change kernel → Python (MultimodalFusionRanking)**.

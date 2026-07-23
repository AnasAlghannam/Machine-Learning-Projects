# Waste Product Classification via Transfer Learning

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Classifies waste product images into categories using VGG16 fine-tuned on a custom dataset.

## Techniques
- Transfer learning with VGG16 (fine-tuning)
- Image data preprocessing & augmentation
- Model evaluation with accuracy metrics & prediction visualization

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd WasteProductClassificationTransferLearning
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install tensorflow keras pillow matplotlib jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name WasteProductClassificationTransferLearning --display-name "Python (WasteProductClassificationTransferLearning)"
jupyter notebook "WasteProductClassificationTransferLearning.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (WasteProductClassificationTransferLearning)**. Run `deactivate` when you're finished.

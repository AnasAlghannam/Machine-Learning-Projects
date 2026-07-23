# Data Loading and Augmentation — PyTorch

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Implements PyTorch data pipelines using custom `Dataset` classes, `ImageFolder`, and `DataLoader`.

## Techniques
- Custom `torch.utils.data.Dataset`
- Built-in `ImageFolder` utility
- `DataLoader` for batching & shuffling
- Augmentation & performance comparison

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd DataLoadingAugmentationPyTorch
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install torch torchvision matplotlib pillow jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name DataLoadingAugmentationPyTorch --display-name "Python (DataLoadingAugmentationPyTorch)"
jupyter notebook "DataLoadingAugmentationPyTorch.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (DataLoadingAugmentationPyTorch)**. Run `deactivate` when you're finished.

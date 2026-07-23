# Anime Image Classification with CNN

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Builds and trains a Convolutional Neural Network to classify anime images into categories.

## Techniques
- Custom CNN architecture in PyTorch
- Image preprocessing & augmentation
- Training/validation split & evaluation

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd AnimeImageClassificationCNN
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install torch torchvision matplotlib pillow jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name AnimeImageClassificationCNN --display-name "Python (AnimeImageClassificationCNN)"
jupyter notebook "AnimeImageClassificationCNN.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (AnimeImageClassificationCNN)**. Run `deactivate` when you're finished.

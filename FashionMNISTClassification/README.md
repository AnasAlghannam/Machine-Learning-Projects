# Fashion-MNIST Classification

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Classifies Fashion-MNIST clothing items using a CNN built in PyTorch.

## Techniques
- Custom Dataset class with transforms
- CNN with Softmax output
- Cross-entropy loss & Adam optimizer

## Dataset
Fashion-MNIST (via torchvision)

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd FashionMNISTClassification
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install torch torchvision matplotlib jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name FashionMNISTClassification --display-name "Python (FashionMNISTClassification)"
jupyter notebook "FashionMNISTClassification.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (FashionMNISTClassification)**. Run `deactivate` when you're finished.

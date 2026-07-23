# Data Loading and Augmentation — Keras

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Builds efficient image data pipelines using Keras, comparing custom generators against the built-in `image_dataset_from_directory` utility.

## Techniques
- Custom Python generator for on-the-fly data loading
- `tf.keras.utils.image_dataset_from_directory`
- `.map()`, `.cache()`, `.prefetch()` optimizations
- Performance comparison & analysis

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd DataLoadingAugmentationKeras
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install tensorflow matplotlib numpy jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name DataLoadingAugmentationKeras --display-name "Python (DataLoadingAugmentationKeras)"
jupyter notebook "DataLoadingAugmentationKeras.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (DataLoadingAugmentationKeras)**. Run `deactivate` when you're finished.

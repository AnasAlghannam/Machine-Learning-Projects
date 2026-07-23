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
```bash
pip install tensorflow matplotlib numpy
```
Run the notebook: `jupyter notebook "DataLoadingAugmentationKeras.ipynb"`

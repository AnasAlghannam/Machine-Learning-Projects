# Aircraft Damage Classification and Captioning

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Classifies aircraft damage (dent vs crack) from images using transfer learning, and generates captions using a pretrained transformer model.

## Techniques
- Transfer learning with pretrained VGG16 (feature extraction)
- Binary image classification
- BLIP transformer model for image captioning & summarization
- Training/validation curve visualization

## Dataset
[Aircraft Damage Dataset](https://universe.roboflow.com/youssef-donia-fhktl/aircraft-damage-detection-1j9qk) — Roboflow (CC BY 4.0)

## Setup
```bash
pip install tensorflow keras transformers pillow matplotlib
```
Run the notebook: `jupyter notebook "AircraftDamageClassificationCaptioning.ipynb"`

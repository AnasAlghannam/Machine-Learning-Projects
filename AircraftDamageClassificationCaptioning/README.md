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

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd AircraftDamageClassificationCaptioning
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install tensorflow keras transformers pillow matplotlib jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name AircraftDamageClassificationCaptioning --display-name "Python (AircraftDamageClassificationCaptioning)"
jupyter notebook "AircraftDamageClassificationCaptioning.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (AircraftDamageClassificationCaptioning)**. Run `deactivate` when you're finished.

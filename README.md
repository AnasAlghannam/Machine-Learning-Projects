# Machine Learning Projects

**Author:** Anas AlGhannam

A collection of machine learning and deep learning projects covering classification, computer vision, and NLP.

---

## Projects

### 1. Australian Weather Rain Prediction
**Notebook:** `AUSWeather.ipynb`

Predicts whether it will rain tomorrow in Australia using the Australian Bureau of Meteorology dataset (2008–2017).

**Techniques:**
- Data preprocessing & feature engineering
- Logistic Regression
- Random Forest Classifier
- GridSearchCV hyperparameter tuning
- Confusion matrix & classification report evaluation

**Dataset:** [Kaggle - Australian Weather Dataset](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)

---

### 2. Aircraft Damage Classification and Captioning
**Notebook:** `Classification Captioning.ipynb`

Classifies aircraft damage (dent vs crack) from images using transfer learning, and generates captions using a pretrained transformer model.

**Techniques:**
- Transfer learning with pretrained VGG16 (feature extraction)
- Binary image classification
- BLIP transformer model for image captioning & summarization
- Training/validation curve visualization

**Dataset:** [Aircraft Damage Dataset](https://universe.roboflow.com/youssef-donia-fhktl/aircraft-damage-detection-1j9qk) — Roboflow (CC BY 4.0)

---

## Setup

```bash
pip install numpy pandas matplotlib scikit-learn seaborn
pip install torch torchvision transformers pillow
```

Run notebooks via Jupyter:
```bash
jupyter notebook
```

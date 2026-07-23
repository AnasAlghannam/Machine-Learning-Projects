# Australian Weather Rain Prediction

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Predicts whether it will rain tomorrow in Australia using the Australian Bureau of Meteorology dataset (2008–2017).

## Techniques
- Data preprocessing & feature engineering
- Logistic Regression, Random Forest Classifier
- GridSearchCV hyperparameter tuning
- Confusion matrix & classification report evaluation

## Dataset
[Kaggle – Australian Weather Dataset](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd AUSWeather
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install pandas numpy scikit-learn matplotlib seaborn jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name AUSWeather --display-name "Python (AUSWeather)"
jupyter notebook "AUSWeather.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (AUSWeather)**. Run `deactivate` when you're finished.

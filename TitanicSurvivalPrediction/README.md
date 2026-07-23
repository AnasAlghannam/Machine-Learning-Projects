# Titanic Survival Prediction

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Predicts passenger survival on the Titanic using ensemble classifiers and pipeline optimization.

## Techniques
- Random Forest & additional classifiers
- sklearn Pipeline for preprocessing + modeling
- Cross-validation & GridSearchCV hyperparameter tuning
- Comparative model evaluation

## Dataset
Titanic Survival Dataset

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd TitanicSurvivalPrediction
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install pandas numpy scikit-learn matplotlib seaborn jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name TitanicSurvivalPrediction --display-name "Python (TitanicSurvivalPrediction)"
jupyter notebook "TitanicSurvivalPrediction.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (TitanicSurvivalPrediction)**. Run `deactivate` when you're finished.

# League of Legends Match Predictor

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Predicts match outcomes in League of Legends using match statistics and a neural network.

## Techniques
- Logistic Regression & neural network classifier
- Feature scaling with StandardScaler
- PyTorch training loop
- Accuracy & loss evaluation

## Dataset
`league_of_legends_data_large.csv`

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd LeagueOfLegendsMatchPredictor
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install torch pandas numpy scikit-learn matplotlib jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name LeagueOfLegendsMatchPredictor --display-name "Python (LeagueOfLegendsMatchPredictor)"
jupyter notebook "LeagueOfLegendsMatchPredictor.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (LeagueOfLegendsMatchPredictor)**. Run `deactivate` when you're finished.

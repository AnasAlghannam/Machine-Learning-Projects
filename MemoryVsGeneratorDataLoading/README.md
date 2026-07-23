# Memory-Based vs Generator-Based Data Loading

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Explores geospatial satellite image classification by comparing memory-based and generator-based data loading strategies.

## Techniques
- Memory-based vs generator-based loading benchmarks
- Keras image pipelines
- Agricultural vs non-agricultural land classification
- Trade-off analysis (speed vs memory efficiency)

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd MemoryVsGeneratorDataLoading
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install tensorflow numpy matplotlib jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name MemoryVsGeneratorDataLoading --display-name "Python (MemoryVsGeneratorDataLoading)"
jupyter notebook "MemoryVsGeneratorDataLoading.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (MemoryVsGeneratorDataLoading)**. Run `deactivate` when you're finished.

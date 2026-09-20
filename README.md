# MLOPS Experiment 3

An MLOps experiment for versioning a heart disease dataset and Random Forest models with Git and DVC.

## Project structure

- `data/heart.csv.dvc`: DVC pointer for the heart disease dataset
- `models/`: DVC pointers for versioned Random Forest models
- `src/train.py`: trains and evaluates the classifier
- `notebooks/`: experiment notebooks

## Setup

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Train the model

Run from the repository root:

```powershell
python src/train.py
```

The script expects `data/heart.csv` to be available and writes the trained model to `models/random_forest_v1.pkl`.

## DVC

The dataset and model binaries are intentionally kept outside Git and represented by DVC pointer files. Configure a DVC remote appropriate for your environment, then restore tracked artifacts with:

```powershell
dvc pull
```
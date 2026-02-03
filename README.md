# Random Forest Model Project

## Overview
This project applies a Random Forest classifier to gene expression data from GEO (Gene Expression Omnibus) datasets.  
The primary goal is **feature selection**—identifying high-importance genes that contribute most to classification performance.  
The trained model is saved as a `.pkl` file for reproducibility and downstream analysis.

## Project Structure
- `random_forest_model.pkl` – Serialized Random Forest model
- `data/` – Input dataset (not included here; replace with your own)
- `google colab` – for data preprocessing, training, and evaluation
- `scripts/` – Python scripts for automation and reproducibility
- `README.md` – Project documentation

## Requirements
- Python 3.8+
- Libraries:
  - scikit-learn
  - pandas
  - numpy
  - joblib (for saving/loading models)

Workflow
- Data Retrieval
- Download GEO dataset (e.g., GSEXXXX).
- Normalize and preprocess expression values.
- Model Training
- Train Random Forest classifier on labeled samples.
- use normalized counts, phenodata and the DEGs from particular contrast
- Feature Selection
- Extract feature importance scores from the trained model.
- Rank genes by importance.
- Save top-ranked genes for downstream biological interpretation.
- Model Saving
- Serialize trained model with joblib.dump().
- Store feature importance table as CSV.

Install dependencies:
 ```bash
pip install -r requirements.txt
import joblib

# Load the trained model
model = joblib.load("random_forest_model.pkl")


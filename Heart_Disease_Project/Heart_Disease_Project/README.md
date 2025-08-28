# Heart Disease ML Pipeline (UCI)

A full end‑to‑end machine learning project following the SprintUP graduation guide.
This repository covers preprocessing, PCA, feature selection, supervised & unsupervised
models, hyperparameter tuning, model export, and a Streamlit app.

## Dataset
Download the Heart Disease dataset from UCI and place the CSV here:
`data/heart_disease.csv`

UCI page: https://archive.ics.uci.edu/ml/datasets/heart+disease

> Tip: Many public mirrors also host a combined CSV (e.g., `heart.csv`). As long as
> your columns are consistent with the notebook expectations, it will work.

## Environment
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Notebooks (order)
1. `01_data_preprocessing.ipynb` — EDA, cleaning, encoding, scaling, train/test split.  
2. `02_pca_analysis.ipynb` — PCA fit, variance plots, transformed features.  
3. `03_feature_selection.ipynb` — Chi², RFE, model-based importances.  
4. `04_supervised_learning.ipynb` — Train LR / DT / RF / SVM; metrics + ROC/AUC.  
5. `05_unsupervised_learning.ipynb` — KMeans + Hierarchical clustering.  
6. `06_hyperparameter_tuning.ipynb` — Grid/Random search; export best pipeline.

## Streamlit App
After running notebook 06 (which saves `models/final_pipeline.pkl`), start the app:
```bash
streamlit run ui/app.py
```

## Ngrok (optional)
See `deployment/ngrok_setup.txt` for how to expose the app publicly.

## Results
Key metrics will be saved under `results/` as you run notebooks.

## File Tree
```
Heart_Disease_Project/
  data/
    heart_disease.csv             # (you add this)
  notebooks/
    01_data_preprocessing.ipynb
    02_pca_analysis.ipynb
    03_feature_selection.ipynb
    04_supervised_learning.ipynb
    05_unsupervised_learning.ipynb
    06_hyperparameter_tuning.ipynb
  models/
    final_pipeline.pkl            # (created by notebook 06)
  ui/
    app.py                        # Streamlit UI
  deployment/
    ngrok_setup.txt
  results/
    evaluation_metrics.txt        # filled by notebooks
  README.md
  requirements.txt
  .gitignore
```

---

**Maintainer Notes**
- Set `RANDOM_STATE = 42` for reproducibility.  
- All plotting uses matplotlib by default.  
- Notebooks are designed to be run in order.

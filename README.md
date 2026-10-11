# Wholesale Customer Segmentation

This project explores and segments wholesale customers using their annual spending across six product categories. The notebook performs exploratory analysis, prepares the spending features, compares clustering methods, visualizes the resulting groups, and demonstrates a prediction for a new customer.

The source dataset contains 440 customers and 8 columns. `Channel` and `Region` describe each customer; the six spending fields are used for clustering.

## Analysis

`code/code.ipynb` includes:

- Dataset inspection, summary statistics, missing-value and duplicate checks
- Spending distributions, boxplots, and feature correlations
- `log1p` transformation and standardization of spending features
- K-Means model selection with inertia and silhouette scores
- Three-cluster K-Means segmentation and agglomerative clustering comparison
- Cluster profiles, channel and region comparisons, and PCA visualizations
- A sample prediction for a new customer's spending profile

## Project Structure

```text
.
|-- code/
|   `-- code.ipynb
|-- dataset/
|   |-- Wholesale customers data.csv
|   `-- wholesale_customer_segments.csv
|-- models/
|   |-- wholesale_kmeans_model.pkl
|   |-- wholesale_pca.pkl
|   `-- wholesale_scaler.pkl
`-- requirement.txt
```

## Setup and Run

Install Python 3.10 or later, then run these commands from the project root in PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirement.txt
.\.venv\Scripts\python.exe -m jupyter lab code/code.ipynb
```

The notebook expects to be run with the project root as its working directory so it can read `dataset/Wholesale customers data.csv`.

## Dependencies

Dependencies are listed in `requirement.txt`: pandas, NumPy, Matplotlib, Seaborn, scikit-learn, joblib, and Jupyter.

## Generated Files

The notebook exports `wholesale_customer_segments.csv` and saves the fitted scaler, K-Means model, and PCA model as pickle files. These save paths are relative to the notebook's current working directory. The workspace currently includes the CSV under `dataset/` and the model files under `models/`.

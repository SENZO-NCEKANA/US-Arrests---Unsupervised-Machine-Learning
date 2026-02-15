# Unsupervised Machine Learning: PCA & Clustering Analysis

A capstone project applying **Principal Component Analysis (PCA)** and **clustering** to the US Arrests dataset. The analysis explores crime statistics across 50 US states using dimensionality reduction and two clustering methods (K-means and Hierarchical).

---

## Table of Contents

- [Overview](#overview)
- [Project Architecture](#project-architecture)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Features](#features)
- [Key Findings](#key-findings)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Technologies](#technologies)
- [Results & Visualizations](#results--visualizations)
- [Methodology](#methodology)
- [Author](#author)

---

## Overview

This project demonstrates an end-to-end unsupervised learning workflow: loading and preprocessing data, correlation analysis, PCA for dimensionality reduction, component selection and justification, biplot interpretation, and clustering with K-means and Hierarchical methods. Results are compared and interpreted to uncover patterns in crime and urbanization across US states.

### Project Architecture

High-level flow from input data through the analysis pipeline to outputs:

![Project Architecture](images/project_architecture.png)

---

## Objectives

- Perform **dimensionality reduction** using PCA and justify the number of components
- Conduct **correlation analysis** and interpret variable relationships
- Build **biplots** to visualize observations and variable loadings in PCA space
- Apply **K-means** and **Hierarchical** clustering and analyze the resulting clusters
- Compare clustering methods and comment on **similarities within clusters**

---

## Dataset

**US Arrests** (`UsArrests.csv`) — 50 US states, 4 variables:

| Variable   | Description                                  |
|-----------|----------------------------------------------|
| Murder    | Murder rate per 100,000 residents            |
| Assault   | Assault rate per 100,000 residents           |
| UrbanPop  | Percentage of population in urban areas      |
| Rape      | Rape rate per 100,000 residents              |

---

## Features

| Section              | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **Preprocessing**    | Load, explore, and standardize data (StandardScaler); missing-value checks  |
| **Correlation**      | Correlation matrix and heatmap; interpretation of variable relationships   |
| **PCA**              | Full PCA, scree plots, variance explained, component selection justification|
| **Biplot**           | Biplot of first two PCs with state labels and variable loadings            |
| **K-means**          | Elbow method, silhouette scores, k=3 clustering, cluster analysis         |
| **Hierarchical**    | Ward linkage, dendrogram, k=3 clusters, cluster analysis                   |
| **Comparison**       | Agreement between methods; states with different assignments               |

---

## Key Findings

- **PCA:** The first two principal components explain **~86.75%** of the variance (PC1 ≈ 62%, PC2 ≈ 25%).
- **Interpretation:** PC1 reflects overall crime level (Murder, Assault, Rape); PC2 reflects urbanization (UrbanPop).
- **Clustering:** Both methods yield **three clusters**: high-crime urban, low-crime rural, and moderate-crime states.
- **Method agreement:** ~32% of states receive the same cluster label from both K-means and Hierarchical clustering.

---

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/unsupervised-ml-pca-clustering.git
   cd unsupervised-ml-pca-clustering
   ```

2. **Create and activate a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

1. Place `UsArrests.csv` in the project root (or adjust the path in the notebook).
2. Start Jupyter and open the notebook:
   ```bash
   jupyter notebook unsupervised_task.ipynb
   ```
   Or with JupyterLab:
   ```bash
   jupyter lab unsupervised_task.ipynb
   ```
3. Run all cells in order to reproduce the analysis and generate figures.

---

## Project Structure

```
.
├── unsupervised_task.ipynb   # Main analysis notebook
├── UsArrests.csv             # US Arrests dataset
├── requirements.txt          # Python dependencies
├── README.md                 # This file
└── images/                   # Generated figures (created when you run the notebook)
    ├── project_architecture.png  # Architecture diagram (this README)
    ├── correlation_matrix.png
    ├── pca_scree_plots.png
    ├── pca_biplot.png
    ├── kmeans_evaluation.png
    ├── kmeans_clustering.png
    ├── hierarchical_clustering.png
    └── clustering_comparison.png
```

---

## Technologies

- **Python 3.x**
- **pandas** — Data loading and manipulation
- **NumPy** — Numerical operations
- **Matplotlib** & **Seaborn** — Plotting and heatmaps
- **scikit-learn** — StandardScaler, PCA, KMeans, silhouette_score
- **SciPy** — Hierarchical clustering (linkage, dendrogram, fcluster)
- **Jupyter** — Notebook execution

---

## Results & Visualizations

The notebook produces:

1. **Correlation matrix** — Heatmap of variable correlations  
2. **PCA scree plots** — Individual and cumulative explained variance  
3. **Biplot** — States and variables in the space of PC1 and PC2  
4. **K-means** — Elbow/silhouette plots and cluster scatter plot  
5. **Hierarchical** — Dendrogram and cluster scatter plot  
6. **Comparison** — Side-by-side K-means vs Hierarchical cluster assignments  

All plots are saved as PNG files in the `images/` folder.

---

## Methodology

1. **Standardization** — All features scaled to mean 0, standard deviation 1.  
2. **Component choice** — Two components selected using an ~80% variance rule and scree plot.  
3. **Clustering** — K-means (k=3) and Hierarchical (Ward, k=3); cluster quality assessed with silhouette scores.  
4. **Interpretation** — Cluster profiles and within-cluster similarities described in the notebook.

---

## Author

**Senzo Ncekana**

*Project — Unsupervised Machine Learning*

This project is for portfolio purposes.

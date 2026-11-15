# Cryptocurrency Clustering Using K-Means and Principal Component Analysis

## Project Overview

This project explores unsupervised machine learning techniques to identify patterns among cryptocurrencies based on historical price change percentages.

The analysis compares K-Means clustering using the original standardized features with clustering performed after dimensionality reduction using Principal Component Analysis (PCA).

The objective is to evaluate how reducing the number of features affects the representation and interpretation of cryptocurrency clusters.

## Business Problem

Cryptocurrency markets contain numerous assets with varying price movements and volatility characteristics. Identifying groups of cryptocurrencies with similar historical price behavior can support exploratory market analysis and provide a foundation for additional research.

This project investigates whether K-Means clustering can identify meaningful groupings and whether PCA can simplify the feature space while preserving important information.

The resulting clusters are exploratory and should not be interpreted as investment recommendations or predictions of future performance.

## Dataset

The project uses `crypto_market_data.csv`, located in the `Resources` folder.

The dataset includes seven numerical features representing cryptocurrency price change percentages across different periods:

- 24 hours
- 7 days
- 14 days
- 30 days
- 60 days
- 200 days
- 1 year

Cryptocurrency identifiers are retained for associating observations with their respective assets.

## Technologies and Libraries

- Python
- Jupyter Notebook
- Pandas
- Scikit-learn
- K-Means clustering
- Principal Component Analysis
- StandardScaler
- hvPlot

## Methodology

### 1. Data Preparation

The cryptocurrency dataset is imported into a Pandas DataFrame.

Seven price change features are standardized using `StandardScaler` to reduce the influence of differences in feature scale on the clustering algorithm.

### 2. K-Means Clustering Using Original Features

The elbow method evaluates candidate cluster counts using model inertia.

Based on the elbow analysis, four clusters are selected.

A K-Means model is fitted using the seven standardized features, and the resulting cluster assignments are visualized.

### 3. Principal Component Analysis

PCA reduces the original seven features to three principal components.

The explained variance ratios are:

| Principal Component | Explained Variance |
|---|---:|
| PC1 | 37.20% |
| PC2 | 34.70% |
| PC3 | 17.60% |
| **Total** | **89.50%** |

The three components preserve approximately 89.50% of the variance in the standardized dataset.

### 4. K-Means Clustering Using PCA Features

A second K-Means model uses four clusters and is fitted to the three principal components.

Cluster assignments are generated and visualized to compare the reduced feature representation with the original standardized dataset.

### 5. Comparison of Clustering Results

The analysis compares the clustering results before and after PCA.

Reducing the feature space produces a different visual distribution of cryptocurrency clusters. PCA provides a more compact representation while retaining most of the original variance.

However, visually compact clusters do not necessarily demonstrate superior clustering quality.

Additional quantitative validation, such as silhouette scores, would be required to determine whether PCA improves cluster separation.

## Key Findings

1. The elbow method supports selecting four clusters for the original standardized dataset.
2. PCA reduces seven original features to three principal components.
3. The three principal components explain approximately 89.50% of the total variance.
4. K-Means clustering can be applied to both the original standardized features and the PCA representation.
5. PCA changes how clusters are represented visually, but the analysis does not establish that PCA improves clustering performance.

## Limitations

The analysis is exploratory and has several limitations:

- K-Means requires the number of clusters to be specified.
- Cluster assignments depend on the selected features and scaling approach.
- The elbow method provides a heuristic rather than definitive evidence of the optimal number of clusters.
- PCA preserves variance but does not necessarily preserve the most useful structure for clustering.
- The notebook does not establish predictive performance or future investment returns.
- Quantitative cluster quality measures would strengthen the comparison.

## Repository Structure

```text
CryptoClustering/
├── README.md
├── .gitignore
├── Crypto_Clustering_starter_code.ipynb
└── Resources/
    └── crypto_market_data.csv
```

## How to Run the Project

1. Download or clone the repository.
2. Install Python and Jupyter Notebook.
3. Install the required packages:

```bash
pip install pandas scikit-learn hvplot
```

4. Open `Crypto_Clustering_starter_code.ipynb` in Jupyter Notebook.
5. Confirm that `crypto_market_data.csv` is located in the `Resources` folder.
6. Run the notebook cells sequentially.

The notebook uses a relative file path to load the dataset.

## Future Improvements

Potential enhancements include:

- Calculating silhouette scores to evaluate cluster separation.
- Comparing K-Means with alternative clustering algorithms.
- Investigating cluster stability across different random seeds.
- Evaluating additional dimensionality reduction methods.
- Examining how cluster membership changes across different market periods.

## Conclusion

This project demonstrates how K-Means clustering and PCA can be combined to explore cryptocurrency price behavior.

Reducing seven standardized features to three principal components retains approximately 89.50% of the original variance and allows clustering results to be examined in a lower dimensional space.

The findings demonstrate the usefulness of dimensionality reduction for exploratory analysis while emphasizing the importance of quantitative validation before drawing conclusions about clustering quality.

## Author

Adam A. Saenz

Data Science Portfolio

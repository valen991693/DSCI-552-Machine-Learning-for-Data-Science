# Homework 7 — Classification and Clustering

This repository contains Homework 7 for DSCI 552. The assignment focuses on multi-class and multi-label classification, unsupervised clustering, and hierarchical clustering.

The analysis uses the Anuran Calls (MFCCs) dataset to compare Support Vector Machine (SVM) classifiers and evaluate K-Means clustering. It also includes hierarchical clustering exercises from *An Introduction to Statistical Learning (ISLR)*.

## Contents

- `notebook/Kim_Beomjun_HW7.ipynb`: Homework 7 solution
- `data/`: Anuran Calls (MFCCs) dataset
  - `Frogs_MFCCs.csv`
- `references/`: Homework instructions and reference materials

## Part 1 — Multi-Class and Multi-Label Classification

Part 1 focuses on predicting three hierarchical labels (**Family**, **Genus**, and **Species**) using Support Vector Machines.

The analysis covers:

- Loading and exploring the Anuran Calls (MFCCs) dataset
- Training and test data partitioning
- Exact match ratio, Hamming loss, and Hamming score
- Gaussian RBF kernel SVM classification
- One-vs-Rest classification for each label
- Hyperparameter tuning using 10-fold cross-validation
- Feature standardization and L1-penalized linear SVM
- Handling class imbalance using SMOTE
- Comparison of classification performance across models

## Part 2 — K-Means Clustering

Part 2 applies unsupervised K-Means clustering to the Anuran Calls dataset and evaluates clustering performance using the original class labels.

The analysis covers:

- K-Means clustering using MFCC features
- Selection of the optimal number of clusters using the Calinski-Harabasz Index
- Evaluation of cluster counts from **K = 2 to K = 50**
- Monte Carlo simulations with different random seeds
- Determination of majority **Family**, **Genus**, and **Species** labels within each cluster
- Calculation of average Hamming distance, Hamming score, and Hamming loss
- Summary statistics across **50 simulations**

## Part 3 — Hierarchical Clustering

Part 3 covers ISLR Exercise 12.6.2, focusing on hierarchical clustering using a given dissimilarity matrix.

The analysis covers:

- Complete linkage hierarchical clustering
- Single linkage hierarchical clustering
- Construction and interpretation of dendrograms
- Identification of clusters by cutting dendrograms
- Comparison of clustering structures and merge heights
- Equivalent dendrograms through branch rearrangement

## Running the Notebook

Clone the repository and navigate to the notebook directory:

```bash
cd notebook
```

Then open the notebook:

```text
Kim_Beomjun_HW7.ipynb
```

The notebook uses a relative path to access the dataset:

```python
df = pd.read_csv("../data/Frogs_MFCCs.csv")
```

Therefore, the repository directory structure should be preserved when running the notebook.

## Dataset

The assignment uses the **Anuran Calls (MFCCs) dataset**, which contains audio-derived features from frog calls.

The dataset includes:

- **7,195 observations**
- **22 Mel-Frequency Cepstral Coefficient (MFCC) features**
- **Three classification labels:** Family, Genus, and Species
- **RecordID:** An additional identifier column

The MFCC features are used as predictors for supervised classification and as input variables for unsupervised clustering.

The hierarchical classification labels are used to evaluate both classification and clustering performance.

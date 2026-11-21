# Homework 8 — Supervised, Semi-Supervised, Unsupervised, and Active Learning

This repository contains Homework 8 for DSCI 552. The assignment focuses on comparing supervised, semi-supervised, and unsupervised learning methods, as well as evaluating active and passive learning strategies.

The analysis uses the Wisconsin Diagnostic Breast Cancer dataset to compare Support Vector Machine (SVM) classifiers and clustering algorithms. It also uses the Banknote Authentication dataset to investigate the effectiveness of active learning in reducing classification error with fewer labeled observations.

## Contents

- `notebook/Kim_Beomjun_HW8.ipynb`: Homework 8 solution
- `data/`: Datasets used in the assignment
  - `wdbc.data`: Wisconsin Diagnostic Breast Cancer dataset
  - `data_banknote_authentication.txt`: Banknote Authentication dataset
- `references/`: Homework instructions and reference materials

## Part 1 — Supervised, Semi-Supervised, and Unsupervised Learning

Part 1 compares four learning approaches using the Wisconsin Diagnostic Breast Cancer dataset.

### Supervised Learning

The analysis covers:

* Stratified training and test data partitioning
* L1-penalized linear Support Vector Machine (SVM)
* Hyperparameter tuning using 5-fold cross-validation
* Feature standardization using StandardScaler
* Monte Carlo simulations across **30 iterations**
* Evaluation using accuracy, precision, recall, F1-score, and ROC-AUC
* Confusion matrices and ROC curves

### Semi-Supervised Learning

The analysis covers:

* Random selection of initially labeled training observations
* Iterative self-training using an L1-penalized linear SVM
* Selection of unlabeled observations based on SVM decision-function confidence
* Assignment of pseudo-labels to selected observations
* Evaluation of classification performance across **30 Monte Carlo iterations**
* Comparison with fully supervised learning

### Unsupervised Learning — K-Means Clustering

The analysis covers:

* K-Means clustering with two clusters
* Multiple random initializations
* Majority-vote labeling using observations closest to cluster centers
* Assignment of test observations to clusters
* Evaluation using classification metrics, confusion matrices, and ROC curves
* Performance comparison with supervised and semi-supervised learning

### Unsupervised Learning — Spectral Clustering

The analysis covers:

* Spectral clustering using the Gaussian RBF kernel
* Evaluation of different RBF gamma values
* Selection of gamma based on cluster-size differences
* Cluster assignment using fit_predict()
* Majority-vote labeling of training clusters
* Approximate out-of-sample assignment using RBF similarities
* Evaluation across **30 Monte Carlo iterations**
* Comparison with K-Means clustering and SVM-based methods

### Performance Comparison

The four learning approaches are compared using:

* Accuracy
* Precision
* Recall
* F1-score
* Area Under the ROC Curve (AUC)

The analysis examines differences in classification performance and the effectiveness of learning from fully labeled, partially labeled, and unlabeled data.

## Part 2 — Active Learning vs. Passive Learning

Part 2 compares active and passive learning strategies using the Banknote Authentication dataset.

### Passive Learning

The analysis covers:

* Stratified training and test data partitioning
* L1-penalized linear SVM classification
* Hyperparameter tuning using 5-fold cross-validation
* Random selection of additional labeled observations
* Incremental training set expansion in batches of 10
* Evaluation across **50 Monte Carlo iterations**
* Recording test errors at **90 training sizes**

### Active Learning

The analysis covers:

* Initialization with a small labeled training set
* Training an L1-penalized linear SVM
* Selection of unlabeled observations closest to the SVM decision boundary
* Incremental training set expansion in batches of 10
* Hyperparameter tuning using 5-fold cross-validation
* Evaluation across **50 Monte Carlo iterations**
* Recording test errors at **90 training sizes**

### Learning Curve Comparison

The analysis compares the average test errors of passive and active learning as the number of labeled training observations increases.

The comparison focuses on:

* Test error across different training set sizes
* Label efficiency of active learning
* Performance differences when labeled data is limited
* Convergence of classification performance as more labeled observations become available

## Running the Notebook

Clone the repository and navigate to the Homework 8 notebook directory:

```bash
cd "Homework 8/notebook"
```

Then open the notebook:

```text
Kim_Beomjun_HW8.ipynb
```

The notebook uses relative paths to access the datasets:

```python
df = pd.read_csv("../data/wdbc.data", header=None)
```

```python
banknote = pd.read_csv(
    "../data/data_banknote_authentication.txt",
    header=None,
    names=["variance", "skewness", "curtosis", "entropy", "class"]
)
```

Therefore, the repository directory structure should be preserved when running the notebook.

## Datasets

### Wisconsin Diagnostic Breast Cancer Dataset

The dataset contains measurements derived from digitized images of breast mass cell nuclei.

The dataset includes:

* **569 observations**
* **30 numerical features**
* **Two diagnostic classes:** Benign and Malignant
* **ID:** An additional identifier column

The numerical features are used as predictors for supervised classification and as input variables for unsupervised clustering.

The diagnostic labels are used to evaluate classification and clustering performance.

### Banknote Authentication Dataset

The dataset contains features extracted from images of genuine and forged banknotes.

The dataset includes:

* **1,372 observations**
* **Four numerical features:** Variance, Skewness, Curtosis, and Entropy
* **Two classification labels:** Genuine and Forged

The numerical features are used to train L1-penalized linear SVM classifiers.

The classification labels are used to evaluate passive and active learning performance as the number of labeled training observations increases.

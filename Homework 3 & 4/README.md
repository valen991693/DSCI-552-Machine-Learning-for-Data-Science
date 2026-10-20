# Homework 3 & 4 — Time Series Classification

This repository contains Homework 3 and Homework 4 for DSCI 552. The two assignments form a continuous time series classification project using the AReM Activity Recognition dataset.

Homework 3 focuses on data preparation and time-domain feature extraction, while Homework 4 extends the analysis to binary and multiclass classification using logistic regression and Naive Bayes methods.

## Contents

- `notebook/Kim_Beomjun_HW3.ipynb`: Homework 3 solution
- `notebook/Kim_Beomjun_HW4.ipynb`: Homework 4 solution
- `data/`: AReM Activity Recognition dataset
  - `bending1/`
  - `bending2/`
  - `cycling/`
  - `lying/`
  - `sitting/`
  - `standing/`
  - `walking/`
- `references/`: Homework instructions and reference materials

## Homework 3 — Feature Creation and Extraction

Homework 3 covers:

- Loading and cleaning the AReM Activity Recognition dataset
- Training and test data partitioning
- Time-domain feature extraction from sensor time series
- Estimation of feature standard deviations
- Bootstrap confidence intervals for feature standard deviations
- Selection of important time-domain features

## Homework 4 — Binary and Multiclass Classification

Homework 4 builds on the feature extraction procedures developed in Homework 3 and covers:

- Binary classification of bending versus other activities
- Time-series segmentation and segmented feature extraction
- Logistic regression with recursive feature elimination
- Cross-validation for model and feature selection
- Confusion matrices, ROC curves, and AUC
- Class separation and class imbalance
- Case-control sampling and intercept adjustment
- L1-penalized logistic regression
- Multiclass L1-penalized logistic regression
- Gaussian and Multinomial Naive Bayes
- Multiclass model comparison
- ISLR classification exercises

## Running the Notebooks

Clone the repository and navigate to the notebook directory:

```bash
cd notebook
```

Then open either notebook:

```text
Kim_Beomjun_HW3.ipynb
Kim_Beomjun_HW4.ipynb
```

Both notebooks use a relative path to access the dataset:

```python
DATA_DIR = Path("../data")
```

Therefore, the repository directory structure should be preserved when running the notebooks.

## Dataset

The assignments use the AReM Activity Recognition dataset, which contains sensor measurements for seven human activities:

- bending1
- bending2
- cycling
- lying
- sitting
- standing
- walking

Each activity contains multiple time-series instances used for feature extraction and classification.

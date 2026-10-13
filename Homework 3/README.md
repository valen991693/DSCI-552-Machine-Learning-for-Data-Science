# Homework 3

## Contents

- `notebook/Kim_Beomjun_HW3.ipynb`: Homework 3 solution
- `data/`: AReM Activity Recognition dataset
  - `bending1/`
  - `bending2/`
  - `cycling/`
  - `lying/`
  - `sitting/`
  - `standing/`
  - `walking/`
- `references/`: Homework instructions and reference materials

## Topics

This homework covers:

- Time series classification and feature extraction
- Training and test data partitioning
- Time-domain feature extraction from sensor data
- Bootstrap confidence intervals for feature standard deviations
- Selection of important time-domain features
- ISLR regression exercises

## Running the Notebook

Clone the repository and navigate to the Homework 3 notebook directory:

```bash
cd "3. Homework 3/notebook"
```

Then open:

```text
Kim_Beomjun_HW3.ipynb
```

The notebook uses a relative path to access the dataset:

```python
DATA_DIR = Path("../data")
```

Therefore, the directory structure should be preserved when running the notebook.

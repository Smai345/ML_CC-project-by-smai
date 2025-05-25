
# 📊 Task 1: Level 1 – Variable Identification Protocol

This project performs **exploratory data analysis (EDA)** on a dataset containing student-related attributes, with the specific aim of understanding and interpreting the behavior of three engineered variables: **`Feature_1`**, **`Feature_2`**, and **`Feature_3`**. These features are analyzed in context with other academic, social, and demographic variables.

---

## 🧾 Dataset Overview

- **Rows**: 649
- **Columns**: 33
- **Features include**:
  - Demographic info (e.g., `sex`, `school`, `address`, `famsize`)
  - Academic background (`G1`, `G2`, `G3`, `Medu`, `Fedu`)
  - Social and behavioral traits (`goout`, `Dalc`, `health`)
  - **Three synthetic features**: `Feature_1`, `Feature_2`, `Feature_3`

---

## 📂 Project Structure

```text
├── Task 1.ipynb        # Main notebook for analysis
├── Dataset.csv         # Student dataset (assumed file)
└── README.md           # This file
```

---

## 🔍 Objective

The goal of this task is to:

1. **Identify and analyze** the role of `Feature_1`, `Feature_2`, and `Feature_3`.
2. **Visualize** the distribution of these features.
3. **Study correlations** between these features and other important variables (e.g., grades, failures, social factors).
4. **Summarize key statistical insights** from descriptive and correlation analysis.

---

## 🧪 Approach and Methodology

### 1. **Import Libraries**
Standard Python libraries are used:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. **Load and Inspect Data**
Data is read into a DataFrame:
```python
df = pd.read_csv("Dataset.csv")
df.info()
```

This gives an overview of column types, missing values, and memory usage.

---

### 3. **Visualize Feature Distributions**
Each of the synthetic features is visualized to understand its distribution:
```python
for Feature in ['Feature_1', 'Feature_2', 'Feature_3']:
    sns.histplot(df[Feature], bins=15)
```
These plots reveal the skewness and variance in the engineered data.

---

### 4. **Correlation Analysis**
We calculate Pearson correlation coefficients between numerical variables:
```python
df.corr(numeric_only=True)
```

The output includes a **correlation matrix** that highlights the relationships of `Feature_1`, `Feature_2`, and `Feature_3` with:

- Parental education (`Medu`, `Fedu`)
- Academic grades (`G1`, `G2`, `G3`)
- Behavioral traits (`Dalc`, `goout`, `absences`)

---

### 5. **Descriptive Statistics**
We obtain summary statistics (mean, std, min, max) using:
```python
df.describe()
```

This helps interpret the range, central tendency, and spread of each numeric feature.

---

### 6. **Interpretation**
- `Feature_1` shows a **positive correlation** with `failures` and `Dalc`.
- `Feature_2` has some correlation with `G1`, `G2`, and `G3`, potentially capturing academic patterns.
- `Feature_3` aligns moderately with `goout` and social behavior patterns.

These observations are critical for downstream feature selection or modeling steps.

---

## 📌 Conclusions

- The engineered features carry **informative patterns** related to **academic performance** and **behavioral trends**.
- **Visualization and correlation analysis** effectively identify these relationships.
- Some variables have **missing values**, which have been handled as part of this analysis.

---

## ▶️ How to Run

1. Make sure Python and Jupyter Notebook are installed.
2. Place `Dataset.csv` and `Task 1.ipynb` in the same folder.
3. Run the notebook sequentially to reproduce the results and plots.

---

## ✅ Requirements

This notebook uses:

- Python 3.7+
- pandas
- numpy
- matplotlib
- seaborn

Install them via:

```bash
pip install pandas numpy matplotlib seaborn
```

---

## 🧠 Further Exploration

The following aspects have already been addressed in the notebook:

- ✅ Handling of missing values
- ✅ Distribution analysis of synthetic features
- ✅ Correlation analysis with academic and behavioral variables
- ✅ Statistical summaries and insights.

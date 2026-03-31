# Opioid Overdose Forecasting & Risk Analysis

## Overview

This project analyzes opioid overdose trends across U.S. states by integrating multiple public health datasets. The goal is to forecast overdose death rates and identify mismatches between overdose risk and naloxone distribution.

Using machine learning models and clustering techniques, this project highlights high-risk states and gaps in intervention coverage.

📄 **Full report included:**
`FINAL Opioid OD Deaths - Indicators & Actions.pdf`

---

## Key Questions

* What factors are most predictive of opioid overdose deaths?
* How well can overdose rates be forecasted at the state level?
* Are naloxone dispensing rates aligned with overdose risk?
* Which states are most at risk of worsening outcomes?

---

## Data Sources

* CDC SUDORS Overdose Death Data
* DEA ARCOS Naloxone Dispensing Data
* U.S. Census Demographic Data
* U.S. Census Population Data
* Bureau of Labor Statistics Unemployment Data

All datasets are included in this repository for reproducibility.

---

## Methodology

### Data Integration

* Combined 5 datasets at the state-year level (2020–2023)
* Merged using left and inner joins
* Handled missing values via imputation

### Feature Engineering

* Created derived variables (e.g., differenced unemployment)
* Aggregated overdose subtype metrics
* One-hot encoded categorical features

### Modeling

* Linear Regression
* Random Forest
* Gradient Boosting

**Random Forest selected for best performance (R² ≈ 0.98)**

### Clustering & Risk Analysis

* K-means clustering on projected 2027 outcomes
* Built a **risk index** based on:

  * Predicted overdose rates
  * Predicted naloxone dispensing rates

---

## Key Findings

* Illegally manufactured fentanyl (IMF) is the strongest predictor of overdose deaths
* Demographic variables were weaker predictors than expected
* Significant misalignment exists between overdose burden and naloxone distribution
* High-risk states include:

  * West Virginia
  * Delaware
  * Washington, DC
* Overdose deaths show seasonal trends (summer/early fall peaks)

---

## Repository Structure

```
opioid-overdose-analysis/
│
├── notebooks/
│   ├── clean_analysis.ipynb
│   └── exploratory_analysis.ipynb
│
├── data/        # Raw datasets
├── outputs/     # Generated CSV outputs
│
├── FINAL Opioid OD Deaths - Indicators & Actions.pdf
└── README.md
```

---

## Notebooks

### Cleaned Notebook (Recommended)

`clean_analysis.ipynb`

* Streamlined and reproducible
* Focused on modeling and results
* Best entry point for recruiters

### Exploratory Notebook

`exploratory_analysis.ipynb`

* Full exploratory workflow
* Additional visualizations and analysis
* Demonstrates depth of work

---

## Outputs

Running the cleaned notebook generates:

* `overdose_model_results.csv`
* `naloxone_model_results.csv`
* `prediction_results.csv`
* `risk_index_2027.csv`

---

## How to Run

1. Clone the repository
2. Open the cleaned notebook
3. Ensure datasets are in the same directory
4. Run all cells

---

## Tools & Technologies

* Python (pandas, NumPy)
* scikit-learn
* matplotlib / seaborn
* Excel

---

## Limitations

* Limited time range (2020–2023)
* State-level aggregation may mask local variation
* Some missing data required imputation
* Naloxone data may not reflect real-time access

---

## Future Work

* Add county-level data
* Incorporate real-time signals (911 calls, prescriptions)
* Improve forecasting models
* Expand intervention analysis beyond naloxone

---

## Author: Waleed Jamil
Syracuse University – Applied Data Science

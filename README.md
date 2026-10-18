# CodGen Machine Learning Virtual Internship — Week 1

## 📌 Project Overview: Data Exploration & Preprocessing
This repository contains the complete Week 1 submission for the **CodGen Machine Learning Virtual Internship**. The project focuses on rigorous exploratory data analysis (EDA), handling missing values with statistical justification, categorical feature encoding, and data visualization on the Titanic dataset.

---

## 🚀 Key Tasks & Deliverables

- **Task 1 — Load & Explore Dataset**: 
  - Comprehensive inspection of shapes, data types, distributions, and missing values using Pandas.
- **Task 2 — Handle Missing Values**: 
  - **`Age` (19.9% missing)**: Imputed using **median** due to positive skewness and outliers.
  - **`Embarked` (0.2% missing)**: Imputed using **mode** (`'S'`, representing >72% of entries).
  - **`Cabin` (77.1% missing)**: Extracted high-value binary feature `Has_Cabin` to preserve wealth/class proxy, then removed the sparse raw column.
- **Task 3 — Encode Categorical Columns**: 
  - **`Sex`**: Transformed via **Label Encoding** (0 = female, 1 = male) without dimensionality explosion.
  - **`Embarked`**: Transformed via **One-Hot Encoding** (`drop_first=True`) to prevent misleading ordinal hierarchy between nominal ports.
- **Task 4 — Data Visualisation**: 
  - Numerical distributions (Histograms with KDE for `Age` and `Fare`).
  - Categorical survival rates (Bar plots with percentage annotations for `Sex` and `Pclass`).
  - Complete correlation heatmap using Seaborn.
- **Task 5 — Key Observations & Insights**: 
  - Data-driven conclusions on the "women & children first" evacuation protocol, class divide, wealth proxies, and removal of non-generalizable identifiers (`PassengerId`, `Name`, `Ticket`).

---

## 📈 Key Insights Summary

1. **Gender Disparity:** Female survival rate was **74.2%** vs. male survival rate of **18.9%** ($r \approx -0.54$).
2. **Socioeconomic Stratification:** First-class passengers survived at **63.0%**, compared to 47.3% for second-class and 24.2% for third-class ($r \approx -0.34$).
3. **Wealth Proxy:** Passengers with recorded cabin manifests had a **66.7%** survival rate vs. **30.0%** for unrecorded passengers ($r \approx +0.32$).
4. **Vulnerability Factor:** Children aged 0–10 experienced higher survival rates (>60%) regardless of ticket class.
5. **Feature Relevance:** `Sex`, `Pclass`, `Fare`, `Has_Cabin`, and `Age` are top predictive drivers; metadata like `PassengerId`, `Name`, and `Ticket` provide no predictive utility and are dropped for modeling.

---

## 📂 Repository Structure

```
├── Rinitesh_Week1_MLInternship.ipynb  # Primary executed Jupyter Notebook (all outputs & plots embedded)
├── titanic.csv                        # Dataset
├── build_and_execute_notebook.py      # Automated generation and validation script
├── CodGen_Week1_ML_Task.pdf           # Internship task specification
├── .gitignore                         # Python & environment ignore rules
└── README.md                          # Project documentation
```

---

## 🛠️ Tech Stack
- **Language:** Python 3.12
- **Data Analysis:** Pandas, NumPy
- **Visualisation:** Matplotlib, Seaborn
- **Machine Learning Preprocessing:** Scikit-Learn
- **Environment:** Jupyter Notebook / IPython Kernel

---

## 👤 Author
- **Name:** Rinitesh Singh
- **Internship:** CodGen Virtual Internship Program — Machine Learning (October 2026)

# CodGen Machine Learning Virtual Internship

Repository containing complete weekly project submissions, exploratory notebooks, and machine learning models for the **CodGen Machine Learning Virtual Internship Program** (October - November 2026).

---

## 📌 Program Roadmap & Deliverables

| Week | Milestone | Focus Areas | Primary Notebook | Status |
| :---: | :--- | :--- | :--- | :---: |
| **Week 1** | **Data Exploration & Preprocessing** | Missing value imputation, categorical encoding, EDA, Seaborn visualizations | [`Rinitesh_Week1_MLInternship.ipynb`](./Rinitesh_Week1_MLInternship.ipynb) | ✅ Completed |
| **Week 2** | **Supervised Learning — Classification** | Train/Test split, Logistic Regression, Decision Trees, Random Forests, Confusion Matrices | [`Rinitesh_Week2_MLInternship.ipynb`](./Rinitesh_Week2_MLInternship.ipynb) | ✅ Completed |
| **Week 3** | **Feature Engineering & Model Improvement** | Feature importance, StandardScaler, GridSearchCV tuning, 5-Fold Cross-Validation | [`Rinitesh_Week3_MLInternship.ipynb`](./Rinitesh_Week3_MLInternship.ipynb) | ✅ Completed |
| **Week 4** | **Final Capstone Project** | End-to-end pipeline, advanced ensembling, and deployment preparation | *Upcoming* | ⏳ Queued |

---

## 🚀 Week 3: Feature Engineering & Model Improvement

### 1. Key Tasks & Methodologies
- **Feature Importance:** Extracted Gini importance scores from Random Forest. Identified that **`Sex` (27.1%)**, **`Fare` (24.5%)**, and **`Age` (23.9%)** form over 75% of the total predictive power.
- **Feature Scaling:** Applied `StandardScaler` to continuous numerical features (`Age`, `Fare`, `SibSp`, `Parch`) strictly fitting on the training set to prevent data leakage. Improved solver convergence and derived standardized coefficients.
- **Hyperparameter Tuning:** Conducted `GridSearchCV` with 5-fold cross-validation on Random Forest (`n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf`). Identified optimal configuration (`max_depth: 4`, `min_samples_leaf: 2`, `min_samples_split: 2`, `n_estimators: 100`).
- **5-Fold Cross-Validation:** Evaluated the tuned model across 5 stratified folds, proving high stability (**82.27% Mean Accuracy, $\pm$1.54% Std**).

---

### 2. Before vs. After Model Progression Table

| Model & Stage | Train Accuracy | Test / CV Accuracy | Overfitting Gap | Key Engineering Benefit |
| :--- | :---: | :---: | :---: | :--- |
| **Logistic Regression (Baseline)** | 80.62% | 80.45% | +0.17% | Stable linear baseline |
| **Logistic Regression (StandardScaled)** | 80.62% | 80.45% | +0.17% | Faster solver convergence; standardized weights (`Sex`: -1.30, `Pclass`: -0.86) |
| **Random Forest (Week 2 Default)** | 98.31% | 78.77% | +19.38% | Severely overfitted due to unconstrained tree depth (`max_depth=None`) |
| **Random Forest (Week 3 Tuned via GridSearch)** 🏆 | **85.67%** | **78.21%** | **+7.46%** | **Overfitting gap slashed by >60%** via tree pruning (`max_depth=4`) |
| **Random Forest (5-Fold Stratified CV Mean)** 🌟 | **N/A** | **82.27%** | **Robust** | Proven generalization across dataset folds ($\sigma = \pm 1.54\%$) |

---

## 🚀 Week 2: Supervised Learning — Classification

| Model | Train Accuracy | Test Accuracy | Overfitting Gap | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** 🏆 | 80.62% | 80.45% | +0.17% | 0.7600 | 0.7246 | 0.7385 |
| **Decision Tree** | 98.31% | 79.89% | +18.43% | 0.7692 | 0.7246 | 0.7407 |
| **Random Forest** | 98.31% | 78.77% | +19.38% | 0.7619 | 0.6957 | 0.7185 |

---

## 📂 Repository Structure

```
├── Rinitesh_Week3_MLInternship.ipynb  # Week 3 Executed Notebook (Scaling, GridSearchCV, CV)
├── Rinitesh_Week2_MLInternship.ipynb  # Week 2 Executed Notebook (Baseline models, confusion matrices)
├── Rinitesh_Week1_MLInternship.ipynb  # Week 1 Executed Notebook (EDA, preprocessing, visualisations)
├── titanic.csv                        # Dataset
├── build_and_execute_week3_notebook.py# Week 3 automated build script
├── build_and_execute_week2_notebook.py# Week 2 automated build script
├── build_and_execute_notebook.py      # Week 1 automated build script
├── CodGen_Week1_ML_Task.pdf           # Task Specification
├── .gitignore                         # Git exclusion rules
└── README.md                          # Portfolio Project Documentation
```

---

## 🛠️ Tech Stack
- **Language:** Python 3.12
- **Data Engineering:** Pandas, NumPy
- **Machine Learning & Tuning:** Scikit-Learn (`StandardScaler`, `GridSearchCV`, `StratifiedKFold`, `RandomForestClassifier`, `LogisticRegression`)
- **Evaluation:** Scikit-Learn Metrics (`cross_val_score`, `classification_report`, `accuracy_score`, `f1_score`)
- **Data Visualization:** Seaborn, Matplotlib

---

## 👤 Author
- **Name:** Rinitesh Singh
- **Internship:** CodGen Virtual Internship Program — Machine Learning (October - November 2026)

# CodGen Machine Learning Virtual Internship

Repository containing complete weekly project submissions, exploratory notebooks, and machine learning models for the **CodGen Machine Learning Virtual Internship Program** (October 2026).

---

## 📌 Program Roadmap & Deliverables

| Week | Milestone | Focus Areas | Primary Notebook | Status |
| :---: | :--- | :--- | :--- | :---: |
| **Week 1** | **Data Exploration & Preprocessing** | Missing value imputation, categorical encoding, EDA, Seaborn visualizations | [`Rinitesh_Week1_MLInternship.ipynb`](./Rinitesh_Week1_MLInternship.ipynb) | ✅ Completed |
| **Week 2** | **Supervised Learning — Classification** | Train/Test split, Logistic Regression, Decision Trees, Random Forests, Confusion Matrices | [`Rinitesh_Week2_MLInternship.ipynb`](./Rinitesh_Week2_MLInternship.ipynb) | ✅ Completed |
| **Week 3** | **Hyperparameter Tuning & Optimization** | Cross-validation, Grid/Random Search, Model regularization, ROC-AUC | *Upcoming* | ⏳ Queued |

---

## 🚀 Week 2: Supervised Learning — Classification

### 1. Overview
In Week 2, the cleaned Titanic dataset from Week 1 was transformed into predictive models. The objective was to train, evaluate, and objectively compare three core supervised classification algorithms using standard classification metrics:

1. **Logistic Regression** (Linear baseline)
2. **Decision Tree Classifier** (Non-parametric greedy recursive partitioning)
3. **Random Forest Classifier** (Ensemble bootstrap aggregation)

---

### 2. Experimental Setup
- **Split Ratio:** 80% Training ($N = 712$), 20% Testing ($N = 179$)
- **Stratification:** Stratified on target `Survived` to preserve class balance (~61.6% non-survivors, ~38.4% survivors) across splits.
- **Reproducibility:** Seeded with `random_state=42`.
- **Features Used:** `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Has_Cabin`, `Embarked_Q`, `Embarked_S`.

---

### 3. Model Performance & Comparison Table

| Model | Train Accuracy | Test Accuracy | Overfitting Gap | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** 🏆 | **80.62%** | **80.45%** | **+0.17%** | **0.7600** | **0.7246** | **0.7385** |
| **Decision Tree** | 98.31% | 79.89% | +18.43% | 0.7692 | 0.7246 | 0.7407 |
| **Random Forest** | 98.31% | 78.77% | +19.38% | 0.7619 | 0.6957 | 0.7185 |

---

### 4. Key Findings & Diagnostic Observations

- **Best Performer (Logistic Regression):**  
  Achieved the highest test accuracy (**80.45%**) and demonstrated near-perfect generalization with an overfitting gap of just **0.17%**. Its linear log-odds formulation effectively leveraged the dominant signals (`Sex` and `Pclass`) without learning training noise.
- **Overfitting in Default Tree Models:**  
  Both unpruned Decision Trees and default Random Forests achieved **98.31%** accuracy on the training set but dropped to ~79% on the test set (~18–19% gap). Without tree-depth constraints (`max_depth=None`), individual trees split until leaves were pure, memorizing spurious passenger patterns.
- **Model Recommendation:**  
  Logistic Regression is selected as the most reliable, production-ready baseline model for Week 2. Random Forest remains the highest-potential candidate for Week 3 once constrained with hyperparameter tuning.

---

## 📂 Repository Structure

```
├── Rinitesh_Week2_MLInternship.ipynb  # Week 2 Executed Notebook (Models, reports, confusion heatmaps)
├── Rinitesh_Week1_MLInternship.ipynb  # Week 1 Executed Notebook (EDA, preprocessing, visualisations)
├── titanic.csv                        # Titanic Dataset
├── build_and_execute_week2_notebook.py# Week 2 pipeline generator
├── build_and_execute_notebook.py      # Week 1 pipeline generator
├── CodGen_Week1_ML_Task.pdf           # Week 1 Task Specification
├── .gitignore                         # Git exclusion rules
└── README.md                          # Project Documentation
```

---

## 🛠️ Tech Stack
- **Language:** Python 3.12
- **Data Engineering:** Pandas, NumPy
- **Machine Learning:** Scikit-Learn (`LogisticRegression`, `DecisionTreeClassifier`, `RandomForestClassifier`)
- **Evaluation:** Scikit-Learn Metrics (`confusion_matrix`, `classification_report`, `accuracy_score`, `f1_score`)
- **Data Visualization:** Seaborn, Matplotlib

---

## 👤 Author
- **Name:** Rinitesh Singh
- **Internship:** CodGen Virtual Internship Program — Machine Learning (October 2026)

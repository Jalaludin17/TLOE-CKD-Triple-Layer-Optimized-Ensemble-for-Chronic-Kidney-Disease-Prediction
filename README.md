# TLOE-CKD: Triple-Layer Optimized Ensemble for Chronic Kidney Disease Detection

![Accuracy](https://img.shields.io/badge/Accuracy-99%25-green)
![Recall](https://img.shields.io/badge/Recall-1.00-blue)
![MCC](https://img.shields.io/badge/MCC-0.9794-orange)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)

## 📌 Project Overview
Early diagnosis of Chronic Kidney Disease (CKD) is critical for clinical intervention. This repository implements the **TLOE-CKD** framework, a high-performance diagnostic pipeline that combines evolutionary feature selection with a multi-stage stacking ensemble.

The framework optimizes the diagnostic process by reducing the required clinical tests from 24 to 11 "Golden Features" while maintaining near-perfect predictive accuracy.



## 🛠 Methodology
The TLOE-CKD architecture consists of three primary phases:

1. **Preprocessing & Imputation:** Missing clinical values are handled using **MICE (Multivariate Imputation by Chained Equations)** to preserve the statistical distribution of the renal markers.
2. **Feature Evolution:** A **Genetic Algorithm (GA)** identifies a "Golden Subset" of 11 features (including Hemoglobin, Specific Gravity, and Serum Creatinine) to reduce dimensionality and computational cost.
3. **Triple-Layer Classification:**
   - **Layer 1 (Base):** Random Forest and XGBoost.
   - **Layer 2 (Meta):** Lasso-regularized Logistic Regression to prevent overfitting.
   - **Layer 3 (Output):** Final diagnostic classification.

## 📊 Experimental Results
The model was validated on the UCI Repository CKD Dataset. The results demonstrate that the feature reduction does not compromise safety:

| Metric | Score |
| :--- | :--- |
| **Accuracy** | 99.0% |
| **Recall (Sensitivity)** | **1.00** |
| **Precision (Healthy)** | 1.00 |
| **MCC Score** | **0.9794** |
| **F1-Score** | 0.99 |



## 📂 Repository Structure
```text
├── data/                   # Dataset files (UCI CKD)
├── src/
│   ├── imputation.py       # MICE implementation
│   ├── feature_selection.py # Genetic Algorithm script
│   └── model.py            # Stacked Ensemble architecture
├── notebooks/              # EDA and result analysis
├── results/                # Confusion Matrix, ROC, and t-SNE plots
└── requirements.txt        # Dependencies
```

## 📊 Experimental Results
🚀 Getting Started
```text
**Installation**
git clone [https://github.com/yourusername/TLOE-CKD.git](https://github.com/yourusername/TLOE-CKD.git)
cd TLOE-CKD
pip install -r requirements.txt
Running the Framework
Python
from src.model import TLOECKD
```
```text
**Initialize and run the full pipeline**
model = TLOECKD()
model.fit(X_train, y_train)
results = model.evaluate(X_test, y_test)
print(f"MCC Score: {results['mcc']}")
```

## 🔬 Class Separability
The effectiveness of the Genetic Algorithm's feature selection is visually confirmed through t-SNE manifold projections. The 11 selected features allow for clear, non-overlapping spatial segregation between healthy subjects and CKD patients.

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

Developed for research in Bioinformatics and Clinical Machine Learning.

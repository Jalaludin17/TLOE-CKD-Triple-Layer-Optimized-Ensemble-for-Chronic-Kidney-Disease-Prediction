TLOE-CKD: Triple-Layer Optimized Ensemble for Chronic Kidney Disease Detection
📖 Project Summary
This repository contains the implementation of the TLOE-CKD (Triple-Layer Optimized Ensemble) framework. This research addresses the challenge of early Chronic Kidney Disease (CKD) detection by combining advanced data imputation, evolutionary feature selection, and specialized ensemble learning.

🛠 Methodology
The architecture follows a three-stage optimization pipeline:

Data Completion: Utilizing MICE (Multivariate Imputation by Chained Equations) to handle missing clinical values without introducing bias.

Feature Evolution: Implementation of a Genetic Algorithm (GA) to reduce the feature space from 24 attributes to a "Golden Subset" of 11 critical biomarkers.

Stacked Ensemble: A multi-layer classification strategy using:

Base Learners: XGBoost and Random Forest.

Meta-Learner: Lasso-regularized Logistic Regression to optimize final predictions and prevent overfitting.

📈 Key Performance Metrics
The framework was validated on the UCI Repository CKD Dataset, achieving:

Accuracy: 99.0%

Recall (Sensitivity): 1.00 (Zero False Negatives)

MCC Score: 0.9794

Precision (Healthy): 1.00

🚀 Repository Contents
data/: Raw and processed CKD datasets.

src/preprocessing.py: MICE imputation and data cleaning scripts.

src/genetic_algorithm.py: GA implementation for feature selection.

src/tloe_model.py: The Triple-Layer Stacked Ensemble implementation.

visualizations/: Generated t-SNE, Confusion Matrix, and ROC plots.

💻 Quick Start
Bash
# Clone the repository
git clone https://github.com/yourusername/TLOE-CKD.git

# Install requirements
pip install -r requirements.txt

# Run the full pipeline
python main.py
🔬 Visualizing Class Separation
The effectiveness of the selected "Golden Features" is demonstrated through t-SNE manifold projections, showing clear spatial segregation between healthy patients and those with CKD.

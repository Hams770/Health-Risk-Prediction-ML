# Health Risk Prediction Using Machine Learning
### Across Heterogeneous Patient Populations

---

## 📌 Project Overview
This project focuses on predicting hospital mortality for ICU patients using machine learning techniques. The goal is to build models that can identify high-risk patients using structured clinical data.

The dataset used is the **eICU Collaborative Research Database (Demo v2.0)**, which contains multi-center ICU patient records. This makes the problem more realistic due to variability across hospitals.

---

## 🎯 Objectives
- Predict ICU mortality (0 = Alive, 1 = Expired)
- Compare multiple machine learning models
- Handle class imbalance effectively
- Evaluate robustness using adversarial label noise
- Improve performance using ensemble learning

---

## ⚙️ Project Pipeline

1. Problem Definition
2. Data Collection
3. Preprocessing & EDA
4. Feature Engineering
5. Model Training
6. Hyperparameter Tuning
7. Ensemble Modeling
8. Final Evaluation

---

## 📊 Dataset
- Source: eICU Collaborative Research Database (Demo v2.0)
- Tables used:
- `patient.csv`
- `apachePatientResult.csv`
- `apachePredVar.csv`
- `apacheApsVar.csv`

📎 Dataset link: https://physionet.org/content/eicu-crd-demo/2.0.1/

---

## 🧹 Data Preprocessing
- Removed columns with >70% missing values
- Removed data leakage features (e.g., discharge info)
- Aggregated APACHE tables
- Handled missing values using pipelines
- Applied scaling and encoding

---

## 🧠 Feature Engineering
- Created `is_senior` (age ≥ 65)
- Created `bun_log` (log transformation of BUN)
- Explored PCA (not used in final model)

---

## 🤖 Models Used
- Logistic Regression
- Decision Tree
- Random Forest
- SVM
- KNN
- Naive Bayes
- Gradient Boosting
- XGBoost

---

## ⚡ Key Techniques
- Stratified Train/Validation/Test split
- 5-Fold Cross Validation
- Threshold tuning
- Hyperparameter tuning (GridSearch & RandomizedSearch)
- Adversarial label noise (10%)
- Soft Voting Ensemble

---

## 📈 Results

| Model | Accuracy | Precision | Recall | F1 | AUC |
|------|--------|----------|--------|-----|------|
| Voting Ensemble | 0.892857 | 0.380000 | 0.452381 | 0.413043 | 0.800041 |
| Baseline XGBoost | 0.797619 | 0.227273 | 0.595238 | 0.328947 | 0.799732 |
| Tuned XGBoost | 0.861111 | 0.274194 | 0.404762 | 0.326923 | 0.780561 |

---

## 🧪 Key Findings
- XGBoost was the best individual model
- Ensemble model achieved best overall performance
- Class imbalance significantly affects results
- Label noise reduces model reliability
- Feature selection did not improve performance

---

## 🚧 Limitations
- Moderate F1-score due to task difficulty
- Imbalanced dataset (~91% survival)
- Sensitive to noisy labels
- No external validation
- Limited clinical features

---

## 🔮 Future Work
- Use time-series models (LSTM)
- Apply SMOTE for imbalance
- Add explainability (SHAP)
- External validation on full dataset

---

## 💻 Installation

```bash
git clone https://github.com/Hams770/Health-Risk-Prediction-ML.git
cd Health-Risk-Prediction
pip install -r requirements.txt

▶️ Usage

Run the project using Jupyter Notebook:

jupyter notebook notebooks/ML_PROJECT.ipynb
Or upload the notebook to Google Colab and run all cells step-by-step.

The notebook includes:

Data preprocessing
Feature engineering
Model training
Evaluation and results
📁 Project Structure


Health-Risk-Prediction-ML/
│
├── Notebooks/
│ └── ML_PROJECT.ipynb
│
├── presentation/
│ └── ML Presentation.pdf
│
├── Report/
│ └── ML-report.pdf
│
├── Results/
│ ├── IMG_9073.jpeg
│ ├── IMG_9074.jpeg
│ ├── IMG_9075.jpeg
│ └── IMG_9076.jpeg
│
├── README.md
├── requirements.txt

📦 Dependencies

All required libraries are listed in requirements.txt.

Install them using:

pip install -r requirements.txt

👥 Authors

Hams Aljohani
Ghala Alghamdi
Hiba Amanulla
Effat University
Computer Science Department
Course: CS4082 – Machine Learning
Instructor: Dr. Naila Marir

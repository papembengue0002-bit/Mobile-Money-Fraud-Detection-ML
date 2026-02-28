# 🚀 Mobile Money Fraud Detection using Machine Learning

![Python](https://img.shields.io/badge/Python-3.10-blue) ![ML](https://img.shields.io/badge/ML-Logistic%20Regression%2C%20SMOTE-green) ![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 🌟 Project Overview

This project focuses on detecting fraudulent mobile money transactions using machine learning. Fraud in mobile money systems can cause **financial losses and reputational damage**, especially in high-volume services.

The goal is to train a model capable of **identifying suspicious transactions** using a synthetic mobile money transaction dataset.

Key steps include:

- Data exploration and analysis (EDA)  
- Feature engineering  
- Handling class imbalance with SMOTE  
- Training and evaluating a Logistic Regression model  
- Visualization of performance metrics  
- Discussion of practical and financial implications  

---

## 📊 Dataset

**Source:** Synthetic Mobile Money Transaction Dataset  

**Dataset Statistics:**

- **Number of rows:** 1,720,181  
- **Number of columns:** 10  
- **Normal transactions:** 1,235,730  
- **Fraudulent transactions:** 140,414 (~11%)  

> Note: The dataset is **highly imbalanced**, which is common in fraud detection.



## 🔍 Methodology

### 1️⃣ Exploratory Data Analysis
- Checked dataset dimensions and feature types  
- Examined class distribution and imbalance  
- Analyzed correlation between numerical features  

### 2️⃣ Feature Engineering
- Calculated balance differences for transaction initiator  
- Created transaction-to-balance ratios  
- Computed balance change errors (detect anomalies)  
- One-hot encoded categorical features (transaction type)  

### 3️⃣ Handling Imbalanced Data
- Applied **SMOTE** to generate synthetic samples for fraudulent transactions  
- Ensured balanced representation in training data  

### 4️⃣ Model Training
- Logistic Regression as baseline model  
- Standardized features using StandardScaler  
- Trained on resampled data  

### 5️⃣ Evaluation
- Metrics: **Accuracy, Precision, Recall, F1-score, ROC-AUC**  
- Visualizations: Confusion Matrix, ROC Curve, Precision-Recall Curve  
- Feature importance via coefficients  

---

## 📈 Results

The Logistic Regression model achieved:

- **Accuracy:** 78.29%  
- **Precision:** 31.96%  
- **Recall:** 99.94% ✅  
- **F1-Score:** 48.43%  
- **ROC-AUC:** 0.8882  

**Interpretation:**  
- Nearly all fraudulent transactions are detected (**high Recall**)  
- Some legitimate transactions are incorrectly flagged (**low Precision**)  
- This trade-off is common in fraud detection and acceptable when missing fraud is costly  

![Confusion Matrix](results/confusion_matrix.png)  
![ROC Curve](results/roc_curve.png)  



## 💡 Discussion

- **Precision vs Recall:** High Recall ensures most frauds are caught (reducing financial losses). Low Precision means more false positives, which may annoy users. Threshold tuning is important.  
- **Cost of errors:**  
  - False negatives → financial loss  
  - False positives → customer frustration  
- **Deployment:**  
  - Integrate into real-time transaction pipelines  
  - Monitor and retrain regularly  
  - Adjust thresholds according to risk strategy  
  - Use explainable AI for regulatory compliance  


## 🔮 Future Improvements

- Ensemble models (Random Forest, XGBoost)  
- Cost-sensitive learning  
- Graph-based fraud detection for transaction networks  
- Real-time detection system with API or streaming  



## 🗂 Folder Structure

```text
mobile-money-fraud-detection/
│
├── data/                  # Dataset files
├── notebooks/             # Jupyter notebooks
├── src/                   # Python scripts
├── models/                # Saved model files (.pkl)
├── results/               # Plots and evaluation metrics
├── requirements.txt       # Python dependencies
└── README.md              # Project overview

⚡ How to Run

# Clone the repository
git clone <your-repo-link>

# Install dependencies
pip install -r requirements.txt

# Run notebook
jupyter notebook notebooks/EDA.ipynb

🏆 Highlights

- ML applied to real-world fraud detection

- Handles imbalanced datasets with SMOTE

- Interpretable model using Logistic Regression

- Includes operational insights and deployment discussion


















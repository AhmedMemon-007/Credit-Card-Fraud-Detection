# 💳 Credit Card Fraud Detection & Analytics Dashboard

## 📌 Project Overview
Credit card fraud is a critical problem for financial institutions. The goal of this project is to **detect fraudulent credit card transactions** accurately so that customers are not charged for purchases they did not make.

This repository contains:
- End-to-end **machine learning modeling** for fraud detection
- **Evaluation using appropriate metrics** for imbalanced data
- **Power BI dashboard** for visual and business-friendly insights

---

## 📊 Dataset Information

**Source:**  
[Kaggle – Credit Card Fraud Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)

### Context
Credit card companies must be able to identify fraudulent transactions to prevent financial loss and protect customers.

### Content
- Transactions made by **European cardholders** in **September 2013**
- Covers **2 days** of transactions
- **284,807 total transactions**
- **492 fraud cases**
- Fraud rate: **0.172%** (highly imbalanced dataset)

### Features
- All features are **numerical**
- **V1 – V28**: PCA-transformed features (original features are confidential)
- **Time**: Seconds elapsed since the first transaction
- **Amount**: Transaction amount
- **Class**:
  - `1` → Fraud
  - `0` → Non-fraud

### Important Note on Evaluation
Due to extreme class imbalance:
- ❌ Accuracy is **not meaningful**
- ✅ **Area Under the Precision–Recall Curve (AUPRC)** is the recommended metric

---

## 🧠 Methodology

### 1. Data Preprocessing
- Scaled `Amount` feature
- Dropped `Time` (low predictive value)
- Stratified train–test split
- Handled class imbalance using **SMOTE** (training set only)

### 2. Models Trained
The following classification models were evaluated:
- Logistic Regression
- Naive Bayes
- Decision Tree
- Random Forest
- XGBoost

### 3. Evaluation Strategy
- **Model comparison:** AUPRC
- **Decision making:** Precision, Recall, F1-score at a fixed threshold
- **Interpretability:** Confusion matrices

---

## 📈 Results Summary

| Model               | AUPRC  |
|--------------------|--------|
| Random Forest      | **0.87** |
| XGBoost            | 0.85 |
| Logistic Regression| 0.72 |
| Decision Tree      | 0.42 |
| Naive Bayes        | 0.09 |

- **Random Forest** achieved the best overall performance
- High recall was prioritized to minimize missed fraud cases

---

## 📊 Power BI Dashboard

The Power BI dashboard provides:
- Model comparison using AUPRC
- Precision vs Recall trade-off visualization
- Interactive confusion matrices
- KPI cards for quick insights

### Files used for Power BI:
- `fraud_model_metrics_all.csv`
- `confusion_matrices_all_models.csv`
- `credi_card_dashboard.pbix`

---


---

## 🚀 How to Run
1. Clone the repository
2. Open `credit_card_fraud_detection.ipynb`
3. Run all cells to reproduce results
4. Open `credi_card_dashboard.pbix` in Power BI
5. Load the provided CSV files if prompted

---

## 📌 Key Takeaways
- Fraud detection is an **imbalanced classification problem**
- **AUPRC** is the correct evaluation metric
- Tree-based ensemble models outperform simpler classifiers
- Visualization bridges the gap between ML results and business understanding

---

## 👤 Author
**Muhammad Ahmed Memon**  
Computer Science | Machine Learning | Data Analytics

---

## 📜 License
This project is for **academic and educational purposes**.

---

## 📁 Repository Structure


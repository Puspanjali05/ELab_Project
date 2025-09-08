# ELab_Project

# Credit Card Fraud Detection using Machine Learning

## 📌 Introduction
Credit card fraud is a major issue in today’s digital economy, causing billions of dollars in financial losses worldwide. Detecting fraudulent transactions quickly and accurately is critical for both financial institutions and customers.  
This project builds a machine learning model to detect fraudulent credit card transactions by addressing the **class imbalance problem** using sampling techniques.

---

## 🎯 Objective
The main goals of this project are to:
- Accurately identify fraudulent transactions.
- Handle severe class imbalance in the dataset.
- Compare the effectiveness of **under-sampling** and **over-sampling** strategies.

---

## 📂 Dataset
- **Source:** [Kaggle – Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Records:** 284,807 transactions  
- **Features:**
  - `Time`: Seconds elapsed between each transaction.
  - `V1–V28`: Anonymized numerical features (derived from PCA).
  - `Amount`: Transaction amount.
  - `Class`: Target variable (0 = Normal, 1 = Fraud).
- **Class Distribution:**
  - Fraud cases ≈ **492 (0.17%)**
  - Genuine cases ≈ **284,315 (99.83%)**

---

## 🛠️ Data Preprocessing
1. **Data Cleaning:** Checked for missing values (none found).  
2. **Feature Scaling:** StandardScaler applied to `Amount` and `Time`.  
3. **Class Balancing:**
   - **Under-Sampling:** Reduced majority class (non-fraud) to match minority class.  
   - **Over-Sampling (SMOTE):** Increased fraud samples synthetically.

---

## 🤖 Modeling Approach
Machine learning models applied:
- Logistic Regression  
- Decision Tree Classifier  
- Random Forest Classifier  
- XGBoost Classifier  

**Train-Test Split:** 70% training, 30% testing  
**Evaluation Metrics:** Accuracy, Precision, Recall, F1-score, ROC-AUC  

---

## 📊 Results
### Without Sampling
- High Accuracy (>99%) but very poor Recall for fraud detection due to imbalance.  

### Under-Sampling
- Accuracy dropped (due to less data).  
- Recall improved but with higher false positives.  

### Over-Sampling (SMOTE)
- Balanced performance with high Recall and reasonable Precision.  
- **XGBoost** achieved the best results with ROC-AUC > **0.98**.  

**Key Finding:**  
➡️ Over-Sampling with advanced classifiers (Random Forest/XGBoost) provides the most reliable fraud detection system.

---

## 💡 Discussion
- **Under-Sampling:** Faster, but genuine transaction data is lost.  
- **Over-Sampling:** More computationally expensive but preserves data distribution.  
- **In fraud detection, Recall > Accuracy** since missing fraud (False Negatives) is more costly than false alarms.  

---

## ✅ Conclusion
- Machine learning can effectively detect fraudulent credit card transactions.  
- Handling class imbalance is **critical** for accuracy and reliability.  
- Best performing approach: **SMOTE + XGBoost**, with strong Recall and ROC-AUC values.  

---

## 🚀 Tech Stack
- Python 🐍  
- Pandas, NumPy  
- Scikit-learn  
- XGBoost  
- Matplotlib, Seaborn  

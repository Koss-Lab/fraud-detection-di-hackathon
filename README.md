
# 🕵️‍♂️ Credit Card Fraud Detection — DI Hackathon 2025

A data analysis & machine learning project developed for the **Developers Institute Hackathon (October 2025)**.  
The goal is to detect fraudulent credit-card transactions using data-driven techniques and machine-learning models.

---

## 🚀 Overview

Fraudulent transactions are **extremely rare** — less than 0.2 % of all transactions.  
This project demonstrates how to:

1. Explore and understand the data through **EDA (Exploratory Data Analysis)**  
2. Handle **imbalanced data** using **SMOTE**  
3. Train and evaluate several **classification models**:
   - Logistic Regression  
   - Random Forest  
   - XGBoost  
4. Tune decision thresholds to **maximize recall** (catch more frauds)  
5. Export model reports and feature-importance rankings for analysis

---

## 🧰 Tech Stack

| Category | Tools / Libraries |
|-----------|-------------------|
| Core | Python 3.10 + |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| ML & Evaluation | Scikit-learn, XGBoost, Imbalanced-Learn |
| Notebook & Reports | Jupyter Notebook / Google Colab |
| Environment | Virtualenv + pip (requirements.txt) |

---

## 📦 Dataset

**Source :** [Kaggle – Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)  
- 284 807 transactions (492 fraudulent)  
- 30 anonymized PCA features (V1–V28 + Time + Amount)  
- Target column `Class`: `0 = Legit`, `1 = Fraud`

Place the dataset file here:


fraud-detection-di-hackathon/data/creditcard.csv



---

## 🧠 Project Structure

```

fraud-detection-di-hackathon/
├── data/
│   └── creditcard.csv
├── notebooks/
│   └── fraud_analysis_di_hackathon.ipynb      ← Google Colab / Jupyter version
├── fraud_analysis_di_hackathon.py             ← main script (executable)
├── reports/
│   ├── model_summary.csv                      ← model metrics
│   ├── feature_importance_rf.csv              ← Random Forest importance
│   └── feature_importance_xgb.csv             ← XGBoost importance
├── requirements.txt
└── README.md

```

---

## ⚙️ Installation & Execution (Local)

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/Koss-Lab/fraud-detection-di-hackathon.git
cd fraud-detection-di-hackathon
```

### 2️⃣ Create & Activate a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate          # Mac/Linux
venv\Scripts\activate             # Windows
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

 🧩 If you’re on macOS and see an error with XGBoost (libomp):

```bash
brew install libomp
export DYLD_LIBRARY_PATH=/opt/homebrew/opt/libomp/lib:$DYLD_LIBRARY_PATH
```

### 4️⃣ Run the Script

```bash
python3 fraud_analysis_di_hackathon.py
```

This will:

* Load and analyze the dataset
* Balance it with SMOTE
* Train Logistic Regression, Random Forest & XGBoost
* Save results to `/reports/`
* Display evaluation metrics and plots

---

## 💻 Execution on Google Colab

If you prefer running it online:
👉 [**Open in Google Colab**](https://colab.research.google.com/drive/1gtHC7pGkNpZDpFUbTtoWx6FrIkW9R5DY?usp=sharing)

Steps :

1. Upload the dataset (`creditcard.csv`) when prompted.
2. Run all cells sequentially.
3. The notebook will automatically download the `/reports` CSV files when finished.

---

## 📈 Results & Insights

| Model                       | Precision | Recall |   F1 |  AUC |
| :-------------------------- | --------: | -----: | ---: | ---: |
| Logistic Regression (tuned) |      0.72 |   0.85 | 0.78 | 0.97 |
| Random Forest               |      0.72 |   0.86 | 0.79 | 0.98 |
| XGBoost                     |      0.50 |   0.86 | 0.63 | 0.98 |

**Interpretation :**

* All models achieved high AUC (≈ 0.98) → excellent discrimination between fraud / legit.
* Random Forest gave the best balance between precision and recall.
* Tuned Logistic Regression performed almost as well with lighter computation.

### Feature Importance

The most influential variables for detecting fraud were PCA features `V14`, `V17`, `V12`, `V10`, and `V4`.

---

## 🧮 Key Concepts

| Metric        | Meaning                                                  |
| ------------- | -------------------------------------------------------- |
| **Precision** | Among predicted frauds, how many are actually fraudulent |
| **Recall**    | Among all real frauds, how many were caught by the model |
| **F1 / F2**   | Balance between precision and recall (F2 → favor recall) |
| **AUC (ROC)** | Model’s overall ability to separate fraud vs non-fraud   |

---

## 📊 Generated Reports

Once executed, you’ll find in `/reports/` :

* `model_summary.csv` → comparative metrics for each model
* `feature_importance_rf.csv` → Random Forest top features
* `feature_importance_xgb.csv` → XGBoost top features

Example :

```
reports/
├── model_summary.csv
├── feature_importance_rf.csv
└── feature_importance_xgb.csv
```

---


## 👨‍💻 Author

**Ariel Kossmann**
Developers Institute — Tel Aviv 🇮🇱

---


Here is a clean **copy-paste ready README.md** version:

---

# 💳 Credit Card Default Prediction

## 📌 Project Overview

This project analyzes the **UCI Credit Card Default Dataset** to predict whether a customer will default on their credit card payment next month.

The dataset contains 30,000 customer records and 25 financial & demographic features including credit limit, billing history, repayment status, and payment amounts.

The objective of this project is to:

* Perform exploratory data analysis (EDA)
* Handle outliers and preprocessing
* Identify key risk drivers
* Build predictive machine learning models
* Optimize model performance

---

## 📊 Dataset Information

* Total Records: 30,000
* Final Records After Cleaning: 27,283
* Features: 24 (after preprocessing)
* Target Variable: DEFAULT_PAY (1 = Default, 0 = No Default)
* Default Rate: 22.12%
* No missing values
* No duplicate records

---

## 🔎 Exploratory Data Analysis Insights

### Credit Limit (LIMIT_BAL)

* Most users have limits below 300,000.
* Customers with very high limits rarely default.
* 600,000 selected as threshold to retain low-risk high-limit users.

### Billing Amounts (BILL_AMT1–6)

* Majority between 0–200,000.
* Higher bill amounts are mostly associated with non-defaulters.
* Some negative values indicate refunds or overpayments.

### Payment Amounts (PAY_AMT1–6)

* Most payments are below 20,000.
* Defaulters tend to make very low payments.
* Higher payments correlate with lower default risk.

### Repayment Status (PAY_1–PAY_6)

* Strongest predictors in the dataset.
* Higher delay values significantly increase default probability.
* Early repayment behavior is a powerful risk signal.

### Demographics

* Younger customers (<35) show higher default rates.
* Education and marital status have moderate predictive value.
* Gender is not a dominant standalone predictor.

---

## 🧹 Data Cleaning & Preprocessing

* Removed extreme outliers:

  * LIMIT_BAL > 600,000
  * BILL_AMT > 300,000
  * PAY_AMT > 50,000 (60,000 for PAY_AMT6)

* Removed invalid category values:

  * EDUCATION = 0
  * MARRIAGE = 0

* Applied:

  * StandardScaler to numerical features
  * OneHotEncoder to categorical features
  * L2 Regularization for Logistic Regression
  * PCA for ensemble models

Final dataset retained 27,283 records, ensuring strong data coverage without excessive data loss.

---

## 📈 Correlation Insights

* Strong multicollinearity among:

  * PAY_X features
  * BILL_AMT features

* Regularization used to stabilize coefficients.

* PCA applied in ensemble models to reduce dimensionality impact.

---

## 🤖 Models Implemented

### Logistic Regression (L2 Regularized)

* Training Accuracy: 80.25%
* Test Accuracy: 80.58%

### Random Forest (Optuna Tuned + PCA)

* Best Cross-Validation Accuracy: 81.46%

### XGBoost (Optuna Tuned + PCA)

* Best Cross-Validation Accuracy: ~80.96%

---

## 🛠 Technologies Used

* Python
* Pandas & NumPy
* Matplotlib & Seaborn
* Scikit-learn
* Optuna
* XGBoost

---

## 🎯 Business Impact

This model can support:

* Credit risk scoring
* Default prediction systems
* Loan approval decisions
* Customer risk segmentation
* Early warning systems

Key Insight: Repayment history and payment behavior are the strongest drivers of credit default risk.

---

## 🚀 Future Improvements

* Optimize for ROC-AUC instead of accuracy
* Implement SHAP feature importance analysis
* Add class imbalance handling (SMOTE)
* Deploy as API (FastAPI/Flask)
* Build interactive dashboard

---

## 👤 Author

Harshith Reddy
Data Scientist | Machine Learning Engineer
Email: [harshithreddymr25@gmail.com](mailto:harshithreddymr25@gmail.com)


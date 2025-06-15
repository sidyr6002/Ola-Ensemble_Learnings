# 📊 Ola Driver Attrition Prediction (Ensemble Learning)

**Predicting driver churn to help Ola retain its workforce through data-driven strategies leveraging ensemble methods.**

---

## 🎯 Problem Statement

Driver churn is one of the most significant operational challenges for Ola—high turnover not only increases recruitment costs but also affects service quality and driver morale. This project aims to:

- Predict whether a driver will leave the company in a future period.
- Identify key factors driving attrition.
- Provide recommendations to improve driver retention.

---

## 📌 Dataset Overview

Monthly driver-level data spanning 2019–2020:

| Feature                  | Description                                                            |
|--------------------------|------------------------------------------------------------------------|
| `Driver_ID`              | Unique identifier                                                      |
| `MMMM-YY`                | Reporting month/year                                                   |
| `Age`, `Gender`, `City`, `Education_Level` | Demographic variables                                       |
| `Income`                 | Avg. monthly driver income                                             |
| `Date Of Joining`, `LastWorkingDate` | Tenure metrics                                            |
| `Grade`                  | Driver performance grade                                               |
| `Total Business Value`   | Business generated, with negatives indicating refunds or cancellations |
| `Quarterly Rating`       | Driver ratings from 1 (bad) to 5 (excellent)                           |

---

## 🛠️ Methodology

1. **Exploratory Data Analysis (EDA)**
   - Identified missing values, skewed distributions, and feature trends.
2. **Data Preprocessing**
   - KNN imputation for missing values.
   - Feature engineering: tenure, cancellation/refund ratios, income delta.
   - Standardization and categorical encoding.
   - SMOTE to handle class imbalance.
3. **Model Building**
   - **Bagging**: Random Forest
   - **Boosting**: LightGBM
4. **Model Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1-score
   - Confusion Matrix & ROC Curve visualizations
5. **Insights & Recommendations**
   - Drivers with frequent cancellations and no income growth are high-risk.
   - Males churn more than females.
   - Ratings and refund behavior strongly influence churn.

---

## 📈 Model Performance

### 🪵 Bagging (Random Forest)

- **Overall Accuracy**: **95%**
- **Class 0 (Negative - Driver Will Leave)**  
  - Precision: **90%**  
  - Recall: **97%**  
  - F1-Score: **93%**
- **Class 1 (Positive - Driver Will Stay)**  
  - Precision: **98%**  
  - Recall: **95%**  
  - F1-Score: **97%**
- **Macro Average**  
  - Precision: **94%**, Recall: **96%**, F1-Score: **95%**
- **Weighted Average**  
  - Precision: **96%**, Recall: **95%**, F1-Score: **95%**

> 🔍 Excellent generalization and robustness, especially in classifying churned drivers.

---

### ⚡ Boosting (LightGBM)

- **Overall Accuracy**: **96%**
- **Class 0 (Negative - Driver Will Leave)**  
  - Precision: **90%**  
  - Recall: **97%**  
  - F1-Score: **93%**
- **Class 1 (Positive - Driver Will Stay)**  
  - Precision: **99%**  
  - Recall: **95%**  
  - F1-Score: **97%**
- **Macro Average**  
  - Precision: **94%**, Recall: **96%**, F1-Score: **95%**
- **Weighted Average**  
  - Precision: **96%**, Recall: **96%**, F1-Score: **96%**

> 🚀 LightGBM slightly outperforms bagging in accuracy and precision, making it a top choice for deployment.

---

## 💡 Business Recommendations

- Offer driver incentives tied to cancellation/refund behavior.
- Gender-based churn insights suggest the need for targeted retention programs.
- Monitor quarterly ratings and reward consistently high-performing drivers.
- Set up churn-risk alerts using model predictions.

---

## 🔧 Future Improvements

* Add hyperparameter tuning (Grid Search / Optuna).
* Incorporate temporal features using rolling averages.
* Add SHAP/LIME for explainable AI insights.
* Build automated retraining & dashboard for production use.


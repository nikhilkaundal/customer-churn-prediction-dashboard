# 📊 Customer Churn Prediction & Retention Dashboard

An end-to-end machine learning project that predicts customer churn risk for a telecom company and translates those predictions into an interactive, business-ready Power BI dashboard — complete with revenue-impact analysis, a discount-impact simulator, and per-customer drill-through profiles.

---

## 🎯 Problem Statement

Customer acquisition costs far exceed retention costs. This project identifies **which customers are likely to churn, why, and how much revenue is at stake** — giving a business team the tools to act before a customer leaves, not after.

---

## 📈 Key Results

| Metric | Value |
|---|---|
| Baseline churn rate | 26.5% |
| Annualized revenue at risk | $2.51M |
| Model recall (SMOTE-balanced) | 80% |
| ROC-AUC | 0.846 |
| Customers analyzed | 7,043 |

---

## 🔑 Key Business Insights

- **Contract type is the strongest churn driver** — month-to-month customers churn at **42.7%**, vs. **2.8%** for two-year contracts (~15x difference).
- **Tenure matters most in the first year** — churn probability is highest for customers with 0–12 months tenure and drops sharply after.
- **Fiber optic internet customers** show elevated churn risk compared to DSL or no-internet customers.
- Four actionable customer segments were identified via K-Means clustering: *Loyal Low-Spenders, High-Risk High-Spenders, Loyal High-Spenders,* and *New At-Risk* customers — each requiring a different retention strategy.

---

## 🛠️ Tech Stack

- **Python** — pandas, NumPy, scikit-learn, imbalanced-learn (SMOTE)
- **Machine Learning** — Logistic Regression, Random Forest, K-Means clustering
- **Power BI** — DAX measures, What-If parameters, drill-through pages, decomposition tree, conditional formatting

---

## 🧠 Methodology

**1. Data Cleaning & Feature Engineering**
- Handled missing values in `TotalCharges`
- Engineered `tenure_group`, `charges_ratio`, and `service_count` features
- One-hot encoded categorical variables

**2. Model Training & Evaluation**
- Trained and compared Logistic Regression and Random Forest
- Addressed class imbalance (26.5% churn) using **SMOTE**, prioritizing **recall** over raw accuracy — a missed churner costs more than a false alarm
- Achieved 80% recall and 0.846 ROC-AUC on the SMOTE-balanced model

**3. Customer Segmentation**
- Applied K-Means clustering (tenure, monthly charges, churn probability) to group customers into 4 actionable segments

**4. Business Translation**
- Calculated per-customer and total **annualized revenue at risk**
- Built a Power BI dashboard with:
  - KPI overview (churn rate, revenue at risk, at-risk customer count)
  - Contract-type and tenure-based churn breakdowns
  - A **discount-impact simulator** (What-If parameter) to model retention-offer ROI
  - A **drill-through page** showing individual customer risk profiles
  - Conditional-formatted risk table (High/Medium/Low)

---
## 📁 Repository Structure

```
customer-churn-prediction/
├── README.md
├── data/
│   ├── telco_churn.csv
│   └── cleaned_churn_data.csv
├── notebooks/
│   ├── 01_data_cleaning_feature_engineering.ipynb
│   └── 02_model_training.ipynb
├── dashboard/
│   ├── churn_dashboard.pbix
│   └── screenshots/
│       ├── main_dashboard.png
│       └── drill_through.png
└── requirements.txt
```

---

## 🖼️ Dashboard Preview

![Main Dashboard](dashboard/screenshots/main_dashboard.png)

![Drill-Through View](dashboard/screenshots/drill_through.png)

---

## 🚀 What-If Simulation

An interactive discount slider lets a business user simulate: *"If we offer a 15% discount to at-risk customers, how much does projected churn drop?"* — connecting a data science output directly to a business decision.

---

## 📌 Future Improvements

- Incorporate real timestamped churn events for time-series trend analysis
- Add SHAP-based explainability for individual predictions
- Deploy the model as a live API for real-time scoring

---

## 👤 Author

**Nikhil Kaundal**
[GitHub](https://github.com/nikhilkaundal) • [Portfolio](https://nikhilkaundal.space)

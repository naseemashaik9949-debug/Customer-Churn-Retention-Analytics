# Customer Churn & Retention Analytics

## 1. Business Problem

ABC Telecom is experiencing customer churn and needs to understand the customer characteristics and service patterns associated with customers leaving the company.

This project analyzes customer demographics, contract types, internet services, payment methods, tenure, and charges to identify high-churn customer segments. Python, Oracle SQL, and Power BI are used to clean data, validate results, explore churn patterns, and present insights that can support customer retention strategies.

## 2. Project Objectives

- Measure overall customer churn and retention rates.
- Identify customer segments associated with higher churn.
- Analyze churn across contract types, tenure groups, internet services, and payment methods.
- Compare monthly charges between churned and retained customers.
- Identify high-churn customer segments and retention opportunities.
- Develop actionable recommendations to support retention decisions.

## 3. Tools and Technologies

- **Python:** Pandas, NumPy, data profiling, data cleaning, and exploratory data analysis (EDA).
- **SQL:** Oracle SQL, aggregations, data validation, ETL, and data reconciliation.
- **Power BI:** DAX measures, KPI cards, interactive slicers, dashboards, and visualizations.

## 4. Dataset

The project uses the IBM Telco Customer Churn dataset, containing 7,043 customer records and 21 columns covering customer details, subscribed services, contracts, billing, tenure, and churn status.

- **Source:** [IBM Telco Customer Churn Dataset — Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Target variable:** `Churn`
- **Analysis focus:** Churn, retention, service usage, contracts, tenure, and billing characteristics.

## 5. Data Cleaning and Preparation

- Inspected data types, missing values, and duplicate records using Python.
- Converted `TotalCharges` from text to a numeric data type.
- Identified 11 blank `TotalCharges` values associated with customers whose tenure was zero; preserved them as missing values.
- Checked for duplicate customer IDs and duplicate records.
- Validated tenure and monthly charge values.
- Exported the cleaned dataset as `telco_customer_churn_cleaned.csv`.
- Reconciled record counts and key aggregate values across Python and Oracle SQL.

## 6. SQL Analysis

Oracle Database 21c XE was used for data validation, ETL processing, and business-focused analysis.

- Validated customer counts, missing values, duplicate IDs, and churn counts.
- Analyzed churn across contract types, tenure groups, internet services, payment methods, and customer characteristics.
- Identified high-churn segments using combined customer and service attributes.
- Reconciled record counts and aggregate values between ETL and final tables.

## 7. Power BI Dashboard

The report contains three pages:

### Executive Overview

- Displays total customers, churned customers, retained customers, churn rate, and retention rate.
- Visualizes churn and retention distribution.
- Compares customer distribution by contract type and tenure group.
- Includes contract, internet service, and payment method slicers.
- Includes a Reset Filters button and a dynamic chart title.

### Churn Drivers Analysis

- Examines churn across contract types, internet services, payment methods, and tenure groups.
- Compares churn rates across customer segments.
- Highlights segments that warrant further investigation.

### Retention Opportunities

- Focuses on customers with month-to-month contracts, fiber optic internet, and electronic-check payments.
- Displays segment size, churned customers, retained customers, and churn rate.
- Presents practical retention recommendations.

## 8. Key Findings

- **Overall churn:** 1,869 of 7,043 customers churned, giving a churn rate of 26.54%.
- **Contract type:** Month-to-month customers had a churn rate of 42.71%, compared with 11.27% for one-year contracts and 2.83% for two-year contracts.
- **Tenure:** Customers with 0–12 months of tenure had a churn rate of 47.44%.
- **Internet service:** Fiber optic customers had a churn rate of 41.89%.
- **Payment method:** Customers using electronic checks had a churn rate of 45.29%.
- **Monthly charges:** Average monthly charges were $74.44 for churned customers and $61.27 for retained customers.
- **High-risk segment:** Among 1,307 customers with month-to-month contracts, fiber optic internet, and electronic-check payments, 789 churned and 518 were retained. The segment's churn rate was 60.37%.

These findings describe observed associations and do not establish that any single characteristic causes churn.

## 9. Business Recommendations

- Introduce onboarding support and early check-ins for customers during their first 12 months.
- Investigate why month-to-month customers leave more frequently and explain longer-term plan benefits where appropriate.
- Review pricing, reliability, installation experience, and customer satisfaction among fiber optic customers.
- Investigate possible billing or payment concerns among electronic-check users.
- Assess customer awareness of online security and technical support services.
- Monitor churn rates over time to evaluate retention initiatives.

These recommendations should be tested and evaluated using subsequent customer data.

## 10. Project Structure
Customer-Churn-Retention-Analytics/
├── Data/
│   ├── telco_customer_churn_cleaned.csv
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── Documentation/
│   └── README.md
├── PowerBI/
│   └── Customer Churn & Retention Analysis.pbix
├── Python/
│   ├── 01_Data_Profiling.ipynb
│   ├── 02_Data_Cleaning.ipynb
│   └── 03_Churn_Analysis.ipynb
└── SQL/
    └── connection_creation.sql

 Customer Churn & Retention Analytics

1. Business Problem
ABC Telecom is experiencing customer churn and needs to understand the customer characteristics and service patterns associated with customers leaving the company.
This project analyzes customer demographics, contract types, internet services, payment methods, tenure, and charges to identify high-churn customer segments. Python, SQL, and Power BI are used to clean the data, validate the results, explore churn patterns, and present actionable insights that can support customer retention strategies.

2. Project Objectives
- Measure overall customer churn and retention rates.
- Identify customer segments associated with higher churn.
- Analyze churn patterns across contract types, tenure groups, internet services, and payment methods.
- Compare monthly charges between churned and retained customers.
- Identify high-risk customer segments and evaluate their retention opportunities.
- Develop actionable recommendations to support customer retention decisions.

3. Tools and Technologies
- Python: Pandas, NumPy, data profiling, data cleaning, exploratory data analysis (EDA).
- SQL: Oracle SQL, joins, subqueries, aggregations, data validation, and ETL data reconciliation.
- Power BI: Interactive dashboards, KPI cards, slicers, DAX measures, and data visualization.
- Excel: Data inspection and basic data analysis.
- Documentation: Markdown and GitHub-ready project documentation.

4. Dataset
This project uses the IBM Telco Customer Churn dataset, which contains customer information, subscribed services, contract details, billing information, tenure, and churn status.

- Source: IBM Telco Customer Churn Dataset — Kaggle (https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- Original records: 7,043 customers
- Original columns: 21
- Target variable: Churn
- Analysis focus: Customer churn, retention patterns, service usage, contract types, tenure, and billing characteristics.
The dataset was cleaned and prepared before being used for Python analysis, Oracle SQL processing, and Power BI visualization.

5. Data Cleaning and Preparation
- Inspected the dataset structure, column data types, missing values, and duplicate records using Python.
- Converted 'TotalCharges' from text to a numeric data type.
- Identified 11 blank 'TotalCharges' values associated with customers whose tenure was zero; preserved them as missing values rather than replacing them with zero.
- Checked for duplicate customer IDs and duplicate records.
- Validated tenure and monthly charge values.
- Saved the cleaned dataset as 'telco_customer_churn_cleaned.csv' for downstream analysis.
- Reconciled the cleaned data across Python and Oracle SQL to verify record counts and key aggregate values.

6. SQL Analysis
Oracle SQL was used to validate the cleaned dataset and perform business-focused churn analysis.
- Loaded customer data into Oracle Database 21c XE.
- Used staging and final tables to organize the data-processing workflow.
- Converted blank 'TotalCharges' values to 'NULL' during ETL processing.
- Validated customer counts, missing values, duplicate customer IDs, and churn counts.
- Analyzed churn across contract types, tenure groups, internet services, payment methods, and customer characteristics.
- Identified high-churn customer segments using combined customer and service attributes.
- Reconciled record counts and key aggregate values between the ETL and final tables.
Database environment: Oracle Database 21c XE, using the `XEPDB1` service.
The SQL analysis helped verify data quality and establish the findings presented in the Power BI dashboard.

7. Power BI Dashboard
The Power BI report contains three interactive pages designed to communicate customer churn patterns and retention opportunities.
  1. Executive Overview
- Displays total customers, churned customers, retained customers, churn rate, and retention rate.
- Visualizes churn and retention distribution.
- Compares customer distribution by contract type and tenure group.
- Provides slicers for contract, internet service, and payment method.
- Includes a Reset Filters button and a dynamic chart title.

  2. Churn Drivers Analysis
- Examines churn patterns across contract types, internet services, payment methods, and tenure groups.
- Compares churn rates across important customer segments.
- Highlights customer groups that warrant further investigation.

  3. Retention Opportunities
- Focuses on customers with month-to-month contracts, fiber optic internet, and electronic-check payments.
- Displays segment size, churned customers, retained customers, and churn rate.
- Presents practical recommendations for customer retention.

Technical implementation: DAX measures, interactive slicers, KPI cards, charts, conditional visual formatting, and report-level design consistency.

8. Key Findings
- Overall churn: 1,869 of 7,043 customers churned, resulting in a churn rate of 26.54%.
- Contract type: Month-to-month customers had a churn rate of 42.71%, compared with 11.27% for one-year contracts and 2.83% for two-year contracts.
- Tenure: Customers with 0–12 months of tenure had the highest churn rate among the analyzed tenure groups, at 47.44%.
- Internet service: Fiber optic customers had a churn rate of 41.89%.
- Payment method: Customers using electronic checks had a churn rate of 45.29%.
- Monthly charges: Average monthly charges were $74.44 for churned customers and $61.27 for retained customers.
- High-risk segment: Customers with month-to-month contracts, fiber optic internet, and electronic-check payments numbered 1,307. Of these, 789 churned and 518 were retained, giving the segment a churn rate of 60.37%.
These findings describe observed associations in the dataset and do not establish that any single characteristic causes customers to churn.

9. Business Recommendations
Based on the observed churn patterns, ABC Telecom could consider the following actions:
- Improve early-tenure retention: Introduce onboarding support and early check-ins for customers during their first 12 months.
- Review contract flexibility: Investigate why month-to-month customers leave more frequently and communicate the benefits of longer-term plans where appropriate.
- Investigate fiber optic service experience: Review pricing, reliability, installation experience, and customer satisfaction among fiber optic users.
- Review electronic-check payment experience: Understand whether payment friction or billing concerns contribute to dissatisfaction.
- Promote support services: Assess whether customers are aware of available online security, technical support, and other service options.
- Monitor retention outcomes: Track churn rates by customer segment over time to evaluate the effectiveness of retention initiatives.
These are recommendations for further investigation and testing, not guaranteed solutions. Their effectiveness should be evaluated using subsequent customer data.

10. Project Structure

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



# Data Dictionary — Customer Churn & Revenue Risk Dashboard

## Table: Customer_Churn (fact table)

| Field | Type | Description |
|---|---|---|
| CustomerID | Text | Unique identifier for each customer |
| Contract | Text | Contract type: Month-to-month, One year, Two year |
| Tenure_Months | Whole Number | Number of months the customer has been with the company |
| Tenure_Group | Text (derived) | Binned tenure: 0–12, 13–24, 25–48, 49–72 months |
| Payment_Method | Text | Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic) |
| Monthly_Charges | Decimal | Monthly revenue from the customer |
| Total_Charges | Decimal | Cumulative revenue from the customer to date |
| Churn_Status | Text (Yes/No) | Whether the customer has churned |
| Churn_Reason | Text | Stated reason for churn (where available) |
| Customer_Risk_Category | Text (derived) | Low / Medium / High / Critical, based on tenure, contract, and payment method |

## Table: Data_Dictionary
Reference table describing each field above — used for in-report documentation and onboarding new report viewers.

## Table: Data_Quality
Tracks completeness and validation flags for key fields (e.g., missing Churn_Reason, invalid Tenure_Months) to support data-quality transparency in the report.

## Key DAX Measures

| Measure | Logic (conceptual) |
|---|---|
| Churn Rate | Churned Customers ÷ Total Customers |
| Retention Rate | 1 − Churn Rate |
| Revenue at Risk % | Revenue from Churned Customers ÷ Total Monthly Revenue |

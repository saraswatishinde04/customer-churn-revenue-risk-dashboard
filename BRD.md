# Business Requirements Document (BRD)
## Customer Churn & Revenue Risk Analysis Dashboard

| | |
|---|---|
| **Prepared by** | Saraswati Sarjerao Shinde |
| **Role** | Data Analyst (Project Author) |
| **Document Version** | 1.0 |
| **Date** | September 2026 |
| **Status** | Final |

---

## 1. Project Overview
Subscription-based businesses lose recurring revenue when customers churn, often without early warning. This project defines the requirements for a Power BI dashboard that identifies churn patterns, segments customers by risk, and quantifies the revenue impact of churn — enabling the business to act on retention proactively rather than reactively.

## 2. Business Objectives
- Reduce revenue loss from customer churn by identifying at-risk customers before they leave.
- Provide a single, self-serve dashboard for leadership to monitor churn and retention KPIs without requesting ad-hoc reports.
- Identify the specific drivers of churn (contract type, tenure, payment method, stated reason) to inform targeted retention campaigns.

## 3. Scope

**In Scope**
- Analysis of historical customer data: demographics, contract type, tenure, payment method, charges, and churn status.
- Calculation of churn rate, retention rate, and revenue-at-risk percentage.
- Customer risk segmentation (Low / Medium / High / Critical).
- Root-cause breakdown of churn by contract type, tenure group, payment method, and stated churn reason.
- A single executive-facing Power BI report page ("Executive Overview").

**Out of Scope**
- Predictive/ML-based churn modeling (this project is descriptive/diagnostic analytics, not predictive).
- Real-time data refresh or live database connection (static dataset for this version).
- Customer-level action tracking (e.g., CRM integration for retention outreach).

## 4. Stakeholders

| Stakeholder | Interest |
|---|---|
| Business / Leadership | High-level churn and revenue-risk visibility |
| Customer Retention Team | Identifying which customer segments to target |
| Data Analyst (self) | Deliver an accurate, self-serve reporting tool |

## 5. Data Requirements

| Field | Description |
|---|---|
| Customer ID | Unique identifier per customer |
| Contract Type | Month-to-month, One year, Two year |
| Tenure (Months) | Length of customer relationship, grouped into bands (0–12, 13–24, 25–48, 49–72) |
| Payment Method | Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic) |
| Monthly / Total Charges | Revenue contribution per customer |
| Churn Status | Whether the customer has churned (Yes/No) |
| Churn Reason | Stated reason for churn, where available |
| Customer Risk Category | Derived field: Low / Medium / High / Critical |

Data is structured across three tables: `Customer_Churn` (fact table), `Data_Dictionary` (field definitions/reference), and `Data_Quality` (validation/completeness checks).

## 6. Functional Requirements

| ID | Requirement |
|---|---|
| FR-1 | Dashboard must display total customers, churned customers, churn rate, retention rate, and revenue-at-risk % as headline KPIs. |
| FR-2 | Dashboard must break down churn rate by contract type. |
| FR-3 | Dashboard must break down churn rate by tenure group. |
| FR-4 | Dashboard must break down churn rate by payment method. |
| FR-5 | Dashboard must show churned customers by stated churn reason. |
| FR-6 | Dashboard must segment total customers by risk category (Low/Medium/High/Critical). |
| FR-7 | All monetary and percentage values must include on-chart data labels for readability. |

## 7. Key Performance Indicators (Success Metrics)
- **Churn Rate** — % of total customers who have churned.
- **Retention Rate** — % of customers retained (1 − churn rate).
- **Revenue at Risk %** — share of total monthly revenue attributable to churned/at-risk customers.
- **Risk Segment Distribution** — proportion of customers in each risk tier.

## 8. Assumptions & Constraints
- Dataset is a point-in-time snapshot; it does not reflect real-time churn events.
- Churn reason data is self-reported and may be incomplete for some customers (tracked via the `Data_Quality` table).
- Risk category thresholds are defined based on tenure, contract type, and payment method, and may need recalibration if the underlying customer base changes.

## 9. Deliverables
- Power BI dashboard file (`.pbix`) — Executive Overview page.
- This BRD document.
- Supporting data dictionary.
- Exported dashboard screenshot(s) for portfolio/reporting use.

## 10. Approval
This BRD represents a self-directed portfolio project completed to demonstrate business-analyst and data-analyst competencies, including requirements definition, data modeling, DAX measure design, and dashboard development.

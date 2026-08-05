# Telco Customer Churn Analysis
*Analyzing 7,043 telecom customer accounts to understand why customers churn and what the business can do to reduce a 26.5% churn rate.*

---

## ⚙️ Project Type Flags
> *Check what applies. This helps reviewers and collaborators understand the nature of the work at a glance. Delete this block before publishing.*

- [x] Exploratory Data Analysis (EDA)
- [ ] SQL Analysis / Querying
- [x] Dashboard / Data Visualization
- [ ] Data Pipeline / ETL
- [ ] Predictive Modelling / Machine Learning
- [ ] Data Cleaning / Wrangling
- [ ] End-to-End (multiple of the above)
- [ ] Other: ___________

---

## Table of Contents
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objectives)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Analysis & Metrics](#6-analysis--metrics)
7. [Key Insights](#7-key-insights)
8. [Recommendations](#8-recommendations)
9. [Assumptions & Limitations](#9-assumptions--limitations)
10. [Deliverables](#10-deliverables)
11. [Author](#11-author)

---

## 1. Project Overview
**Context:** The company is losing roughly 1 in 4 customers to churn each cycle - a direct hit to recurring revenue that costs far more to replace than to retain.

**Problem Statement:** Why are customers leaving the company, which segments respond worst, which factors drive churn most and what can the business change to reduce it?

**Approach:** Built a Power BI dashboard on the Telco Customer Churn dataset (7,043 account-level records) covering demographics, subscribed services, billing, and churn outcome, then analyzed churn patterns by contract type, tenure, service type, and payment method.

**Outcome:** Identified that churn is concentrated in a small set of identifiable segments - month-to-month contracts, early-tenure customers, fiber optic subscribers, senior citizens and electronic check payers - enabling targeted rather than broad retention efforts.

---

## 2. Objectives

**Primary Objective:** Identify why customers are leaving the company and which factors drive churn most.

**Secondary Objective 1:** Determine which customer segments respond worst to churn - and which stay loyal.

**Secondary Objective 2:** Identify which contract, service, and billing factors drive churn most.

**Secondary Objective 3:** Recommend what the business can change to reduce churn and protect revenue.

---

## 3. Project Scope & Tools

### Scope

| Dimension | Details |
|-----------|---------|
| **In Scope** | 7,043 customer accounts covering demographics, contract type, services subscribed, billing details, and churn outcome |
| **Out of Scope** | Customer support interaction logs, marketing campaign response data |
| **Time Period** | Snapshot dataset (no time-period avaiable) |
| **Granularity** | One row per customer account |


### Tools & Technologies
| Category | Tool(s) Used |
|----------|-------------|
| Data Analysis | Power BI |
| Dashboard Design | Power BI (interactive dashboard) |
| Presentation | PowerPoint (slide deck summarizing key insights and recommendations) |
| Documentation | Markdown, GitHub |

---

## 4. Repository Structure

```
Telecom-Churn-Analysis/
│
├── data/
│   └── raw/                  # Original Telco Customer Churn dataset (not hosted here - see Data Source)
│
├── power-bi/                 # Power BI dashboard file (.pbix)
│
├── reports/                  # Slide deck summarizing findings and recommendations
│
├── visuals/                  # Power BI dashboard screenshots
│
├── README.md                 # You are here
└── project_metadata.yml      # Project metadata

```

## Data Source 

This project uses the [Telco Customer Churn dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) (7,043 customer records). Download the CSV and place it in data/raw/ to reproduce this analysis.

---

## 5. Data Workflow

1. **Source:** Telco Customer Churn dataset (7,043 account-level records) covering demographics, subscribed services, billing and churn outcome.

2. **Ingestion:** Dataset loaded into Power BI for analysis and dashboard building.

3. **Cleaning:** In Power Query, converted Total Charges from text to numeric, replaced 11 blank Total Charges values (customers with zero tenure) with 0, recorded Senior Citizen from 0/1 to NO/Yes for readability, removed duplicate customer records and standardized column headers to Title case.

4. **Transformation:** Calculated churn rate, average tenure, and average monthly charges as summary metrics; segmented customers by contract type, internet service, payment method and senior citizen status.

5. **Analysis:** Compared churn rates across contract type, tenure, service type, payment method, and demographic segments using Power BI visuals.

6. **Output:** An interactive Power BI dashboard and a slide deck summarizing key findings and recommendations for stakeholders.

---

## 6. Analysis & Metrics

### Analytical Approach

This was primarily exploratory and diagnostic - segmenting the customer base by contract, service, billing, and demographic attributes to identify which factors are most associated with churn, in order to guide targeted retention recommendations.

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|--------|---------------------------|-----------------|
| `Churn Rate` | % of customers who left the company | Core measure of customer attrition |
| `Average Tenure` | Average number of months a customer has stayed | Indicates typical customer lifespan and retention risk points |
| `Average Monthly Charges` | Average amount billed to customers per month | Helps assess whether pricing correlates with churn |
| `Churn Rate by Segment` | Churn % broken down by contract type, service type, payment method, and demographics | Identifies which customer segments are highest-risk |

### Methods Used

- Segmentation / group comparison by contract type, internet service, payment method, tenure, and senior citizen status
- Descriptive statistics - churn rate, average tenure, average monthly charges
- Comparative analysis between churned and retained customers (e.g., monthly charge gap)

---

## 7. Key Insights

**Insight 1: Contract type is the #1 driver of churn*
Month-to-month customers churn at 40%+, compared to ~10% for one-year contracts and under 5% for two-year contracts. This suggests contract flexibility, while attractive to customers, comes at a major retention cost.

**Insight 2: Churn is front-loaded by tenure*
New customers churn at 50–60% within their first months, with the rate falling steadily as tenure grows. This points to the earliest months of the customer relationship as the highest-risk window.

**Insight 3: Fiber optic customers churn most*
Fiber optic churns at ~40%, far above DSL (~19%) and no-internet customers (~7%) - suggesting pricing or service quality issues specific to fiber optic offerings.

**Insight 4: Churned customers pay more and skew senior/manual-payment*
Churned customers average $74.44/month vs. $61.27 for retained customers. Senior citizens churn at ~40% (roughly double non-seniors), and electronic check has the highest churn rate of any payment method - together pointing to price sensitivity and friction in manual payment processes as compounding risk factors.

---

## 8. Recommendations

| Priority | Recommendation | Based On | Suggested Owner |
|----------|-----------------|----------|------------------|
| High | Incentivize longer contracts - offer discounts or perks for switching from month-to-month to annual plans | Insight 1 - contract type is the top churn driver | Retention / Marketing team |
| High | Launch an early-tenure retention program with proactive onboarding and milestone offers in a customer's first 10 months | Insight 2 - churn is front-loaded by tenure | Customer Success team |
| Medium | Review fiber optic pricing and service quality to address its outsized churn rate | Insight 3 - fiber optic churns highest | Product / Service Quality team |
| Medium | Encourage automatic payment methods over electronic check through small incentives, and create a senior citizen support track with simplified plans | Insight 4 - payment method and senior status compound risk | Customer Success / Billing team |

---

## 9. Assumptions & Limitations

### Assumptions
- The dataset was assumed to represent a complete and accurate snapshot of customer accounts at the time of extraction, with no independent validation against the company's live billing system.
- Churn was treated as a fixed outcome (Yes/No) for each customer, without visibility into churn timing relative to the snapshot date.

### Limitations
- This is a single-point-in-time snapshot rather than time-series data, so trends in churn rate over time cannot be assessed - only cross-sectional patterns.
- No customer support interaction or complaint data was available, limiting the ability to link service issues directly to churn.
- The dataset doesn't include reasons customers gave for leaving, so drivers are inferred from correlation with account attributes, not directly confirmed causes.

---

## 10. Deliverables

| Deliverable | Description | Location |
|-------------|--------------|----------|
| Power BI dashboard | Interactive dashboard analyzing churn by contract, tenure, service, and payment method | power-bi/Telecom_Churn_Dashboard.pbix |
| Dashboard screenshots | Static images of the dashboard for quick viewing | visuals/Telecom Churn Dashboard pic
| Slide deck | Presentation summarizing business problem, findings, and recommendations | reports/Telco_Churn_Presentation.pptx |

---

## 11. Author

**Vivian Okwara**

Data Analyst | Lagos Nigeria 

- 🔗 https://Linkedin.com/in/okwara-vivian
- 💼 https://Vivian-Portfolio.github.io
- 📧 okwaravivian26@gmail.com

---

*Last updated:  August 2026*

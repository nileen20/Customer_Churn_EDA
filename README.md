# Customer Churn Exploratory Data Analysis

## Project Overview

This project analyzes customer churn for a telecom company to understand **why customers leave and which customer segments have higher observed churn rates**.

The analysis focuses on identifying patterns in customer demographics, tenure, contracts, services, payment methods, and monthly charges, and translating those patterns into actionable customer retention recommendations.

> This project identifies associations and patterns in the available data. It does not establish causation.

---

## Business Problem

The telecom company is experiencing customer churn and wants to better understand:

- Which customer characteristics are associated with higher churn?
- Which customer segments show particularly high observed churn?
- Where should the business focus further retention analysis?

---

## Objectives

1. Understand the structure and quality of the customer data.
2. Clean and validate the dataset.
3. Analyze churn across important customer characteristics.
4. Identify high-risk customer segments.
5. Translate findings into business insights and retention recommendations.

---

## Dataset

- **Initial records:** 7,262 customers
- **Columns:** 22
- **Final records after duplicate removal:** 7,250
- **Final columns:** 22
- **Final missing values:** 0
- **Final duplicate rows:** 0
- **Final unique Customer IDs:** 7,250
- **Overall observed churn rate:** 25.37%

Each row represents a customer.

---

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- VS Code
- Git & GitHub

---

## Project Workflow

```text
Business Understanding
        ↓
Data Understanding
        ↓
Data Quality Assessment
        ↓
Data Cleaning
        ↓
Data Validation
        ↓
Exploratory Data Analysis
        ↓
Churn Segmentation
        ↓
Business Insights
        ↓
Retention Recommendations
```

---

## Data Cleaning

The dataset contained several data-quality issues that were addressed before analysis.

### Duplicate records

12 duplicate rows were identified and removed.

### Categorical standardization

Inconsistent values such as:

```text
Yes / yes
No / NO
```

were standardized.

### Missing values

Missing values were handled using context-appropriate approaches:

- **Age:** median by SeniorCitizen group
- **MonthlyCharges:** median by InternetService
- **TechSupport:** logical category handling and group mode
- **PaymentMethod:** overall mode
- **TotalCharges:** median by Tenure

After cleaning, all 22 columns contained zero missing values.

---

## Key Findings

### 1. Early-tenure customers have higher churn

Customers with **0–6 months tenure** had an observed churn rate of **47.28%**, compared with **7.57%** for customers with 49–72 months tenure.

**Business insight:** The early customer lifecycle is an important period for retention.

### 2. Month-to-month customers have higher churn

Month-to-month customers had an observed churn rate of **38.56%**, compared with **7.24%** for two-year contract customers.

**Business insight:** Month-to-month customers represent a high-risk customer segment.

### 3. Fiber-optic customers have higher churn

Fiber-optic customers had an observed churn rate of **34.55%**, compared with **22.10%** for DSL customers.

**Business insight:** Pricing, service quality, technical issues, and customer experience should be investigated among fiber customers.

### 4. Electronic-check customers have higher churn

Customers using electronic checks had an observed churn rate of **33.10%**.

**Business insight:** Electronic-check customers are another segment worth investigating for retention.

### 5. Higher monthly charges are associated with higher churn

The high monthly-charge group had an observed churn rate of **35.69%**, compared with **11.31%** for the low-charge group.

**Business insight:** Pricing and perceived value should be investigated among customers with higher monthly charges.

---

## High-Risk Segment Analysis

A segment combining three observed risk characteristics was analyzed:

- Tenure: **0–6 months**
- Contract: **Month-to-month**
- Payment method: **Electronic check**

Results:

| Metric               |                   Value |
| -------------------- | ----------------------: |
| Customers in segment |                     420 |
| Churned customers    |                     236 |
| Segment churn rate   |                  56.19% |
| Overall churn rate   |                  25.37% |
| Difference           | 30.82 percentage points |
| Share of total churn |                  12.83% |

This segment has a substantially higher observed churn rate than the overall customer base and represents a meaningful portion of total churn.

---

## Business Insights & Recommendations

### 1. Improve early customer onboarding

Focus on customers during their first six months through onboarding, early check-ins, and faster issue resolution.

### 2. Target high-risk month-to-month customers

Consider targeted retention offers or suitable incentives for month-to-month customers with higher observed churn.

### 3. Investigate fiber customer experience

Review pricing, service quality, technical issues, and customer experience among fiber-optic customers.

### 4. Review high-charge customers

Investigate pricing, discounts, service bundles, and perceived value among customers with higher monthly charges.

### 5. Prioritize customers with multiple risk characteristics

Use targeted retention strategies for customers showing multiple observed risk characteristics, such as short tenure, month-to-month contracts, and electronic-check payment.

> These recommendations are based on observed associations in the data. Further testing would be required to determine whether specific interventions actually reduce churn.

---

## Analysis Limitations

- The analysis identifies **associations and patterns**, not causation.
- A higher churn rate for a segment does not mean that the segment characteristic causes churn.
- The analysis is based on the available dataset and its recorded customer characteristics.
- No machine-learning prediction model was developed.
- Retention recommendations should be tested before implementation.

---

## Project Structure

```text
customer-churn-eda/
│
├── data/
│   ├── raw/
│   └── processed/
│       └── customer_churn_cleaned.csv
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
│   ├── 04_churn_analysis.ipynb
│   └── 05_business_insights.ipynb
│
├── outputs/
│   ├── charts/
│   │   ├── overall_customer_churn.png
│   │   ├── churn_rate_by_tenure.png
│   │   ├── churn_rate_by_contract.png
│   │   ├── churn_rate_by_internet_service.png
│   │   ├── churn_rate_by_payment_method.png
│   │   ├── high_risk_customer_segments.png
│   │   ├── overall_vs_high_risk_churn.png
│   │   └── churn_contribution.png
│   │
│   └── tables/
│       └── high_risk_segment_summary.csv
│
├── .gitignore
└── README.md
```

---

## Notebook Descriptions

| Notebook                             | Purpose                                                                     |
| ------------------------------------ | --------------------------------------------------------------------------- |
| `01_data_understanding.ipynb`        | Dataset structure, schema, distributions, and data-quality assessment       |
| `02_data_cleaning.ipynb`             | Duplicate removal, standardization, missing-value treatment, and validation |
| `03_exploratory_data_analysis.ipynb` | Churn analysis across customer characteristics and visualization            |
| `04_churn_analysis.ipynb`            | High-risk segment analysis and contribution to total churn                  |
| `05_business_insights.ipynb`         | Business findings, retention recommendations, and limitations               |

---

## Author

**Nileen Bharat Alone**

Data Analyst

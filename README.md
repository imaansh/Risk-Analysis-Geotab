# Risk-Analysis-Geotab
Identifying top 20 at-risk accounts based on data signals

# Customer Risk Analysis & Prioritization Model

## Overview
This project builds an automated customer health scoring system to identify at-risk accounts and prioritize them based on **risk intensity and revenue impact**.  
It combines behavioral, contractual, and financial signals into a unified scoring framework.

---

## Objective
- Detect early churn risk signals across customers  
- Build a transparent and explainable risk scoring model  
- Prioritize accounts based on **business impact + risk level**  
- Enable proactive action for Sales & Customer Success teams  

---

## Data Sources
`accounts.csv` including:
- Fleet size  
- MRR (Monthly Recurring Revenue)  
- Last login activity  
- Support ticket volume  
- Contract end date  

---

## Methodology

### 1. Data Processing
Data is loaded and processed using **DuckDB SQL**, enabling scalable and fast transformations.

---

### 2. Feature Engineering
Percentiles (25th, 50th, 75th) are computed for all key signals to create **relative benchmarks** instead of fixed thresholds, ensuring the model adapts to distribution changes in the dataset.

---

### 3. Risk Scoring Model
Each account is evaluated across four risk dimensions:

- Engagement Risk (usage/activity decline)
- Support Risk (customer friction signals)
- Contract Risk (renewal pressure)
- Fleet Risk (customer scale relevance)

Each dimension is normalized into a 0–100 risk score.

---

### 4. Weighting Strategy (Why these weights?)

A weighted scoring approach is used to reflect **real-world churn drivers in SaaS/telematics-style businesses**:

- **Engagement Risk (35%)**  
  *Highest weight because usage decline is the strongest early indicator of churn.*

- **Contract Risk (30%)**  
  *Renewal proximity directly impacts revenue retention risk.*

- **Support Ticket Risk (25%)**  
  *High ticket volume signals product friction and customer dissatisfaction.*

- **Fleet Size Risk (10%)**  
  *Lower weight because it reflects account scale, not immediate churn behavior.*

👉 The weights prioritize **behavioral + contractual signals over static account attributes**, ensuring the model is predictive rather than descriptive.

---

### 5. Total Risk Score
A composite score is calculated:
Total Risk Score =
(Engagement Risk × 0.35) +
(Support Risk × 0.25) +
(Contract Risk × 0.30) +
(Fleet Risk × 0.10)


---

### 6. Segmentation
Accounts are categorized as:
- Critical (≥70)
- High (50–69)
- Medium (30–49)
- Low (<30)

---

### 7. Prioritization Logic
A **Priority Score** is computed by combining:
- Risk severity
- Revenue impact (MRR)

This ensures that **high-value + high-risk accounts are surfaced first**.

---

## Output
The final output is a ranked list of top at-risk accounts including:
- Company name  
- Country  
- Risk level  
- Priority score  
- Primary risk driver  
- Revenue at risk  

---

## Tech Stack
- Python  
- DuckDB (SQL engine)  
- Pandas  
- Jupyter / Google Colab  

---

## Key Insight
This framework shifts the approach from reactive churn reporting to a **proactive, revenue-aware risk detection system**, enabling teams to act before customer degradation becomes irreversible.

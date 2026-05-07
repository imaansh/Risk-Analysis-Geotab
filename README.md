# Customer & Market Intelligence: Risk, Dashboard & Research Project

## Overview
This project combines **customer risk analytics, interactive dashboarding, and AI-assisted market research** to support data-driven decision-making for sales and strategy teams.  

It includes three core components:
- **Task 1:** Customer Risk Scoring Model  
- **Task 2:** Pipeline Health Dashboard (Tableau/Power BI)  
- **Task 3:** AI-Assisted Market Research (EMEA Opportunity Analysis)  

---

# Task 1 — Customer Risk Scoring Model

## Objective
Build an automated system to identify and rank at-risk accounts based on behavioral, financial, and contractual signals.

## Approach
- Data loaded using DuckDB from `accounts.csv`
- Percentiles computed for key metrics (MRR, engagement, support tickets, fleet size)
- Risk scores assigned across:
  - Engagement Risk
  - Support Risk
  - Contract Risk
  - Fleet Risk

## Scoring Logic
A weighted model was used:

- Engagement Risk → 35% (primary churn signal)
- Contract Risk → 30% (renewal pressure)
- Support Risk → 25% (product friction indicator)
- Fleet Risk → 10% (account scale factor)

## Output
- Total Risk Score (0–100)
- Risk segmentation (Critical, High, Medium, Low)
- Priority ranking combining risk + revenue (MRR)

---

# Task 2 — Pipeline Health Dashboard

## Objective
Create a **one-page executive dashboard** to visualize pipeline health and revenue risk for non-technical stakeholders.

## Key Visuals
- Open pipeline by stage  
- Estimated close-date distribution  
- Average deal size by product  
- Cumulative revenue view  

## Design Principles
- Single-page executive view  
- Minimal color palette for clarity  
- Focus on trends over detail  
- Time-based filtering for pipeline movement  

## Key Insight Areas
- Revenue concentration in upcoming periods  
- Deal stage bottlenecks  
- High-value opportunities at risk of delay  

---

# Task 3 — AI-Assisted Market Research

## Objective
Identify high-potential EMEA markets for telematics expansion using AI-assisted analysis and validation.

## Methodology
- AI prompt designed to evaluate:
  - GDP growth forecasts  
  - Market penetration levels  
  - Demographics (youth population, age distribution)  
  - Tech adoption trends  
  - Competitive saturation  
  - Total Addressable Market (TAM)

- AI generated a large-scale (~400-page) opportunity report
- Outputs were validated using:
  - Public macroeconomic data sources  
  - Manual research  
  - Cross-checking with a second AI model  

## Key Insight Adjustment
- AI initially ranked South Africa as 3rd opportunity market  
- Further validation showed **Turkey’s GDP growth (~3.6%) is significantly higher**, leading to a revised ranking  

---

# Tools & Technologies
- Python (Pandas, DuckDB)
- SQL
- Tableau / Power BI
- Google Colab / Jupyter Notebook
- AI-assisted analysis tools

---

# Key Outcome
This project demonstrates an end-to-end analytics workflow:
- **Predictive analytics (risk scoring)**  
- **Business intelligence (dashboarding)**  
- **Strategic research (market opportunity analysis)**  

Together, they enable **data-driven prioritization of customers and markets for revenue growth.**

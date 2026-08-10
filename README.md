# HR Employee Attrition: Risk & Retention Cost Analysis

## 📌 Project Overview
Most HR attrition analyses stop at describing *who left and when*. This project goes a step further — it translates attrition into a **quantified business cost problem** and builds a **risk-prioritization framework** that HR/business teams could actually act on.

Instead of just answering "what is our attrition rate?", this analysis answers: **"Where are we losing the most money to attrition, and which employee segments should we prioritize retaining?"**

## 🎯 What Makes This Different
Most public HR attrition projects (including nearly every tutorial using this same dataset) stop at exploratory charts — attrition % by department, by age, by income — without connecting the findings to a business decision. This project adds three things most versions skip:

1. **Cost quantification** — every attrition event is converted into an estimated replacement cost (0.75× annual salary, based on SHRM's industry-standard turnover cost range of 0.5–2× salary), so attrition is measured in ₹ impact, not just headcount %.
2. **Multi-signal risk flagging** — instead of ranking risk on a single variable (like low satisfaction alone), employees are flagged High/Medium/Low risk using a combined rule (overtime + job satisfaction + tenure), which better reflects how attrition risk actually compounds in real teams.
3. **Prioritization, not just description** — the final dashboard page ranks departments and roles by **total cost at risk**, directly answering where a retention budget would have the highest ROI.

## 🗂️ Dataset
IBM HR Analytics Employee Attrition & Performance dataset (Kaggle) — 1,470 employee records, 35 attributes, fictional but structurally realistic HR data created by IBM data scientists.

## 🛠️ Methodology

**1. Data Cleaning (Excel)**
- Removed constant/non-informative columns (EmployeeCount, Over18, StandardHours)
- Verified data types and checked for duplicates

**2. Feature Engineering (Excel formulas)**
- `TenureBand`: Buckets employees into 0-1, 1-3, 4-6, 7+ years for tenure-based trend analysis
- `EstReplacementCost`: MonthlyIncome × 12 × 0.75 — estimated cost to replace an employee
- `RiskFlag`: Combines OverTime, JobSatisfaction, and YearsAtCompany into a High/Medium/Low attrition risk score
- `AtRiskCost`: Replacement cost incurred only where attrition actually occurred (Attrition = "Yes")

**3. Aggregation (Excel Pivot Tables)**
- Attrition rate by department (using % of Row Total on actual Yes/No split)
- Attrition rate by tenure band
- Average replacement cost by job role (attrited employees only)
- Risk flag distribution by department

**4. Dashboard (Power BI, 3 pages)**
- **Page 1 – Attrition Overview**: KPIs, department and tenure-band attrition trends
- **Page 2 – Risk Segmentation**: risk-flag distribution, satisfaction vs. tenure scatter, department/overtime slicers
- **Page 3 – Cost Impact & Retention Priority**: total cost at risk, department/role cost ranking, and written business insight

## 📊 Key Findings
- Attrition is not evenly distributed — a small number of departments/roles account for a disproportionate share of total replacement cost, not just headcount.
- High-risk flags (overtime + low satisfaction + short tenure) cluster in specific roles, suggesting targeted rather than company-wide retention interventions would be more cost-effective.
- Framing attrition in ₹ cost rather than % rate reframes the business conversation from "is this normal" to "is this affordable."

## 🖼️ Dashboard Screenshots
See `/screenshots- page1_overview (2).png , page2_risk.png , ` folder for all 3 Power BI pages.

## 🔧 Tools Used
Excel (data cleaning, feature engineering, pivot tables) · Power BI (DAX, dashboard design) · DAX (CALCULATE, DIVIDE, filter context measures)

## 💡 Why This Matters
This project is designed to mirror how an HR Analytics or People Analytics team would actually use this data — not just to report attrition, but to prioritize where retention investment should go. That business-outcome framing is the core differentiator from a standard EDA-style attrition dashboard.

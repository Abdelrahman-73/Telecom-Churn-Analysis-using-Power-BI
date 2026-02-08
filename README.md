# 📉 Databel Telecom: Customer Churn Analysis

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📄 Executive Summary
**Databel** (a fictional telecom provider) is facing a critical issue with customer retention. This project utilizes **Power BI** to diagnose the root causes of customer churn. By analyzing demographic, geographic, and account-level data from **6,687 customers**, I identified key risk factors—specifically related to competitor offers and contract types—and developed a dynamic dashboard to empower the retention team.

## 📂 Repository Contents
* **`Telecome_ Churn_Project.pbix`**: The complete, interactive Power BI Desktop file containing the data model, DAX measures, and report pages.
* **`Telecome-Project-Dashboards.pdf`**: A static, high-resolution export of the dashboard pages for quick viewing (no software required).

---

## 🔍 Business Problem
The goal was to transform raw usage data into actionable insights. The stakeholders required answers to:
1. What is the current **Churn Rate**, and is it sustainable?
2. Why are customers leaving? (Price, Service, or Competitors?)
3. Which customer segments (Age, Group, Contract) are most likely to cancel?
4. How does international activity impact retention?

---

## 💡 Key Insights & Findings
* **Critical Churn Rate:** The overall churn rate is **26.86%**, which is significantly high for the industry.
* **Competitors are the Main Threat:** The top two reasons for churn are *"Competitor made better offer"* (**303 instances**) and *"Competitor had better devices"* (**297 instances**). This indicates a pricing and hardware competitiveness issue rather than just service quality.
* **Contract Risk:** Customers on **Month-to-Month** contracts are the highest risk group, with a churn rate of **46.29%**, compared to much lower rates for 1- or 2-year contracts.
* **International Plan Anomaly:** Surprisingly, customers with an **Active International Plan** have a significantly higher churn rate (**~40%**) compared to those without one, suggesting potential dissatisfaction with international call quality or pricing.
* **Demographics:** "Senior" citizens exhibit different churn behaviors compared to the "Under 30" demographic, requiring targeted retention strategies.

---

## 🛠️ Technical Solution & Methodology

### 1. Data Transformation (ETL)
* Imported raw CSV data into Power BI.
* **Data Cleansing:** Checked for duplicates, handled null values in the 'Reason' column, and standardized state codes.
* Created conditional columns to group `Age` into bins (e.g., Seniors, Under 30) for better segmentation.

### 2. Data Modeling & DAX
* Established a Star Schema (if applicable) or optimized relationships between the Fact table (`Databel Data`) and Dimension tables.
* **Key Measures Created:**
    * `Churn Rate %` = `DIVIDE([Churned Customers], [Total Customers])`
    * `Count of Churned` = `CALCULATE(COUNTROWS('Databel'), 'Databel'[Churn Label] = "Yes")`
* **Advanced Logic:**
    * Implemented logic to analyze "Group" contracts vs. individual contracts.

### 3. Visualization
The report consists of multiple analytical pages:
* **Overview Page:** High-level KPIs (Total Customers, Churn Rate) and a map of Churn by State.
* **Age & Group Analysis:** Breakdown of churn by age bins and group contract size.
* **Churn Details:** A deep dive into the specific reasons for leaving (Competitor, Support, Price) using Matrix visuals and Clustered Bar Charts.

---

## 📂 Dashboard Overview
<img width="1274" height="718" alt="Screenshot 2026-02-08 181342" src="https://github.com/user-attachments/assets/b46b48c6-a3b5-49b5-9d59-c7f3ea083e30" />

<img width="1276" height="719" alt="Screenshot 2026-02-08 181242" src="https://github.com/user-attachments/assets/371c2a75-5e0c-42ec-9ed5-30251bc45ec4" />

<img width="1281" height="718" alt="Screenshot 2026-02-08 181416" src="https://github.com/user-attachments/assets/8b152200-7f7e-4e57-8a6c-6ef236ada266" />

<img width="1278" height="718" alt="Screenshot 2026-02-08 181432" src="https://github.com/user-attachments/assets/d64c01f2-48b3-4fc6-b763-09e23fc05479" />

### Full Interactive Experience
1. Download `Telecome_ Churn_Project.pbix`.
2. Open it in **Microsoft Power BI Desktop**.
3. Use the slicers (Age, State, Payment Method) to cross-filter the visuals and explore the data.

---
*Author: Abdelrahman Hosam*

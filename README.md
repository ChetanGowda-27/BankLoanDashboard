# 💼 Bank Loan, Credit & Debit Analysis Dashboard 📊

## 🔍 Overview

This project leverages **SQL** and **Power BI** to analyze bank loan disbursement patterns, customer demographics, creditworthiness, and transaction behavior. It provides a comprehensive, interactive dashboard for financial decision-makers to monitor and act upon key performance indicators (KPIs).

---

## 🎯 Objectives

- Perform ETL on loan and transaction data using SQL.
- Create dynamic Power BI dashboards for clear insights.
- Analyze loan disbursement trends, default risks, and customer segmentation.
- Evaluate debit/credit performance across branches.
- Enable data-driven strategies using KPIs and visualization.

---

## 📂 Dataset Information

### 🔸 1. Loan Dataset

| Column Name      | Description                                   |
|------------------|-----------------------------------------------|
| Loan_ID          | Unique identifier for each loan               |
| Loan_Amount      | Disbursed loan amount                         |
| Interest_Rate    | Interest rate applied                         |
| Term             | Duration of the loan in months                |
| Grade            | Credit grade of the borrower (A–G)            |
| Age_Group        | Age category of the borrower                  |
| Religion         | Religion of the borrower                      |
| Product_Group    | Type of loan (e.g., Home, Auto)               |
| State            | State of the borrower                         |
| Branch_Name      | Branch issuing the loan                       |
| Disbursement_Date| Date the loan was issued                      |
| Loan_Status      | Status (Active, Closed, Delinquent, etc.)     |
| Is_Verified      | Whether the loan was verified                 |

### 🔸 2. Transaction Dataset

| Column Name      | Description                                   |
|------------------|-----------------------------------------------|
| Transaction_ID   | Unique identifier for the transaction         |
| Account_ID       | Customer’s account number                     |
| Transaction_Type | Either "Credit" or "Debit"                    |
| Amount           | Value of the transaction                      |
| Branch_Name      | Branch where the transaction took place       |
| Transaction_Date | Date of the transaction                       |

---

## 🗄️ SQL Table Schemas

### 📘 Table: `loan_data`

```sql
CREATE TABLE loan_data (
    Loan_ID VARCHAR(20) PRIMARY KEY,
    Loan_Amount DECIMAL(12,2),
    Interest_Rate DECIMAL(5,2),
    Term INT,
    Grade CHAR(1),
    Age_Group VARCHAR(20),
    Religion VARCHAR(20),
    Product_Group VARCHAR(50),
    State VARCHAR(50),
    Branch_Name VARCHAR(100),
    Disbursement_Date DATE,
    Loan_Status VARCHAR(20),
    Is_Verified VARCHAR(10)
);
````

### 📘 Table: `transaction_data`

```sql
CREATE TABLE transaction_data (
    Transaction_ID VARCHAR(30) PRIMARY KEY,
    Account_ID VARCHAR(30),
    Transaction_Type VARCHAR(10),
    Amount DECIMAL(12,2),
    Branch_Name VARCHAR(100),
    Transaction_Date DATE
);
```

---

## 📘 Entity Relationship Diagram (ERD)

```
+---------------------+              +--------------------------+
|     loan_data       |              |     transaction_data     |
+---------------------+              +--------------------------+
| Loan_ID (PK)        |              | Transaction_ID (PK)      |
| Loan_Amount         |              | Account_ID               |
| Interest_Rate       |              | Transaction_Type         |
| Term                |              | Amount                   |
| Grade               |              | Branch_Name              |
| Age_Group           |              | Transaction_Date         |
| Religion            |              +--------------------------+
| Product_Group       |
| State               |
| Branch_Name  <--------------------->  Branch_Name
| Disbursement_Date   |
| Loan_Status         |
| Is_Verified         |
+---------------------+
```

---

## 📌 KPIs Monitored

### 💳 Loan Dashboard KPIs

* Total Loan Amount Funded
* Total Loans
* Total Collection (Principal + Interest)
* Total Interest Income
* Branch-Wise Performance
* State-Wise Loan Distribution
* Religion-Wise Loan Breakdown
* Product Group-Wise Loans
* Disbursement Trend (Yearly)
* Grade-Wise Risk Analysis
* Default Loan Count
* Delinquent Client Count
* Delinquent & Default Loan Rate
* Loan Status Breakdown
* Age Group-Wise Loan Share
* Loan Maturity Timeline
* No Verified Loans Count

### 💰 Credit & Debit Dashboard KPIs

* Total Credit Amount
* Total Debit Amount
* Credit to Debit Ratio
* Net Transaction Amount
* Account Activity Ratio
* Transactions per Day/Week/Month
* Total Transaction Volume by Branch

---

## 📊 Power BI Dashboards

### 🔹 Loan Analysis Dashboard

![Loan Dashboard](https://github.com/user-attachments/assets/40e5a01c-03c1-43d8-8c17-6a50612ef9f3)

### 🔹 Credit & Debit Analysis Dashboard

![Credit & Debit Dashboard](https://github.com/user-attachments/assets/d060d9bb-f35b-4b25-8c01-8d32b2905b11)

---

## 📈 Key Insights

* **Religion-Wise Loan:** 75% of loans issued to Hindu borrowers; Muslim (11%), Sikh (13%), Christian (1%).
* **Disbursement Trend:** Peak in FY 2019 (56.87%), sharp fall in FY 2020 (8.51%).
* **Age Group:** 26–45 years account for most loans; youngest and oldest age groups take fewer loans.
* **Grade-Wise:** Grades B and C dominate; lower risk preference.
* **Loan Status:** 63% active, only 12% delinquent/defaulted — strong repayment profile.
* **Loan Maturity:** 36-month loans dominate over 60-month ones in outstanding loans.
* **Product Group:** Home Loans ₹278.26 Cr, Services ₹155.53 Cr — housing dominates.
* **Unverified Loans:** 16,921 marked “No,” 25,818 as “Unknown” — indicates risk in documentation.

---

## 💡 Use Cases

* Identify high-risk customers and default patterns.
* Analyze branch-level performance and customer behavior.
* Use geographic and demographic filters for targeted campaigns.
* Understand net cash flow through debit-credit tracking.
* Improve loan product strategy based on customer profiles.

---

## 🧠 Skills Applied

* SQL: ETL, joins, filtering, transformation
* Power BI: Slicers, DAX measures, KPI Cards, line & bar charts
* Data Modeling: Relationships and normalization
* Dashboard Design: Interactive, clean, user-focused
* Insight Generation: Business decision support

---

## 🛠️ How to Use This Project

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/Bank-Loan-Credit-Debit-Analysis.git
   ```

2. **Open Power BI Desktop** and load:

   * `loan_data.csv`
   * `transaction_data.csv`

3. **Configure SQL connection** if you're pulling from a database.

4. Refresh model and explore dashboards interactively.

---

## 🚀 Future Enhancements

* Integrate live APIs or real-time SQL connection
* Add Python/R scripts for ML-based default prediction
* Embed dashboards on a web portal with role-based filters
* Add forecasting using Power BI’s built-in analytics
* Automate alerts for default spikes or unusual activity

---



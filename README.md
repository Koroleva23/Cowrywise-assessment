# Cowrywise-assessment
# SQL Business Insights – Customer & Account Analytics

This project contains four SQL scripts I wrote to support different business teams (Marketing, Finance, and Operations) in answering key questions about customer behavior, transaction patterns, and account health. The queries are written in MySQL and based on sample data tables from a typical financial services environment.

---

## Scripts Overview

### 1. High-Value Customers with Multiple Products

**Use case:** Identify customers who have both a savings and an investment plan — a great cross-selling opportunity.

- Joins user, account, and plan tables
- Filters for customers with both product types
- Calculates total deposits
- Sorted by deposit value

---

### 2. Transaction Frequency Analysis

**Use case:** Segment customers into frequency buckets (high, medium, low) based on how often they transact monthly.

- Uses CTEs for clarity
- Calculates active months per customer
- Categorizes users by average transactions/month
- Outputs segment counts and averages

---

### 3. Account Inactivity Alert

**Use case:** Flag accounts that have had no inflow transactions in over a year (365+ days).

- Compares last transaction date to current date
- Groups by account and customer
- Classifies as either Savings or Investment
- Returns accounts inactive for over a year

---

### 4. Customer Lifetime Value (CLV) Estimation

**Use case:** Estimate CLV using account tenure and transaction volume with a simplified profitability model.

- Calculates months since signup
- Computes total transactions and average transaction value
- Estimates CLV using:  
  `(transactions / tenure) * 12 * 0.1% of avg transaction`
- Ranked by CLV from highest to lowest

---

##  How to Run

1. Open your MySQL client (e.g., MySQL Workbench, DBeaver, or CLI).
2. Make sure you're connected to the appropriate database (e.g., `adashi_staging`).
3. Run each `.sql` script separately depending on the question you're trying to answer.
4. Review results in the query output or export as needed.

---

## Prerequisites

- MySQL 5.7+ or compatible
- Tables :
  - `users_customuser`
  - `savings_savingsaccount`
  - `plans_plan`

Make sure the data in these tables includes columns such as `created_on`, `amount`, `is_regular_savings`, and `is_a_fund`.

---

## Notes

- I used `GREATEST()` and `PERIOD_DIFF()` to handle edge cases like zero-month tenures.
- I used CTEs where helpful to break down complex logic and make the queries more readable.

---

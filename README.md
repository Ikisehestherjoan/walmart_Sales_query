
---

# 🛒 Walmart Sales Analysis (SQL Project)

## 📌 About the Project

This project explores Walmart sales data to uncover insights into:

* Top-performing branches and product lines
* Sales trends across different periods
* Customer purchasing behavior

The goal is to identify key drivers of sales performance and provide insights to improve and optimize business strategies.

The dataset was sourced from the **Kaggle Walmart Sales Forecasting Competition**, where historical sales data from 45 Walmart stores is used to predict future sales across departments.

> *“Participants are provided with historical sales data for 45 Walmart stores located in different regions. Each store contains multiple departments, and the task is to forecast sales for each department. Holiday markdown events are included, which impact sales but are difficult to predict.”*

---

## 🎯 Project Objectives

The main objectives of this project are:

* Analyze sales performance across branches
* Identify high- and low-performing product lines
* Understand customer segments and behavior
* Evaluate factors influencing revenue and profitability

---

## 📊 Dataset Description

The dataset contains **1,000 rows and 17 columns**, representing sales transactions from three Walmart branches located in:

* Mandalay
* Yangon
* Naypyitaw

### 📁 Column Overview

| Column Name             | Description           | Data Type |
| ----------------------- | --------------------- | --------- |
| invoice_id              | Sales invoice ID      | VARCHAR   |
| branch                  | Branch location code  | VARCHAR   |
| city                    | City of the branch    | VARCHAR   |
| customer_type           | Customer category     | VARCHAR   |
| gender                  | Customer gender       | VARCHAR   |
| product_line            | Product category      | VARCHAR   |
| unit_price              | Price per unit        | DECIMAL   |
| quantity                | Quantity sold         | INT       |
| VAT                     | Value Added Tax       | FLOAT     |
| total                   | Total purchase amount | DECIMAL   |
| date                    | Transaction date      | DATE      |
| time                    | Transaction time      | TIME      |
| payment_method          | Payment method used   | VARCHAR   |
| cogs                    | Cost of goods sold    | DECIMAL   |
| gross_margin_percentage | Profit margin (%)     | FLOAT     |
| gross_income            | Gross profit          | DECIMAL   |
| rating                  | Customer rating       | FLOAT     |

---

## 🔍 Analysis Performed

### 📦 Product Analysis

* Identify top-performing product lines
* Determine underperforming categories
* Analyze product performance by gender

### 💰 Sales Analysis

* Revenue trends over time
* Sales performance by branch and city
* Impact of time of day on sales

### 👥 Customer Analysis

* Customer segmentation (type & gender)
* Payment method preferences
* Customer contribution to revenue

---

## ⚙️ Approach

### 1. Data Wrangling

* Checked for missing/null values
* Created structured database tables
* Ensured data integrity using constraints

### 2. Feature Engineering

Created additional columns to enhance analysis:

* **time_of_day** → Morning, Afternoon, Evening
* **day_name** → Day of the week
* **month_name** → Month of transaction

### 3. Exploratory Data Analysis (EDA)

* Performed SQL queries to answer key business questions
* Generated insights on sales, customers, and products

---

## ❓ Business Questions Answered

### 🧾 General

* How many unique cities are present?
* Which branches operate in each city?

### 📦 Product

* What are the most selling product lines?
* Which product line generates the highest revenue?
* Which product line has the highest VAT?
* What is the most common payment method?

### 💰 Sales

* What are the sales trends by time of day?
* Which customer type generates the most revenue?
* Which city has the highest VAT contribution?

### 👥 Customer

* What is the most common customer type?
* Which gender dominates purchases?
* When do customers give the highest ratings?
* Which day has the best average ratings?

---

## 🧮 Key Metrics & Calculations

* **COGS (Cost of Goods Sold)**

  ```
  COGS = unit_price × quantity
  ```

* **VAT (5%)**

  ```
  VAT = 0.05 × COGS
  ```

* **Total Revenue**

  ```
  Total = COGS + VAT
  ```

* **Gross Profit**

  ```
  Gross Profit = Total - COGS
  ```

* **Gross Margin (%)**

  ```
  Gross Margin = (Gross Income / Total Revenue)
  ```

---

## 🛠️ SQL Implementation

```sql
CREATE DATABASE IF NOT EXISTS walmartdb;

CREATE TABLE IF NOT EXISTS sales (
    invoice_id VARCHAR(30) NOT NULL PRIMARY KEY,
    branch VARCHAR(5) NOT NULL,
    city VARCHAR(30) NOT NULL,
    customer_type VARCHAR(30) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    product_line VARCHAR(100) NOT NULL,
    unit_price DECIMAL(10,2) NOT NULL,
    quantity INT NOT NULL,
    VAT FLOAT(6,4) NOT NULL,
    total DECIMAL(12,4) NOT NULL,
    date DATETIME NOT NULL,
    time TIME NOT NULL,
    payment_method VARCHAR(15) NOT NULL,
    cogs DECIMAL(10,2) NOT NULL,
    gross_margin_percent FLOAT(11,9),
    gross_income DECIMAL(12,4) NOT NULL,
    rating FLOAT(2,1) NOT NULL
);
```

---

## 📁 Project Structure

```
├── walmartquery.sql   # SQL queries and analysis
├── README.md          # Project documentation
```

---

## 📌 Conclusion

This project provides actionable insights into Walmart’s sales performance by analyzing product trends, customer behavior, and revenue drivers. The findings can help improve sales strategies, optimize inventory, and enhance customer targeting.

---

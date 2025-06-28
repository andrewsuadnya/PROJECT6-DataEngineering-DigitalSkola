# 📊 Monthly Order Reporting using Hadoop MapReduce

## 📄 Project Summary

This project is a continuation of a previous batch processing workflow. The goal is to design and implement a data analytics pipeline using **Hadoop** to generate a **monthly order report**. The final output is a data mart table named `total_orders_based_on_month`, which aggregates order data using **MapReduce** to support business reporting and dashboarding.

The solution integrates PostgreSQL (as the source), Hadoop (for distributed processing), and Python-based MapReduce logic to transform the data into a summary view.

### 🔁 ETL Architecture Overview

![PROJECT 6\_Andrew Fortino Mahardika Suadnya (1)](https://github.com/user-attachments/assets/7e25bd2d-f640-4306-9bb5-767978595685)

### 🔣 MapReduce Transformation Flow

![PROJECT 6\_Andrew Fortino Mahardika Suadnya (2)](https://github.com/user-attachments/assets/55df1687-d237-4ef8-974d-e30da1703f5a)

---

## 🎯 Objective

Transform and summarize historical order data into a monthly-level reporting format to support business intelligence and dashboard visualization. The processing is designed to be efficient and completed within 1 hour using distributed computing tools.

---

## 📌 Implementation Highlights

* ✅ Source data was pre-loaded into PostgreSQL via batch ETL (Project 3).
* ✅ Hadoop was used as the data warehouse to store `dim_orders`.
* ✅ A custom **MapReduce** script was developed to transform the DWH data into the monthly aggregated data mart `total_orders_based_on_month`.
* ✅ Output was exported into a CSV `.txt` and PostgreSQL for analyst consumption.

---

## 🧱 Output Schema: `total_orders_based_on_month`

| Column Name    | Description                     |
| -------------- | ------------------------------- |
| `month`        | Aggregated month (YYYY-MM)      |
| `total_orders` | Total number of orders in month |

### 📤 Sample Output:

```csv
month,total_orders
"2022-01"	18
"2022-02"	9
"2022-03"	9
"2022-04"	9
"2022-05"	18
"2022-06"	18
"2022-07"	27
```

---

## 🔍 Technical Notes

* **Hadoop Environment**: Local setup via Docker and testing on a shared cluster.
* **HDFS Storage**: Order data from PostgreSQL was exported locally then loaded to HDFS.
* **MapReduce**: Written in Python using custom `mapper.py` and `reducer.py` scripts.
* **Execution Time**: ETL completed in under 1 hour — acceptable for batch-level reporting.

---

## 📊 Insights

* This ETL pipeline enables scalable, efficient monthly aggregation from large transactional data.
* It successfully decouples analytics workloads from production systems.
* The process demonstrates Hadoop's role in modern big data architecture even for small-scale projects.

---

## 🔗 Related Projects

* 📦 [Project 3 - Batch ETL to PostgreSQL Data Warehouse](https://github.com/andrewsuadnya/PROJECT3-DataEngineering-DigitalSkola)

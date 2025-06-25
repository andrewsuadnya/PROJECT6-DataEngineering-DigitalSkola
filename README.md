# Monthly Order Reporting using Hadoop MapReduce

## 📄 Project Summary

This project is a continuation of a previous batch processing workflow. The main goal is to design and implement a data analytics pipeline using Hadoop to generate a **monthly order report**. The final output is a data mart table `total_orders_based_on_month` that aggregates order data from a PostgreSQL-based data warehouse using **MapReduce**.

![PROJECT 6_Andrew Fortino Mahardika Suadnya (1)](https://github.com/user-attachments/assets/a7cd1daf-0574-46a3-bcd3-9212fc239179)
![PROJECT 6_Andrew Fortino Mahardika Suadnya (2)](https://github.com/user-attachments/assets/55df1687-d237-4ef8-974d-e30da1703f5a)

---

## 🎯 Objective

Transform and summarize historical order data into a monthly-level reporting format to support business intelligence and dashboard visualization. The processing is designed to be efficient and completed within 1 hour using big data tools.

---

## 📌 Implementation Highlights

* Source data was already loaded into PostgreSQL via batch ETL in a prior project.
* Hadoop was used to store and process the data warehouse table `dim_orders`.
* A MapReduce job was developed to calculate monthly order totals and produce a reporting table `total_orders_based_on_month`.

---

## 🧱 Output Schema

| Column Name    | Description                     |
| -------------- | ------------------------------- |
| `month`        | Aggregated month (YYYY-MM)      |
| `total_orders` | Total number of orders in month |

Example output:

```
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

* **Hadoop Environment**: Deployed via Docker and also tested on remote cluster.
* **Data Upload**: `dim_orders` was exported from PostgreSQL to local and then uploaded to Hadoop HDFS.
* **MapReduce Processing**: Custom Python-based mapper and reducer scripts were written to group and sum orders by month.
* **Execution Time**: The entire pipeline completed in under 1 hour, fulfilling the project requirement.

---

## 📊 Insights

The final data mart enables efficient reporting for business stakeholders and sets the foundation for further analytics use cases. It decouples reporting workloads from the transactional system and leverages distributed computing to handle large datasets.

---

## 🔗 Related Projects

* [Project 3 - Batch ETL to PostgreSQL Data Warehouse](https://github.com/andrewsuadnya/PROJECT3-DataEngineering-DigitalSkola): Initial ETL pipeline and PostgreSQL setup.

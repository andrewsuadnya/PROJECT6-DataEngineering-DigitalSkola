# Data Analytics with Hadoop

## 📄 Project Overview

This Project is a continuation of the batch processing pipeline developed in Project 3. In this project, you will implement a data analytics pipeline using **Hadoop** to transform batch-processed data into a monthly aggregated data mart for reporting.

The final goal is to create a data mart table named `total_orders_based_on_month` using **MapReduce**, with the columns `month` and `total_orders`, to support monthly sales reporting.

---

## 🚀 Tools & Dependencies

* **PostgreSQL** (via Docker or direct installation)
* **Hadoop** (version < 3.2.1)
* **Python** (for scripting and transformation)
* **DBeaver / PgAdmin** (optional GUI for PostgreSQL)
* **Script Project 3 - Batch Processing**

---

## 🔧 Preparation Steps

1. Download the project script for batch processing: [GitHub Repo](https://github.com/MSinggihP/digitaskola_de_10_batch_processing)

2. Review and understand the previous batch processing scripts.

3. Install Hadoop:

   * [Ubuntu Installation Guide](https://www.rosehosting.com/blog/how-to-install-hadoop-on-debian-11/)
   * [Windows Guide](https://towardsdatascience.com/installing-hadoop-3-2-1-single-node-cluster-on-windows-10-ac258dd48aef)
   * [Docker-based Setup](https://medium.com/analytics-vidhya/hadoop-single-node-cluster-on-docker-e88c3d09a256):

     ```bash
     docker run -d -it --name hadoop-local -p 9864:9864 -p 9870:9870 -p 8088:8088 --hostname hadoop-local hadoop
     ```

4. Update `/etc/hosts` or Windows host file:

   ```
   127.0.0.1 hadoop-local
   35.222.31.142 hadoop-server
   ```

   [Guide to modifying Windows hosts file](https://ecompile.io/blog/localhost-custom-domain-name)

5. Ensure the following Hadoop services are running:

   * NameNode
   * DataNode
   * YARN Resource Manager
   * YARN Node Manager

6. Hadoop access options:

   * Install Hadoop locally (native OS)
   * Use Docker-based Hadoop
   * Connect to tutor's server: [http://35.222.31.142:9870](http://35.222.31.142:9870)

7. (Optional) Connect your PostgreSQL database using DBeaver or PgAdmin.

8. Refer to the [project flow diagram](https://drive.google.com/file/d/1rzhm4n4sy4_668xCfLXOlJKhUkj0HV2j/view?usp=sharing)

---

## 🔮 Study Case

You have previously built a batch processing ETL pipeline. Now, extend that by building a **data mart** for monthly order reporting.

### Requirements:

* Create output with the columns: `month`, `total_orders`
* Use **Hadoop** to store the DWH table `dim_orders`
* Use **MapReduce** to create the data mart `total_orders_based_on_month`
* Total execution time must be < 1 hour

---

## ✅ Tasks Breakdown

1. Skip extraction (already done in Project 3)
2. Create `dim_orders` as DWH table using Hadoop
3. Implement MapReduce to generate `total_orders_based_on_month`

---

## 📘 Step-by-Step Implementation

1. Clone and review Project 3 batch processing scripts.
2. Design and document the new ETL flow (draw diagram).
3. Add Hadoop connection configuration in JSON.
4. Create Python script to connect to Hadoop.
5. Define and use current datetime for transformation.
6. Create dummy data for DWH locally for testing.
7. Upload DWH data to Hadoop HDFS.
8. Implement MapReduce script to transform the data.
9. Generate and verify the final output table with `month` and `total_orders`.

---

## 🔗 Repository

> Link ke repositori pribadi atau publik dapat ditambahkan di sini jika tersedia.

---

## 🙏 Acknowledgements

* DigitalSkola - SIB Batch 6
* Hadoop Tutorial References
* Tutor & Reviewer Support

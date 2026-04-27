# 📊 TP5 - Decision-Making System for a Bookstore

## 🎯 Objective

The goal of this project is to design and implement a **Data Warehouse (DW)** for a bookstore using an ETL process built with Talend.

The system enables analysis of sales, customers, books, and publishers to support decision-making.

---

## 🧩 Data Sources

The data comes from multiple heterogeneous sources:

* 📄 **Livres.xml**: book information
* 📄 **Editions.txt**: publishers information
* 📊 **Clients.csv**: customer data
* 📊 **Ventes.xls**: global sales
* 📊 **Ventes détaillées.xls**: detailed sales

---

## ⚙️ Tools Used

* Talend Open Studio (ETL)
* PostgreSQL (Database Management System)

---

## 🗄️ Database

* DBMS: PostgreSQL
* Type: Data Warehouse
* Modeling: Star Schema ⭐

⚠️ Connection credentials are not included for security reasons.

---

## 📊 Data Model

### 🔹 Dimension Tables

* **DIM_CLIENT**: customer information
* **DIM_EDITEUR**: publisher information
* **DIM_LIVRE**: book information
* **DIM_TEMPS**: time dimension

### 🔹 Fact Table

* **FACT_VENTES**: contains measures (quantity, revenue, etc.)

---

## 🔄 ETL Process (Talend)

The ETL workflow is organized into independent jobs for each dimension and one job for the fact table:

### 🔹 Dimension Jobs

* **TP5_P1 → DIM_CLIENT**

  * Load and prepare customer data

* **TP5_P2 → DIM_EDITEUR**

  * Load and prepare publisher data

* **TP5_P3 → DIM_LIVRE**

  * Load and prepare book data

* **TP5_P4 → DIM_TEMPS**

  * Generate and load time dimension

### 🔹 Fact Table Job

* **TP5 → FACT_VENTES**

  * Combine all dimension keys
  * Perform transformations and joins
  * Load the fact table

---

## 📁 Project Structure

* **metadata/**: data sources and connections
* **process/**: Talend jobs

  * TP5_P1 (DIM_CLIENT)
  * TP5_P2 (DIM_EDITEUR)
  * TP5_P3 (DIM_LIVRE)
  * TP5_P4 (DIM_TEMPS)
  * TP5 (FACT_VENTES)
* **talend.project**: project configuration

---

## 🔗 Execution Logic

The execution should follow this order:

1. TP5_P1 → Load DIM_CLIENT
2. TP5_P2 → Load DIM_EDITEUR
3. TP5_P3 → Load DIM_LIVRE
4. TP5_P4 → Load DIM_TEMPS
5. TP5 → Load FACT_VENTES

⚠️ The fact table must be loaded **after all dimensions** to ensure referential integrity.

---

## 🚀 How to Run the Project

1. Open the project in Talend Open Studio
2. Configure the PostgreSQL connection

### ▶️ Execution

Run the jobs in the following order:

* TP5_P1
* TP5_P2
* TP5_P3
* TP5_P4
* TP5

---

## 📈 Analytical Capabilities

The system can answer the following questions:

* 📊 Top / Flop book sales by month/year
* 👥 Top / Flop customers
* 💰 Total sales by period
* 🚻 Gender-based purchasing analysis

---

## 👤 Author

**Mohammed Ryad Benyakoub**

---

## 📌 Notes

This project was developed as part of the course:
**Multidimensional Databases and Data Warehousing**

It represents a simplified implementation of a real-world decision support system.

# SQL Data Warehouse Project

Building a modern data warehouse using **SQL Server**, covering the full pipeline from raw data ingestion to analytics-ready reporting. This project follows a layered architecture (Bronze → Silver → Gold) to demonstrate ETL design, data modeling, and warehouse best practices.

## 📌 Project Overview

This repository showcases an end-to-end data warehousing solution, including:

- **ETL Pipelines** – Extracting, transforming, and loading data from multiple source systems into the warehouse.
- **Data Modeling** – Designing fact and dimension tables using a star schema for optimized analytical queries.
- **Data Warehouse Architecture** – Implementing a multi-layer approach to ensure data quality and traceability at each stage.
- **Analytics & Reporting** – Enabling business users to run queries and generate insights from clean, structured data.

## 🏗️ Architecture

The warehouse follows the **Medallion Architecture** pattern:

| Layer | Purpose |
|-------|---------|
| **Bronze** | Raw data ingested as-is from source systems (no transformations) |
| **Silver** | Cleaned, validated, and standardized data (deduplicated, typed, joined) |
| **Gold** | Business-ready, aggregated data modeled into star schema for reporting |

```
Source Systems --> Bronze Layer --> Silver Layer --> Gold Layer --> BI / Analytics
     (raw)          (raw copy)      (cleaned)        (modeled)
```

## 🔧 Tech Stack

- **Database:** SQL Server
- **ETL:** T-SQL scripts / SSIS (or specify your tool)
- **Data Modeling:** Star Schema (Fact & Dimension tables)
- **Version Control:** Git & GitHub

## 📂 Repository Structure

```
SQL_Data_Warehouse/
│
├── datasets/              # Sample source data (CSV/raw files)
├── scripts/
│   ├── bronze/            # Scripts to load raw data
│   ├── silver/            # Scripts to clean & transform data
│   └── gold/              # Scripts to build fact/dimension views & tables
├── docs/                  # Data dictionary, architecture diagrams, notes
├── tests/                 # Data quality checks & validation scripts
└── README.md
```

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/SQL_Data_Warehouse.git
   ```
2. Set up a SQL Server instance (local or Docker).
3. Run the Bronze layer scripts to load raw data.
4. Run the Silver layer scripts to clean and transform the data.
5. Run the Gold layer scripts to create the final star schema.
6. Connect your BI tool (Power BI, Tableau, etc.) to the Gold layer for reporting.

## 📊 Data Model

The Gold layer is modeled using a **star schema**, consisting of:

- **Fact Tables** – Store measurable, transactional data (e.g., sales, orders).
- **Dimension Tables** – Store descriptive attributes (e.g., customers, products, dates).

This design optimizes query performance for analytical workloads and simplifies reporting.

## ✅ Data Quality Checks

Includes validation scripts to check for:
- Missing or null values
- Duplicate records
- Referential integrity between fact and dimension tables
- Data type consistency across layers

## 📈 Future Improvements

- Automate pipeline orchestration using Azure Data Factory / SSIS
- Add incremental loading (instead of full refresh)
- Build Power BI dashboards on top of the Gold layer
- Add CI/CD for database deployments

## 📄 License

This project is licensed under the [MIT License](LICENSE) — feel free to use, modify, and share.


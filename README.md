# SQL Data Warehouse & Analytics Pipeline

An end-to-end relational data warehouse and analytical reporting pipeline built using **SQL Server (T-SQL)** and **Python**. This project implements a multi-layer Medallion Architecture (Bronze, Silver, Gold) to ingest, clean, model, and analyze multi-source sales and customer datasets.

---

## Architecture Overview

The pipeline follows a structured three-tier data warehousing workflow:

1. **Bronze Layer (Raw Ingestion):** Ingests raw CSV source files (`CRM` and `ERP` datasets) directly into relational tables without modification.
2. **Silver Layer (Data Cleaning & Transformation):** Cleanses, standardizes, and normalizes raw records—handling missing values, removing duplicates, standardizing categorical codes, and enforcing data types.
3. **Gold Layer (Business Modeling & Star Schema):** Integrates cleaned tables into analytical **Dimension** (`dim_customers`, `dim_products`) and **Fact** (`fact_sales`) views optimized for reporting.
4. **Python Automation & Reporting:** Automates SQL transformation execution and exports consolidated Gold-layer KPI reports to CSV using `pandas` and `pyodbc`.

---

## Repository Structure

```text
├── datasets/                  # Raw CRM and ERP source CSV files
├── scripts/
│   ├── bronze/                # DDL and bulk ingestion scripts for raw tables
│   ├── silver/                # Data cleaning, standardization, and transformation scripts
│   ├── gold/                  # Star schema views (Dimensions & Facts)
│   └── analytics/             # Exploratory Data Analysis (EDA) & KPI reporting queries
├── etl_pipeline.py            # Python script for SQL execution and report export
└── README.md

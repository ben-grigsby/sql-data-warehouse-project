# Data Warehouse Project: Medallion Architecture Implementation

## Overview

This project implements a data warehouse using the Medallion Architecture (Bronze, Silver, Gold layers). It demonstrates how raw sales data is transformed into business-ready insights using structured SQL pipelines and clear documentation. The project showcases core data engineering concepts, with a focus on readability, modular structure, and quality checks.

### Project Structure
```
├── datasets/                   # Raw input datasets (e.g., customers, locations, products)
├── docs/                       # Data architecture and flow diagrams
├── scripts/
│   ├── bronze/                 # DDL & load procedures for the Bronze layer
│   ├── silver/                 # DDL & transformation procedures for the Silver layer
│   ├── gold/                   # DDL for the Gold layer (business-ready tables)
│   └── empty/                  # Initialization scripts
├── tests/                      # SQL scripts for data quality checks
├── LICENSE
└── README.md                   # This file
```

## Data Pipeline Summary

### Bronze Layer
- **Purpose:** Stores raw, ingested data with minimal transformation.
- **Scripts:**
  - `ddl_bronze.sql`
  - `proc_load_bronze.sql`

### Silver Layer
- **Purpose:** Cleansed and joined data ready for analytics.
- **Scripts:**
  - `ddl_silver.sql`
  - `proc_load_silver.sql`

### Gold Layer
- **Purpose:** Curated dimension and fact tables for BI/reporting.
- **Scripts:**
  - `ddl_gold.sql`
- **Quality Checks:**
  - `quality_checks_gold.sql`
  - `quality_checks_silver.sql`

## Documentation

- **Data Architecture Diagrams:**  
  - `data_architecture.drawio`, `data_architecture.drawio.png`  
  - `data_flow_diagram.drawio`, `data_flow_diagram.drawio.png`  
  - `data_mart.drawio`, `data_mart.drawio.png`  
  - `integration_model.drawio`, `integration_model.drawio.png`

- **Data Catalog:**  
  - `data_catalog.md`

### How to Run This Project

To set up and run this data warehouse project, follow these steps:

1. **Initialize the Database**
   - Run the initialization script to create the database schema:
     ```sql
     scripts/empty/init_database.sql
     ```

2. **Load Bronze Layer (Raw Data)**
   - Use the provided DDL and load procedures:
     ```sql
     scripts/bronze/ddl_bronze.SQL
     scripts/bronze/proc_load_bronze.sql
     ```

3. **Transform and Load Silver Layer (Cleaned Data)**
   - Execute transformation logic:
     ```sql
     scripts/silver/ddl_silver.sql
     scripts/silver/proc_load_silver.sql
     ```

4. **Create Gold Layer (Business-Ready Tables)**
   - Run the DDL to build dimension and fact tables:
     ```sql
     scripts/gold/ddl_gold.sql
     ```

5. **Verify Data Quality**
   - Run tests to validate data consistency and integrity:
     ```sql
     tests/quality_checks_silver.sql
     tests/quality_checks_gold.sql
     ```

> **Note:** Ensure your SQL environment (e.g., SQL Server, PostgreSQL, SQLite) is properly configured and has access to the dataset files located in the `/datasets` directory.

### Documentation

The `docs/` directory contains visual diagrams to help understand the data warehouse architecture and flow:

- **data_architecture.drawio / .png** – High-level overview of the medallion architecture (Bronze → Silver → Gold).
- **date_flow_diagram.drawio / .png** – Flow of data from raw ingestion to business-level tables.
- **integration_model.drawio / .png** – Diagram showing how different datasets are integrated.
- **data_mart.drawio / .png** – Final structure of the gold layer with dimension and fact tables.

These diagrams provide context for the database structure, data transformations, and the intended analytical use cases.

## Notes
- SQL scripts are modular and can be executed step-by-step.
- Visual documentation provides a full understanding of schema relationships and data transformation.
- Designed to demonstrate best practices in data modeling, data flow, and validation.

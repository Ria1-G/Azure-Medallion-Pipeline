
# Azure Medallion Architecture Data Pipeline (WIP)

This project demonstrates a scalable data pipeline using Azure services, based on the Medallion Architecture (Bronze → Silver → Gold).

## 📁 Structure

- `step1-3_resource_db_pipeline/`: Initial ADF + SQL Setup
- `step4_incremental_load/`: Incremental ingestion logic
- `step5_silver_layer_databricks/`: Databricks code + transformations
- `step6_gold_star_schema/`: Dimensional modeling (star schema)
- `images/`: Screenshots

## 🏗️ Tools Used

- Azure SQL Database
- Azure Data Factory
- Azure Databricks
- Azure Data Lake Storage (Gen2)

---

## 📁 Project Modules

### 🔹 Step 1–3: ADF Initial Ingestion Pipeline
Location: `step1-3_resource_db_pipeline/`
- Created **Azure Resource Group**, **SQL Database**, and **ADF pipeline**
- Used **Copy Activity** to move data from HTTP to SQL
- Table schema set to all `STRING` fields to handle unclean data

### 🔹 Step 4: Incremental Load Pipeline (ADF)
Location: `step4_incremental_load/`
- Designed **WaterTable** to store `MIN` invoice date
- Used **Lookup Activities** to get `MIN`/`MAX` dates
- Copy Activity stores new data into **Bronze (ADLS Gen2)** in **Parquet format**
- Created a **Stored Procedure** to update the WaterTable after each run

### 🔹 Step 5: Silver Layer Transformation (Databricks)
Location: `step5_silver_layer_databricks/`
- Connected Databricks to **Bronze ADLS** using **access key**
- Transformed and cleaned data saved in **Silver container**
- HTML version of Databricks notebook:  
  👉 [`Silver_Layer_Code.html`](./step5_silver_layer_databricks/Silver_Layer_Code.html)

  ### 🔹 Step 6 : Gold Layer (Star Schema)
Location: `step6_gold_star_schema/`
- Created **3 Dimension Tables**: Retailer, Location, Date
- Added a **Flag** to count pipeline runs (inside Retail dimension)
- Created **1 Fact Table** for transactional metrics


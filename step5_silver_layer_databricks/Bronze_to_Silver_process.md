# Step 5: Silver Layer Transformation using Databricks

## ✅ Objective
To convert raw, uncleaned data from the Bronze layer into a structured, deduplicated, and typed dataset, stored in the Silver layer for analytical use.

---

## 🧠 Summary of Steps

### 1. Read Data from Bronze Layer
- Loaded raw Delta-format data stored in the `/bronze/rawdata` container using Databricks and PySpark.

### 2. Cleaned the data
- Removed comma from quantity using regex

### 3. Cast Data Types
- Converted string-based columns to appropriate types:
  - Dates to `DateType`
  - Profit to `float`, etc.

### 4. Apply Transformations
- Renamed columns for consistency.
- Derived new columns such as `Year` and `Month` from date fields for partitioning and analysis.

### 5. Write to Silver Layer
- Saved the cleaned and transformed data as a Delta table in `/silver/silverdata` in the parquet format.
- Used overwrite mode to ensure up-to-date, versioned storage.

---

## 📄 Output
- A refined Silver-level Delta table ready for star schema modeling in the Gold layer.

---

## 📁 Related Files

- 🧠 Notebook File: [Silver.ipynb](./Silver.ipynb)

➡️ Next: [Step 6 & 7 – Gold Layer Star Schema](../step6_gold_star_schema/Dimension_Tables.md)

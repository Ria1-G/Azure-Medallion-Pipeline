
# Step 4.4 & 4.5: Copy Activity – Incremental Load into Bronze

## ✅ Objective
Filter data using date range and ingest only new records into **Bronze layer** (ADLS) in **Parquet format**.

---

## ⚙️ Configuration Overview

### 🔹 Source:
- SQL Database
- **Query**: Uses `@lastload` parameter from Lookup 1
```sql
SELECT * 
FROM adidas_sales 
WHERE Invoice_Date > '@{activity('min_value').output.value[0].last_load}' 
  AND Invoice_Date <= '@{activity('max_value').output.value[0].max_date}'

```
#### ✅Core of Incremental Logic
- This query is used in the Source tab of my Copy Data activity to:
- Fetch only new records greater than the last load date (min_value)
- And restrict to current load’s max (max_value)
---

### 🔹 Sink
- Target: Azure Data Lake Storage Gen2
- Path: `bronze/rawdata/`
- Format: Parquet
- Linked Service: Azure Storage Account

## Screenshots

1. Source Query

    ![alt text](/images/images4/image43.png)

2. Sink – Store in the bronze container in data lake in parquet format
  
   - Linked service 

    ![alt text](/images/images4/image-431.png)

    ![alt text](/images/images4/image-432.png)

3. Successful debug

    ![alt text](/images/images4/image-433.png)

4. Bronze layer

    ![alt text](/images/images4/image-434.png)

---

---

## 📁 Related Files

- 🧾 Pipeline JSON: [incremental_load.json](./incremental_load.json)

➡️ Next: [Step 4.6 – Stored Procedure: Update WaterTable](./4_StoredProcedure_Update.md)

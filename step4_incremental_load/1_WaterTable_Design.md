# Step 4.1: WaterTable Design – Tracking Last Load Date

## ✅ Objective
Create a WaterTable in the Azure SQL Database to track the `MIN(invoice_date)` for incremental load processing.

---

## 🧠 Why WaterTable?
- Helps identify the earliest date in the raw dataset
- Used by ADF to filter data during incremental runs
- Updated dynamically after each pipeline execution

---

## 🛠️ Table Structure
```sql
CREATE TABLE WaterTable (
  lastload varchar(2000)
);
```
---

## Screenshots

![alt text](/images/image41.png)

---

## 💡 Notes
- WaterTable must be created before running incremental pipeline
- It enables filtering new records based on invoice_date

---

- ➡️ Next: [Step 4.2 – Lookup Activities](./2_Lookup_Activities.md)


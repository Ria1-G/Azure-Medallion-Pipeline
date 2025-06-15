
### 📄 `Lookup_Activities.md`


# Step 4.2 & 4.3: Lookup Activities – Min & Max Date

## ✅ Objective
Configure two Lookup activities in ADF to support incremental filtering:
- Lookup 1: Fetch `MIN(invoice_date)` from `WaterTable`
- Lookup 2: Fetch `MAX(invoice_date)` from the main SQL table

---

## 🔍 Lookup 1: Min Date from WaterTable
**Query:**
```sql
SELECT lastload FROM WaterTable;

```
---

## 🔍 Lookup 2: Max Date from SQL Table
**Query:**
```sql
SELECT MAX(invoice_date) AS maxdate FROM rawdata;

```
---

## Screenshots

1. Lookup-1 
    
    ![alt text](/images/images4/image42.png)

    ![alt text](/images/images4/image-421.png)

    ![alt text](/images/images4/image-422.png)

    ![alt text](/images/images4/image-424.png)

    ![alt text](/images/images4/image-425.png)

2. Lookup-2

    ![alt text](/images/images4/image-426.png)

    ![alt text](/images/images4/image-427.png)

    ![alt text](/images/images4/image-428.png)

    ![alt text](/images/images4/image-429.png)


---
## 🧠 Notes
- Use Lookup output as pipeline parameter (via dynamic content)
- Result should be treated as a single-row JSON object

---

- ➡️ Next: [Step 4.3 – Copy_Activity_Bronze](./3_CopyActivity_Bronze.md)
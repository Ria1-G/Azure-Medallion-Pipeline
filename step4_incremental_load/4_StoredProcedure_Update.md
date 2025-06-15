# Step 4.6: Stored Procedure – Update WaterTable

## ✅ Objective
Update the `lastload` column in the WaterTable after each successful incremental pipeline execution.

---

## 🛠️ Stored Procedure Script
```sql
CREATE PROCEDURE updatewatertable
    @lastload VARCHAR(2000)
AS
BEGIN
    BEGIN TRANSACTION
        UPDATE [dbo].[watertable]
        SET last_load = @lastload;
    COMMIT TRANSACTION
END;

```

---

## ✅ Outcome
- WaterTable now reflects the most recent date loaded
- This enables correct filtering in the next pipeline run

---

## Screenshots

1. ![alt text](/images/images4/image44.png)

2. Set the value of @lastload variable

    ![alt text](/images/images4/image-441.png)

3. ![alt text](/images/images4/image-442.png)

4. Successful implementation of incremental load

    ![alt text](/images/images4/image-443.png)

    ![alt text](/images/images4/image-444.png)

---

---

## 📁 Related Files

- 🧾 Download Pipeline JSON with Stored Procedure: [incremental_load_with_stored_proc.json](./json/incremental_load_with_stored_procedure.json)

➡️ Next: [Step 5 – Silver Layer Transformation using Databricks](./step5_silver_layer_databricks/Silver_Layer_Transformation.md)


# Step 2: Azure SQL Database Setup

## ✅ Objective
Create a SQL Database to store ingested data from ADF and support downstream transformation.

---

## 💡 Why Azure SQL DB?
- Fully managed and serverless options
- Works well with ADF, Databricks, and Power BI
- Supports T-SQL queries and stored procedures

---

## 🔧 Steps

1. Azure Portal → Search `SQL Databases` → `+ Create`
2. Choose:
   - **Subscription**: your Azure subscription 1
   - **Resource Group**: `riaresource`
   - **Database Name**: `riadatabase`
3. Click `Create new server`:
   - Server name (globally unique)
   - Admin username and password
   - Region same as Resource Group
4. Select **Basic**  tier (cost-efficient)
5. Configure Networking:
   - Set to **Public endpoint**
   - Allow Azure services and current IP access
6. Click `Review + Create` → Create

---

## 🧠 Post-Deployment

### Query Editor (in Azure Portal)
- Login using the admin credentials

### Create raw table:
```sql
CREATE TABLE adidas_sales (
    Retailer VARCHAR(2000),
    Retailer_ID VARCHAR(2000),
    Invoice_Date VARCHAR(2000),
    Region VARCHAR(2000),
    State VARCHAR(2000),
    City VARCHAR(2000),
    Product VARCHAR(2000),
    Price_per_Unit VARCHAR(2000),
    Quantity VARCHAR(2000),
    Profit VARCHAR(2000)
);


```
---
## Screenshots

1. ![alt text](/images/image-1.png)

2. ![alt text](/images/image-2.png)

3. CREATE A NEW SERVER AND SET ADMIN DETAILS

    ![alt text](/images/image-3.png)

    ![alt text](/images/image-4.png)

4. CONFIGURE DATABASE  SERVICE TIER TO REDUCE COSTS
  
    ![alt text](/images/image-5.png)

5. SET CONNECTIVITY METHOD TO PUBLIC ENDPOINT ANS SET THE 2 OPTIONS TO YES
 
    ![alt text](/images/image-6.png)

6. REVIEW + CREATE

    ![alt text](/images/image-8.png)

    ![alt text](/images/image-9.png)

7. SQL QUERY

   ![alt text](/images/image-7.png)

---

➡️ Next: [ADF_Pipeline_Ingestion.md](./3_ADF_Pipeline_Ingestion.md)

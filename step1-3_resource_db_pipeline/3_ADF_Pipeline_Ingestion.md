
# Step 3: Azure Data Factory Pipeline - Initial Ingestion

## ✅ Objective
Create a pipeline in Azure Data Factory to ingest data from a web source into SQL Database.

---

## 🚀 Steps

### 1. Create ADF Instance
- Go to Azure Portal → Search **Data Factory**
- Click **+ Create**
- Enter:
  - Name: `riaadf`
  - Region: Same as Resource Group
  - Git: Skip for now
- Review + Create → Deploy

### 2. Open ADF Studio
- Click `Author & Monitor`

### 3. Create Pipeline
- Go to **Author** → `+ Pipeline`
- Name: ``pipeline1` for Initial Load

### 4. Add Copy Activity

#### Source (HTTP):
- Click `+ New` → Choose HTTP
- Base URL: enter the web data host
- Add Relative URL to point to exact file
- Choose file format (CSV)
- Authentication: anonymous/key
- Test connection succeeded

#### Sink (SQL):
- Click `+ New` → Azure SQL DB
- Fill server name, DB name, login credentials
- Select `rawdata` table
- Test connection → Save

### 5. Debug Pipeline
- Use the **Debug** button
- Wait for success
- Confirm data is visible in `rawdata` table

---

## 📄 Notes from `PROJECT_SS_REF_1-3.docx`
- The pipeline links HTTP → SQL using Linked Services
- Format and Relative URL were configured during setup
- Debug confirmed successful ingestion

---

## ✅ Output
- Web data is now flowing into SQL DB's raw table
- Foundation (Bronze layer) for further processing is ready

---

## Screenshots

1. CREATE ADF

    ![alt text](/images/image2.png)

    ![alt text](/images/image-21.png)

2. CREATE A PIPELINE IN ADF

    ![alt text](/images/image-22.png)

3. SOURCE (HTTP)

    ![alt text](/images/image-23.png)

    ![alt text](/images/image-24.png)

4. SINK (AZURE SQL)

    ![alt text](/images/image-25.png)

    ![alt text](/images/image-26.png)

    ![alt text](/images/image-27.png)

5. SUCCESSFUL DEBUG

    ![alt text](/images/image-28.png)

    ![alt text](/images/image-29.png)

6. SUCCESSFUL INGESTION OF DATA

    ![alt text](/images/image-30.png)

---

➡️ Next: [../step4_incremental_load/WaterTable_Design.md](../step4_incremental_load/WaterTable_Design.md)

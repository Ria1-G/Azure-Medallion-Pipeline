# Step 1: Azure Resource Group Setup

## ✅ Objective
To create an Azure Resource Group to organize and manage all components of the Medallion Architecture Pipeline in a logical container.

---

## 💪 Why Resource Group?
- Acts as a container for all related Azure services (SQL, ADF, Storage, Databricks)
- Enables unified billing, monitoring, and role-based access
- Easy to delete or clone entire environments

---

## 💡 Prerequisites
- Active Azure subscription
- Access to [Azure Portal](https://portal.azure.com)

---

## 🔧 Steps to Create Resource Group

1. Log in to [Azure Portal](https://portal.azure.com)
2. Search for `Resource groups` in the search bar
3. Click `+ Create` (top left)
4. Fill in:
   - **Subscription**: Azure_Subscription_1
   - **Resource group name**: `riaresource`
   - **Region**: Central India
5. Click **Review + Create** → **Create**

---

## 📝 Notes
- This step initializes the container for all subsequent resources

---

## 🚀 Output
A clean Resource Group ready to hold:
- Azure SQL DB
- Azure Data Factory
- Azure Storage
- Azure Databricks

---

## Screenshots
![alt text](/images/image.png)

➡️ Next: [SQLDatabase_Setup.md](./2_SQLDatabase_Setup.md)

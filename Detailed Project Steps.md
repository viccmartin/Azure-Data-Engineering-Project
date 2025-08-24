## Detailed Project Steps  

### A. Prerequisites & On-Premises Setup  
1. Install **SQL Server & SSMS**.  
2. Restore **AdventureWorksLT2022** database.  
3. Configure **external access** to SQL Server.  
4. Create SQL user with permissions.  
5. Store **credentials in Azure Key Vault**.  

### B. Azure Environment Setup (Step 1)  
1. Create **Resource Group**.  
2. Provision services:  
   - **ADF**  
   - **ADLS** (with Bronze, Silver, Gold containers)  
   - **Databricks Workspace**  
   - **Synapse Analytics Workspace**  

### C. Data Ingestion (Step 2)  
1. Connect **ADF to SQL Server On-Prem** using **Self-Hosted Integration Runtime (SHIR)**.  
2. Use **Lookup + ForEach + Copy Data** activities to dynamically copy all tables into **Bronze layer** in ADLS.  

### D. Data Transformation (Step 3)  
1. Set up **Databricks cluster**.  
2. Mount **ADLS containers** in Databricks.  
3. **Bronze → Silver**: Format dates.  
4. **Silver → Gold**: Convert column names to snake_case.  
5. Automate **Databricks notebooks** via ADF pipelines.  

### E. Data Loading & Reporting (Step 4)  
1. Configure **Synapse Analytics** with SQL serverless DB.  
2. Create **views** from **Gold layer**.  
3. Automate **view creation** via pipelines.  
4. Build **Power BI Dashboard** with:  
   - KPIs: total sales, total products  
   - Donut chart: gender breakdown  
   - Slicers: category, gender, date filters  

### F. Automation & Monitoring (Step 5)  
- Schedule **ADF pipeline** daily via triggers.  
- Monitor pipelines in **ADF & Synapse Studio**.  

### G. Security & Governance (Step 6)  
- Use **RBAC with Entra ID** for access control.  
- Store secrets only in **Key Vault**.  

### H. End-to-End Testing (Step 7)  
1. Insert new records in **on-prem SQL**.  
2. Verify **Power BI dashboard updates** after scheduled pipeline run.  

---

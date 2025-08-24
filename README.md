# Data Engineering Project in Azure  

## Project Overview  

This project is a comprehensive **data engineering pipeline solution in Azure**, designed to address a key business need. The main objective is to **extract customer and sales data from an on-premises SQL database**, transform it in the cloud, and generate **actionable insights through a Power BI dashboard**.  

The project aims to:  
- Create a **business context** to understand the reasoning behind the data transformations.  
- **Resolve common errors and issues** that typically arise in these types of projects.  
- Provide a tangible output and **demonstrate understanding of the entire data engineering process**, from source to final reporting.  
- Ensure the pipeline **runs automatically every day**, so stakeholders always have access to updated and accurate data.  



## Business Requirements  

The company has identified a **gap in understanding their customers’ demographics**, specifically the **gender distribution and how this might influence product purchases**.  

Key requirements for the KPI dashboard include:  
- **Sales by Gender and Product Category**: Must show the **total products sold**, the **total sales revenue**, and a **clear breakdown by customer gender**.  
- **Data Filtering**: Support **filtering by product category, gender, and date-based queries**.  
- **User-Friendly Interface**: Must be **intuitive and easy to use** for stakeholders.  



## Solution Components (Pipeline Architecture)  

The solution involves a **robust data pipeline** that extracts, loads, and transforms data, feeding into a customized report. The pipeline architecture follows the **Bronze, Silver, and Gold** layered approach in the Data Lake.  

### Data Ingestion  
- **Extract data** from on-premises SQL Server.  
- **Load data** into **Azure Data Lake Storage (ADLS)** via **Azure Data Factory (ADF)**.  
- Store **raw data** in the **Bronze layer**.  

### Data Transformation  
- **Clean and transform data** with **Azure Databricks**.  
- **Silver layer**: Minor transformations (e.g., type conversions, date formatting).  
- **Gold layer**: Query-optimized data with **user-friendly column names**.  

### Data Loading and Reporting  
- **Load transformed data** into **Azure Synapse Analytics**.  
- **Build a Power BI dashboard** for visualization and insights.  

### Automation  
- **Daily scheduled runs** via **ADF** to ensure data freshness.  

### Security and Governance  
- **Azure Key Vault** for secret and credential management.  
- **Azure Entra ID** (formerly Azure Active Directory) for **RBAC** (role-based access control).  



## Technology Stack  

- **Azure Data Factory (ADF)**: Data orchestration  
- **Azure Data Lake Storage (ADLS) Gen2**: Data storage (Bronze, Silver, Gold)  
- **Azure Databricks**: Data transformation with **PySpark**  
- **Azure Synapse Analytics**: Data warehousing & queries  
- **Power BI**: Business Intelligence dashboards  
- **Azure Key Vault**: Secure secrets management  
- **SQL Server (On-Premises)**: Source database (AdventureWorksLT2022)  
- **SQL Server Management Studio (SSMS)**: SQL Server admin tool  
- **Python**: For transformations in Databricks  
- **Data Visualization**: Charts, KPIs, interactive dashboards  
- **Automation**: ADF triggers for scheduling  
- **Data Governance & Security**: Policies for secure access  

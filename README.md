# Data-Engineering-on-Azure-cloud

## **Project onjective
To explore Microsoft Azure services and build ETL pipleines to analyze the data and produce dashboards in Power BI.

Dataset: The dataset used is Olympic Data from Kaggle, which contains details about athletes, coaches, medals, teams, and gender participation in the 2021 Tokyo Olympics.

---

## **Services Used**

- **Azure Data Factory** is used to ingest data from source point.
- **Azure Databricks (Apache Spark)** for scalable data transformations.
- **Azure Data Lake Storage (ADLS Gen2)** for cost-effective data storage.
- **Azure Synapse Analytics** a powerful data warehouse for large-scale SQL queries.
- **Power BI** in data visualization and reporting.



### **Project Workflow**
The data pipeline follows the **ETL (Extract, Transform, Load)** process using the following Azure services:

1. Ingestion → **Azure Data Factory** → Raw Data (ADLS Gen2)
2. Transformation → **Azure Databricks** → Transformed Data (ADLS Gen2)
3. Analytics → **Azure Synapse Analytics**
4. Visualization → **Power BI**

1. **Extract Data (Ingestion)**
   - **Azure Data Factory (ADF)** is used to extract raw data from a GitHub repository.
   - The dataset includes five CSV files (athletes, coaches, medals, teams, entries_gender).
   - ADF moves the raw data into **Azure Data Lake Storage Gen2 (ADLS Gen2)** for further processing.

2. **Transform Data**
   - **Azure Databricks (Apache Spark)** is used to clean and transform the raw data.
   - Transformation steps include:
     - Converting incorrect data types (e.g., strings to integers).
     - Removing duplicates and renaming columns.
     - Computing aggregated statistics such as top countries by gold medals.
   - The transformed data is written back to **Azure Data Lake Storage (ADLS Gen2)**.

3. **Load and Analysis**
   - **Azure Synapse Analytics** is used to query transformed data.
   - Used SQL-based querying and  charts view  to gain insights from the dataset.
   - The processed data is visualized using **Power BI**.
     
4. **Dashboard and Reporting**
   - A dashboard is created to visualize key insights, such as:
     - Top countries with the most medals.
     - Gender participation by discipline.
     - Distribution of medals across different sports.

---

## **Step-by-Step Execution**

### **Step 1: Data Ingestion using Azure Data Factory**
- **Create Azure Data Factory** to manage data pipelines.
- **Create a Storage Account** and a **Data Lake Storage Gen2** container to store the files.
- **Set up a Data Pipeline** in ADF:
  - **Source:** GitHub (HTTP connector)
  - **Destination:** ADLS Gen2 (Raw Data Folder)
- **Pipeline Execution:** Runs successfully and stores the raw data.
- Used ADF (source and sink connections) to load the raw data files from the google drive src usig HTTP connector to storage datalake raw_data.

### **Step 2: Data Transformation using Azure Databricks**
- **Create an Azure Databricks Workspace** and configure a Spark cluster.
- **Mount the Data Lake Storage to Databricks** using Service Principal authentication.
- **Read Data using Apache Spark (PySpark)**
  - Print schema to verify column types.
  - Converted data types where necessary (e.g., medals count from string to integer).
  - Filtered and grouped data where needed for insights.

### **Step 3: Load Transformed Data to ADLS**
- The transformed data is written back to **ADLS Gen2 (Transformed Data Folder)**.
- Data is stored in CSV format with partitioning.

### **Step 4: Data Analysis with Azure Synapse Analytics**
- **Create a Synapse Analytics Workspace**.
- **Load the transformed data into Synapse Tables**.
- **Run SQL queries to extract insights**, such as:
  - Ranking countries by medal count.
  - Finding the top athlete in each discipline.

### **Step 5: Data Visualization using Power BI / Looker / Tableau**
- **Connect Power BI to Synapse Analytics**.
- **Create dashboards** to visualize key insights.
- **Publish Reports** for stakeholders.



---

This project demonstrates a **real-world data engineering workflow** in **Azure Cloud**, integrating multiple services for **data ingestion, transformation, storage, analysis, and visualization**.

Would you like to add any **additional details or improvements** to this summary? 🚀

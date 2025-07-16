
# Sales ETL & BI Pipeline  

## Table of Contents  
1. [Project Overview](#project-overview)  
2. [Tech Stack](#tech-stack)  
3. [ETL & BI Workflow](#etl--bi-workflow)  
4. [Repository Structure](#repository-structure)  
5. [Prerequisites](#prerequisites)  
6. [Configuration](#configuration)  
7. [How to Run](#how-to-run)  
8. [Dashboard Sample](#dashboard-sample)  
9. [Clean-Up](#clean-up)  
10. [Acknowledgments](#acknowledgments)  
11. [Conclusion](#conclusion)  


---

## Project Overview  

I built this **Sales ETL & BI Pipeline** to automate a complete data engineering workflow:  
- Extracting multi-table sales data from **SQL Server**  
- Transforming it using **Python**  
- Orchestrating the pipeline with **Apache Airflow** running in **Docker**  
- Loading it into **Google BigQuery**  
- Visualizing insights using **Looker Studio**  

This end-to-end pipeline runs on **Google Cloud Platform (GCP)** with scheduled automation and scalable architecture.  

---

## Tech Stack  

- **Python** — Data extraction and transformation  
- **Apache Airflow** — Workflow orchestration and scheduling  
- **Docker** — Airflow deployment in isolated containers  
- **Google BigQuery** — Cloud data warehousing  
- **Looker Studio** — Business Intelligence dashboards  
- **Google Cloud Platform (GCP)** — Cloud hosting and services  

---

## ETL & BI Workflow  

1. **ETL with Apache Airflow**  
   - Extract data from **SQL Server**  
   - Transform it with **Python** scripts  
   - Load into **Google BigQuery**  

2. **BI with Looker Studio**  
   - Connect Looker Studio directly to **BigQuery**  
   - Build interactive dashboards with automated refresh  

![Sales Data Pipeline](images/sales_Data_pipeline.png)  

---

## Repository Structure  

```bash
sales_etl_bi_pipeline/
│   etl_script.ipynb
│   README.md
│   vocal-raceway-400113-7e5d84b42be1.json
│
├───airflow_installation/
│       docker-compose.yml
│       Dockerfile
│
└───images/
        connection_mssql.png
        data_in_bigQuery.png
        project_metadata.png
        Sales_Dashboard.jpg
        sales_Data_pipeline.png
        sales_data_sqlserver.png
```

---

## Prerequisites  

Before you start, make sure you have the following installed and set up:  

- **Python 3.x** — For running ETL scripts  
- **Docker** — To run Apache Airflow inside containers  
- **Google Cloud Platform (GCP) account** — With **BigQuery** access  
- **Looker Studio account** — For dashboard creation  
- **SQL Server database** — Containing the sales data to be processed  

---

## Configuration  

### ETL Script Setup  

In `etl_script.ipynb`, update the following variables:  
- `BIGQUERY_PROJECT_ID` — Your GCP project ID  
- `BIGQUERY_DATASET_ID` — Target dataset in BigQuery  

### Apache Airflow Setup  

- Define environment variables inside `docker-compose.yml`  
- Access the **Airflow UI** → **Admin → Connections**  
  - Create a new **MSSQL connection** with your database credentials  

### BigQuery Authentication  

- Place your **GCP service account JSON file** (`vocal-raceway-400113-7e5d84b42be1.json`) in the project root directory  
- Ensure this file is used for authentication when running the ETL pipeline  

---

## How to Run  

1. **Ensure Your SQL Server Has Sales Data**  

![SQL Server Data](images/sales_data_sqlserver.png)  

2. **Start Apache Airflow with Docker**  

```bash
docker-compose up -d
```  

3. **Access Airflow Web UI at** [http://localhost:8080](http://localhost:8080)  

- Go to **Admin → Connections** and create the **MSSQL connection**  

![MSSQL Connection](images/connection_mssql.png)  

4. **Trigger the ETL DAG** inside Airflow  

5. **Check Data in BigQuery After Load**  

![Data in BigQuery](images/data_in_bigQuery.png)  

6. **Connect Looker Studio to BigQuery** and build your dashboards  

---

## Dashboard Sample  

Here is a sample of the interactive **Sales Dashboard** I created using **Looker Studio**:  

![Sales Dashboard](images/Sales_Dashboard.jpg)  

---

## Clean-Up  

To stop and clean up after running the project:  

- Stop Airflow Docker containers:  

```bash
docker-compose down
```  

- Optionally, delete datasets in **BigQuery** and clean up unused resources on **GCP**  

---

## Acknowledgments  

Special thanks to the developers and communities behind these tools that made this project possible:  

- **Apache Airflow** — For orchestrating workflows  
- **Python** — For data manipulation and transformation  
- **Google BigQuery** — For cloud data storage and querying  
- **Looker Studio** — For interactive dashboards and BI reporting  

---

## Conclusion  

This project gave me hands-on experience in:  

- Building and automating ETL pipelines with **Airflow**  
- Managing cloud data warehouses with **BigQuery**  
- Running containerized workflows using **Docker**  
- Visualizing business data through **Looker Studio** dashboards  

It reflects my ability to integrate multiple cloud and open-source tools to deliver automated, scalable data solutions.  

---


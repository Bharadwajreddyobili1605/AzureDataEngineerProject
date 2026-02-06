# AzureDataEngineerProject-Spotify

## Project Overview
This project demonstrates an end-to-end data engineering pipeline for Spotify data using Azure Data Platform and Databricks. The goal is to ingest data from a source system, process it through a Medallion Architecture (Bronze, Silver, Gold), and make it available for business analytics and reporting.
The solution is designed to be scalable, dynamic, and production-ready, handling both initial and incremental data loads, along with advanced ingestion patterns like CDC, backdated refresh, and backfilling.

## Architecture Overview
The project follows the Medallion Architecture:
      Bronze (Raw Layer) – Raw ingested data stored in ADLS Gen2
      Silver (Cleaned Layer) – Transformed and deduplicated data
      Gold (Serving Layer) – Business-ready data models for reporting

## Data Ingestion
### Source System
    - Azure SQL Database (Spotify source data)
### Ingestion Tool
    - Azure Data Factory (ADF)
### Ingestion Strategy
    - The ingestion process is built to handle multiple real-world scenarios:
    - Initial Load – Full load of historical data from Azure SQL Database
    - Incremental Load – Loads only new or changed data
    - Change Data Capture (CDC) – Captures inserts, updates, and deletes
    - Backdated Refresh – Reloads historical data for a given date range
    - Backfilling – Handles late-arriving or missing data
ADF pipelines are designed to be dynamic and parameterized, enabling reusable and flexible ingestion workflows.

## Bronze Layer (Raw)
    - Data ingested from Azure SQL is stored in Azure Data Lake Storage Gen2 (ADLS Gen2)
    - Raw data is stored with minimal transformations
    - Preserves source data for audit and reprocessing
    - Acts as the single source of truth
## Silver Layer (Transformation)
    - The Silver layer focuses on data quality and transformation using Databricks:
    - Removal of duplicate records
    - Data cleansing and standardization
    - Application of required business transformations
    - Schema enforcement and validation
## Gold Layer (Serving)
    - Implemented using Declarative Pipelines (Delta Live Tables)
    - Aggregated and business-friendly data models
    - Optimized for BI, reporting, and analytics
    - Serves data to business users and reporting tools

## Key Features
End-to-end data engineering pipeline
Dynamic and reusable ingestion pipelines
Supports CDC, backdated refresh, and backfilling
Medallion architecture implementation

## Technologies Used
 - Azure SQL Database – Source system
 - Azure Data Factory (ADF) – Data ingestion and orchestration
 - Azure Data Lake Storage Gen2 (ADLS Gen2) – Data storage
 - Azure Databricks – Data processing and transformations
 - Delta Lake / Delta Live Tables – Declarative p







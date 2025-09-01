# ECommerce-ELT-Data-Pipeline-Using-Azure-Medallion-Architecture
An end-to-end data engineering project on Azure (Data Factory, Data Lake, Databricks) using the Medallion Architecture (Bronze, Silver, Gold) and Delta Lake to ensure reliable, efficient, and large-scale e-commerce data analytics.

# Dataset : 
E-commerce - Users of a C2C fashion store : [data.world](https://data.world/jfreex/e-commerce-users-of-a-french-c2c-fashion-store).

# Tech Stack Used :

Azure Data Factory (ADF)
Used as the orchestration tool to automate data movement. ADF pipelines ingest raw CSV/Parquet files into Azure Data Lake Storage and trigger Databricks notebooks for downstream processing.

Azure Data Lake Storage Gen2 (ADLS)
Serves as the central data lake for storing both raw and curated datasets. It provides scalable, secure, and cost-effective storage with hierarchical namespace support for organizing Bronze, Silver, and Gold layers.

Azure Databricks
The processing engine of the pipeline, where PySpark is used to transform data. Databricks provides collaborative notebooks, auto-scaling clusters, and seamless integration with Delta Lake for handling large-scale analytics.

Delta Lake
An open-source storage layer built on top of ADLS that brings reliability to data lakes. Delta Lake provides ACID transactions, schema enforcement, schema evolution, and time travel, making data pipelines more scalable and production-ready.


# Medallion Architecture :

The Medallion Architecture is a layered approach to organizing data pipelines in Databricks:

Bronze Layer
Stores raw, ingested data exactly as it arrives (append-only). This ensures no information is lost and serves as the single source of truth for all downstream layers.

Silver Layer
Contains cleaned, deduplicated, and conformed data. Business rules and schema enforcement are applied here to make the data more consistent and reliable.

Gold Layer
Provides aggregated, business-level datasets optimized for reporting and analytics (e.g., user activity by region, sales performance by category). This layer is what dashboards, BI tools, or machine learning models consume.

# real-time-stock-market-data-engineer-project
In this project, we’ll build a real-time stock market data pipeline using Snowflake, DBT, and Apache Airflow. We’ll stream live market data from an API, orchestrate transformations, manage data in Snowflake, and deliver powerful visualizations — creating a portfolio-ready project that makes you stand out.

<img width="5889" height="3500" alt="image" src="https://github.com/user-attachments/assets/719784c3-958f-4649-aadb-63f36adad361" />

## Technology Used

- Docker → Containerization
- Apache Kafka → Real-time Streaming
- MINio → Open source S3 Bucket
- Snowflake → Cloud Data Warehouse
- DBT → SQL-based Transformations
- Apache Airflow → Workflow Orchestration
- Python → Data Fetching & API Integration
- Power BI → Data Visualization

## Key Features

- Fetching live stock market data (not simulated) from an API
- Real-time streaming pipeline with Kafka
- Orchestrated ETL workflow using Airflow
- Transformations using DBT inside Snowflake
- Scalable cloud warehouse powered by Snowflake
- Analytics-ready Power BI dashboards

## Step-by-Step Implementation

***1. Kafka Setup***
- Configured **Apache Kafka** locally using Docker.
- Created a **stocks-topic** to handle live stock market events.
- Defined producers (API fetch) and consumers (pipeline ingestion).

***2. Live Market Data Producer***
- Developed **Python producer script** `stock_producer.py` to fetch **real-time stock prices** from the **Finnhub API** using an API key.
- Streams stock data into Kafka in JSON format.

***3. Kafka Consumer → MinIO***
- Built **Python consumer script** `stock_consumer.py` to consume streaming data from Kafka.
- Stored consumed data into **MinIO buckets** (S3-compatible storage).
- Organized storage into folders for **raw/bronze layer ingestion**.


***4. Airflow Orchestration***
- Initialized **Apache Airflow** in Docker.
- Created DAG (`stock_pipeline_dag.py`) to:
  - Load data from MinIO into **Snowflake staging tables** (Bronze).
  - Schedule automated runs every **1 minute**.

***5. Snowflake Warehouse Setup***
- Created **Snowflake database, schema, and warehouse**.
- Defined staging tables for **Bronze → Silver → Gold** layers.
- SQL scripts available at:

***6. DBT Transformations***
- Configured **DBT project** with Snowflake connection.
- Models include:
  - Bronze models → raw structured data
  - Silver models → cleaned, validated data
  - Gold models → analytical views (Candlestick, KPI, Tree Map)

***7. Power BI Dashboard***
- Connected **Power BI** to Snowflake (Gold layer) using **Direct Query**.
- Built:
  - **Candlestick chart** → stock market patterns
  - **Tree chart** → stock price trends
  - **gauge charts** → stock volume & total sales breakdown
  - **KPI's** → real-time sortable view

## Final Deliverables
- **Automated real-time data pipeline**
- **Snowflake tables (Bronze → Silver → Gold)**
- **Transformed analytics models with DBT**
- **Orchestrated DAGs in Airflow**
- **Power BI dashboard with live insights**

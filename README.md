# Real-Time Log Analytics using AWS

A fully serverless real-time log analytics pipeline using AWS services including **S3**, **Glue**, **Athena**, and **Python**.  
This project simulates real-time server logs, stores them in Amazon S3, creates schema using AWS Glue Crawlers, and performs SQL-based queries over logs using Amazon Athena.

---



## 🎯 Objective

To design a real-time data pipeline that:
- Collects and stores server logs
- Automatically detects schema
- Enables SQL queries over logs 

---

## 🔧 Tech Stack

| Component       | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| Python + Boto3  | Simulate HTTP server logs and upload as `.parquet` to S3                   |
| Amazon S3       | Central storage for logs in time-partitioned folders (`/YYYY/MM/DD/HH/`)   |
| AWS Glue        | Crawls S3 data, detects schema, and creates Data Catalog                   |
| Amazon Athena   | Queries `.parquet` log data directly from S3 using serverless SQL engine   |

---

## 🔁 Pipeline Flow

```text
Server Logs (Simulated using Python)
            ↓
.parquet Files (every 10s)
            ↓
Amazon S3 (partitioned by time)
            ↓
AWS Glue Crawler (schema detection)
            ↓
Amazon Athena (SQL over S3)

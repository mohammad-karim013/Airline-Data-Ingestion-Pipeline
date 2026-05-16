# Airline-Data-Ingestion-Pipeline
End-to-End Automated Daily Flight Data ETL Pipeline using AWS S3, Glue, Step Functions &amp; Redshift

# Airline Daily Data Ingestion Pipeline

**End-to-End Automated ETL Pipeline**
End-to-End Automated ETL Pipeline for ingesting daily flight data from S3 into Amazon Redshift using modern AWS services.
<img width="1861" height="522" alt="image" src="https://github.com/user-attachments/assets/6d4f4624-5233-430a-a53e-fe95c76b437b" />


## 🚀 Project Overview

This project demonstrates a complete **serverless data pipeline** that automatically ingests, transforms, and loads daily flight data into a Redshift data warehouse.

## 🛠 Tech Stack

- **Storage**: Amazon S3 (Raw & Partitioned data)
- **Event Triggering**: Amazon EventBridge + S3 Events / CloudTrail
- **Data Catalog**: AWS Glue Data Catalog
- **Crawler**: AWS Glue Crawlers (Dim & Fact)
- **ETL Processing**: AWS Glue Visual ETL (Spark-based)
- **Orchestration**: AWS Step Functions
- **Notification**: Amazon SNS
- **Data Warehouse**: Amazon Redshift
- **Monitoring**: AWS CloudWatch

## 📊 Architecture Flow

1. Daily CSV files arrive in S3 (`daily_raw/date=YYYY-MM-DD/`)
2. EventBridge detects new file and triggers Step Function
3. Glue Crawler updates schema
4. Glue Visual ETL Job performs data transformation + joins with dimension tables
5. Clean data is loaded into Redshift Fact Table
6. Success/Failure notification sent via SNS

## ✨ Key Features

- Fully automated daily ingestion pipeline
- Partitioned data loading for better performance
- Star Schema design (Dimension + Fact tables)
- Robust error handling and retry mechanism using Step Functions
- Proper logging and monitoring
- Scalable and production-ready architecture

## 📸 Screenshots

![Step Function Workflow](screenshots/step-function.png)
![Glue ETL Job](screenshots/glue-visual-etl.png)
![Redshift Data](screenshots/redshift-query-result.png)

## 🗄 Database Schema

- **Schema**: `airlines`
- **Dimension Table**: `airports_dim`
- **Fact Table**: `daily_flights_fact` (~2 Million records loaded)

## 📁 SQL Queries

Check `src/sql/` folder for:
- Table creation scripts
- Analysis & validation queries

## 🚀 How to Run the Pipeline

1. Upload CSV file in `daily_raw/date=YYYY-MM-DD/` folder
2. EventBridge triggers Step Function automatically
3. Monitor execution in Step Functions console
4. Check data in Redshift Query Editor

## 📈 Future Enhancements

- Incremental data loading using CDC
- Data quality validation using AWS Deequ
- Infrastructure as Code using Terraform
- Dashboard using Amazon QuickSight
- Cost optimization

## 🧑‍💻 Author

**Mohammad Karim**  
AWS Certified | Data Engineer

---

**⭐ Feel free to star this repository if you find it helpful!**

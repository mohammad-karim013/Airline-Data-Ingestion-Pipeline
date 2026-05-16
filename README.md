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

**Storage: Amazon S3 (Raw & Partitioned data)**
Amazon S3 is used as the central raw storage layer. It stores incoming flight CSV files in a partitioned structure for better performance and scalability.
<img width="1532" height="458" alt="image" src="https://github.com/user-attachments/assets/f4863c7a-980e-4f63-8a70-0d82ce9b6512" />

 **Event Triggering: Amazon EventBridge + S3 Events / CloudTrail**
 Amazon EventBridge detects new flight data files uploaded to S3 and automatically triggers the Step Functions pipeline for processing.

**Data Catalog: AWS Glue Data Catalog**
AWS Glue Data Catalog serves as the central metadata store for all tables and schemas used in the pipeline.

**Crawler: AWS Glue Crawlers (Dim & Fact)**
AWS Glue Crawlers (for Dimension & Fact data) automatically discover schema from S3 files and maintain metadata in Data Catalog.

<img width="1557" height="390" alt="image" src="https://github.com/user-attachments/assets/082040c2-6a53-40d7-b6a5-e841d3371b2b" />

**ETL Processing: AWS Glue Visual ETL (Spark-based)**
AWS Glue Visual ETL (Spark-based) handles data transformation, joins, and loads clean data into Amazon Redshift.

<img width="756" height="550" alt="image" src="https://github.com/user-attachments/assets/46bfe990-4944-4311-914a-818677cab3f3" />

**Orchestration: AWS Step Functions**
AWS Step Functions orchestrates and manages the complete end-to-end workflow of the data ingestion pipeline.
<img width="882" height="573" alt="image" src="https://github.com/user-attachments/assets/0f3aeb7d-cda7-4825-837e-d42dcf83fe68" />

**Notification: Amazon SNS**
Amazon SNS delivers real-time success/failure notifications after each pipeline execution.
<img width="1072" height="576" alt="image" src="https://github.com/user-attachments/assets/b8bdf366-6a85-4bec-a467-08f15d1124e2" />

 **Data Warehouse: Amazon Redshift**
 Amazon Redshift acts as the centralized data warehouse for storing processed flight data for high-speed analytics and querying.
 <img width="1807" height="691" alt="image" src="https://github.com/user-attachments/assets/452dbb2b-12d2-4659-b196-dedc845f549d" />

 **Monitoring: AWS CloudWatch**
 AWS CloudWatch provides comprehensive monitoring, logging, and alerting for all components of the data pipeline.
 
## 📊 Architecture Flow

1. Daily CSV files arrive in S3 (`daily_raw/date=2024-01-21/`)
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

  <img width="1115" height="612" alt="image" src="https://github.com/user-attachments/assets/ae270741-a0ed-4f7a-93b7-4b20553d57d4" />


## 🗄 Database Schema

- **Schema**: `airlines`
- **Dimension Table**: `airports_dim`
  <img width="1090" height="367" alt="image" src="https://github.com/user-attachments/assets/2021d261-2f62-4870-8827-01f65499a7d0" />

- **Fact Table**: `daily_flights_fact` (~2 Million records loaded)
  <img width="1115" height="332" alt="image" src="https://github.com/user-attachments/assets/8b1e116e-bedc-4362-af7f-fa6cf4e24c36" />

## 🚀 How to Run the Pipeline

1. Upload CSV file in `daily_raw/date=2024-01-22/` folder
2. EventBridge triggers Step Function automatically
3. Monitor execution in Step Functions console
4. Check data in Redshift Query Editor

<img width="1806" height="343" alt="image" src="https://github.com/user-attachments/assets/44fb99d0-d167-4c85-ad33-eaab4f8df90b" />


## 📈 Future Enhancements

- Incremental data loading using CDC
- Infrastructure as Code using Terraform
- Dashboard using Amazon QuickSight
- Cost optimization

## 🧑‍💻 Author

**Mohammad Karim**  
AWS Certified | Data Engineer
Name: Mohammad Karim 
Email: Karimcse07@gmail.com
Mob: +91-7065-053-815
Linkedin: www.linkedin.com/in/mohammad-karim-973811258
---

**⭐ Feel free to star this repository if you find it helpful!**

# Spotify End-To-End Data Pipeline

### Introduction
This project builds an ETL (Extract, Transform, Load) pipeline using the spotify API on AWS. The pipeline retrieves data from the spotify API, transform it to a desired format, and load it into AWS data store.  

### About API
API has information about music artist, albums and songs. [Spotify API](https://developer.spotify.com/documentation/web-api)

### Architecture
![Architecture Diagram](https://github.com/vponkia/spotify-end-to-end-data-pipeline/blob/main/spotify_dataPipeline.png)

### Services Used
1. **S3(Simple Storage Service):** Amazon S3 is a highly scalable object storage service that can store and retrieve any amount of data from anywhere on the web. It is commonly used to store and distribute large media files, data backups, aand static website files.

2. **AWS Lambda:** AWS Lambda is a serverless computing service that allows to run code without managing servers, use lambda to run code in response to events like changes in S3, DynamoDB, or other AWS services.

3. **Cloud Watch:** Amazon CloudWatch is a monitoring service for AWS resources and the applications run on them, used to collect and track metrics, collect and monitor log files, and set alarms.

4. **Glue Crawler:** AWS Glue Crawler is a fully managed service that automatically crawls your data sources, identifies data formats, and infers schemas to create an AWS Glue Data Catalog.

5. **Data Catalog:** AWS Glue Data Catalog is a fully managed metadata repository that makes it easy to discover and manage data in AWS, it is mainly used with AWS Athena.

6.  **Amazon Athena:** Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL, can use Athena to analyze data in Glue Data Catalog or other S3 buckets. 

### Install following packages

```
pip install pandas
pip install numpy
pip install spotify
```

### Project Execution Flow
Extract Data From API -> Lambda Trigger (Every 1 hour) -> Run Extract Code -> Store Raw Data -> Trigger Transform Function -> Transform Data and Load -> Query using Athena

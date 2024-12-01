# Reddit ETL Pipeline with AWS S3 and Apache Airflow

## Project Overview  
This project implements an ETL (Extract, Transform, Load) pipeline that extracts top posts from Reddit using the PRAW API, transforms the data, and uploads it to an AWS S3 bucket for storage.  The pipeline is orchestrated using Apache Airflow and leverages a modular architecture to ensure scalability, reusability, and maintainability.

## Key Features  
- Data Extraction: Retrieve top posts from a specific subreddit using Reddit API.
- Data Transformation: Clean and format the extracted data for analysis and storage.
- Data Loading: Upload the processed data to an AWS S3 bucket.
- Orchestration: Schedule and manage tasks with Apache Airflow.
- Dockerized Environment: Easily deploy and run the pipeline in isolated containers.


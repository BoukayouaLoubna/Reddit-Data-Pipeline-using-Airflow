# Reddit ETL Pipeline with AWS S3 and Apache Airflow

## Project Overview  
This project implements an ETL (Extract, Transform, Load) pipeline that extracts top posts from Reddit using the PRAW API, transforms the data, and uploads it to an AWS S3 bucket for storage.  The pipeline is orchestrated using Apache Airflow and leverages a modular architecture to ensure scalability, reusability, and maintainability.

## Key Features  
- Data Extraction: Retrieve top posts from a specific subreddit using Reddit API.
- Data Transformation: Clean and format the extracted data for analysis and storage.
- Data Loading: Upload the processed data to an AWS S3 bucket.
- Orchestration: Schedule and manage tasks with Apache Airflow.
- Dockerized Environment: Easily deploy and run the pipeline in isolated containers.

## Architecture 

![ArchitectureWorkFlow](https://github.com/user-attachments/assets/6b583a9c-eba6-4b3e-a201-d703683858bb)

### Components:
- Reddit Extraction: Extracts data from Reddit using its API and PRAW library.
- Transformation Layer: Cleans and formats raw data into a structured CSV format.
- AWS S3 Storage: Uploads the structured data to an S3 bucket.
- Apache Airflow DAGs: Manages the entire ETL process through tasks.

### Project Structure
- config/: Contains project configurations (e.g., API keys, file paths, AWS settings).
- dags/: Airflow DAGs for ETL orchestration.
- data/: Input and output data directories.
- etl/: Scripts for extraction, transformation, and loading.
- pipelines/: High-level pipeline logic.
- utils/: Helper functions and constants.

### ETL 

#### ETL 1: Extract Reddit Data to CSV
- Extract: Retrieve posts from Reddit's API for a specific subreddit using praw.
- Transform: Clean and preprocess the data (type conversion, fixing missing values).
- Load: Save the transformed data into a CSV file in the output folder.  
*Key Components:*  
reddit_pipeline.py: Orchestrates the extraction, transformation, and loading process.  
Output: Files like reddit_date.csv.  

#### ETL 2: Load CSV to S3 and Data Warehousing
- Extract: Read the CSV files from the output folder.
- Transform: Ensure data readiness for storage in S3, performing validation if needed.
- Load: Upload files to the S3 bucket under the raw directory.  
*Key Components:*  
aws_etl.py: Handles S3 connection, bucket creation, and file uploads.  
aws_s3_pipeline.py: Implements the ETL pipeline for S3 upload.  
Final Step: Prepare data for data warehousing and visualization in BI tools  

## Tools and Technologies

- **Reddit API**: Fetches subreddit posts as raw data.  
- **Apache Airflow**: Orchestrates and schedules ETL workflows.  
- **Celery**: Distributes tasks for parallel execution.  
- **Redis**: Backend for Celery task management.  
- **PostgreSQL**: Stores Airflow metadata.  
- **Amazon S3**: Stores raw and processed data files.  
- **AWS Glue**: Automates ETL and catalogs data.  
- **AWS Catalog**: Organizes metadata for easier data queries.  
- **Amazon Redshift**: Performs analytics on structured data warehouse.  
- **Docker**: Creates isolated environments for services and dependencies.  

## Setup Instructions

### Prerequisites
- Docker and Docker Compose installed.
- AWS account with an S3 bucket.
- Reddit API credentials (Client ID and Secret).

### Steps to Deploy:
- Clone the repository and navigate to the project directory.
- Update the configuration file with AWS credentials, Reddit API keys, and file paths.
- Use Docker Compose to build and start all services.
- Access the Airflow web interface to trigger both ETL pipelines.

## Authors

*Loubna Boukayoua*
Feel free to contact me for any questions or feedback via email loubnaboukayoua@gmail.com

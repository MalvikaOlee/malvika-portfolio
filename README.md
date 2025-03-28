# Data Analyst Portfolio – Malvika

## Project: AWS-Based Data Analytics Platform for Vancouver Water Quality
<img width="800" alt="Image" src="https://github.com/user-attachments/assets/ccdfb270-a785-4ad8-a2c7-009107824cb5" />

## Project Summary 
The goal of this cloud project is to create a Data Analytics Platform (DAP) for the City of Vancouver that is based on three municipal datasets: Building Water Treatment Systems, Decorative Water Features, and Cooling Tower Water.  From intake and profiling to transformation, governance, and monitoring, the project executes the full AWS workflow.  To guarantee performance, security, and data integrity, the solution makes use of Amazon S3, EC2, Glue Studio, Athena, and other AWS services.

**Project Title**: Water Quality Analytics and Transformation Using AWS Cloud Services

**Objective**
Developing a scalable, safe, and effective platform for consuming, profiling, cleaning, transforming, analyzing, and storing data on water quality is the aim of this project.  The datasets are ready for practical use by local government agencies through appropriate data engineering procedures on AWS.  By arranging data into approved and optimized Parquet formats, the initiative also makes it possible for future data science modeling.

**Dataset**
The datasets include water testing and inspection records collected from various city facilities:
- Cooling Tower.csv
- Decorative Water Feature.csv
- Building Water Treatment.csv
Each file contains critical parameters such as pH, chlorine level, temperature, and microbial data.

## Tools and Technologies Used in AWS:
**1. Data Ingestion and EC2 Setup**
EC2 Instance Name: VWQS-Malvi
<img width="1280" alt="Image" src="https://github.com/user-attachments/assets/a37c846f-7d62-43f4-9efc-fd83ae53adb4" />
To import the CSV datasets into AWS S3 buckets, a virtual server called Amazon EC2 was set up.  Data transmission from the local system to S3 and the execution of AWS CLI instructions were done via PowerShell.
<img width="866" alt="Image" src="https://github.com/user-attachments/assets/d05ef66f-3b1c-4e49-acfd-e204d4e0182a" />

**2. Structured S3 Folder Design**
S3 Bucket Name: vancouver-water-quality-data-malvi
<img width="1261" alt="Image" src="https://github.com/user-attachments/assets/b3d83b63-d874-45ff-be8c-da866208e79a" />
<img width="1273" alt="Image" src="https://github.com/user-attachments/assets/811c8e13-cbbc-4081-82f2-a7f2888d2b72" />
A structured folder layout was created with paths organized by dataset type and timestamps (e.g., year/quarter). This logical structure supports efficient retrieval and lifecycle management.

**3: Profiling with AWS Glue DataBrew**
Each file's data quality was examined using Glue DataBrew.  
- About 4% of the missing values were found by the profiling jobs.
- There is some evidence linking elevated temperatures to a lower number of Legionella.
The Cooling Tower, Decorative Water Feature, and Building Water Treatment datasets all had clean, distinct records, according to Glue DataBrew profile, which showed that none of the datasets had duplicate rows.
- Cooling Tower
<img width="1280" alt="Image" src="https://github.com/user-attachments/assets/d8e8c784-0f6b-4333-a8a6-826135bf0140" />
- Decorative Water Feature
<img width="1274" alt="Image" src="https://github.com/user-attachments/assets/88586d49-a499-4e47-b3e5-ea1beda455d4" />
- Building Water Treatment
  <img width="1270" alt="Image" src="https://github.com/user-attachments/assets/09984439-f661-4b70-9b7f-dbc708b16afa" />

**4. Data Cleaning with DataBrew**
Three cleaning jobs were created — one per dataset — to:
- Replace missing values
- Rename columns (to CamelCase)
- Fix delimiters (; instead of ,)
<img width="1273" alt="Image" src="https://github.com/user-attachments/assets/d0a8504c-86eb-4cb3-8c61-11def2d216a5" />

Cleaned files were stored in two locations:
- User Folder: CSV for front-end users
- System Folder: Parquet files with Snappy compression
<img width="1276" alt="Image" src="https://github.com/user-attachments/assets/0908fa24-3088-4ac7-9a3b-001cd6323995" />
<img width="1280" alt="Image" src="https://github.com/user-attachments/assets/aac99aed-9d03-40ff-9a6b-1fd5e07959e2" />

**5. Lifecycle Rules for Cost Optimization**
To lower long-term storage expenses, older files were archived into Glacier Instant Retrieval using the S3 Lifecycle setting.
<img width="1267" alt="Image" src="https://github.com/user-attachments/assets/8a7fa4df-be06-4052-971f-6422898f15d6" />

**6: Data Transformation with Glue Studio (ETL)**
A visual pipeline in AWS Glue Studio transformed, filtered, and summarized the data. Key steps:
- Format temperature and date fields
- Filter invalid records
- Group and aggregate by water type and location
<img width="575" alt="Image" src="https://github.com/user-attachments/assets/a75b5f76-52e1-4842-92f0-b054d5001bb2" />

**7: Schema Registration with AWS Glue Catalog**
Glue Crawlers automatically detected schema and stored metadata into Glue Catalog tables, enabling Athena queries and future analytics.
<img width="1262" alt="Image" src="https://github.com/user-attachments/assets/a5b5af2d-1245-4c54-9159-c019f4efbe29" />
<img width="1275" alt="Image" src="https://github.com/user-attachments/assets/a5decb93-c26d-4018-bb69-b0527b913d55" />

**8: Visual Architecture Overview**
ETL pipelines, Glue profiling, S3 buckets, PowerShell scripting, EC2, lifecycle rules, and cataloging are all part of the end-to-end cloud design.
<img width="891" alt="Image" src="https://github.com/user-attachments/assets/56565a33-7225-43e1-800d-928c21cf9b45" />

## Insight & Recommendation:
  With validation rules and traceable metadata, the project guarantees clean, formatted, and efficient data storage in S3.  Water quality officers will be able to monitor trends, spot irregularities, and ensure adherence to public health standards with the use of the condensed data.
  The solution offers long-term scalability and cost-efficiency by defining lifecycle automation and transforming datasets into partitioned Parquet formats.  For real-time monitoring, the city may eventually connect this platform with dashboards or machine learning algorithms.

# Course Completion Badge:

<img width="685" alt="Image" src="https://github.com/user-attachments/assets/994e4e21-702b-4863-b212-c8b5944c8ff1" />








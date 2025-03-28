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
  ![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/fae437321d55f217c36db312be16b3ad9b627039/3.EC2.png)
To import the CSV datasets into AWS S3 buckets, a virtual server called Amazon EC2 was set up.  Data transmission from the local system to S3 and the execution of AWS CLI instructions were done via PowerShell.
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/4.%20Power%20Shell.png)

**2. Structured S3 Folder Design**
S3 Bucket Name: vancouver-water-quality-data-malvi
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/2.%20S3%20ss.png)
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/17.%20copy%20and%20paste.png)

**3:Profiling with AWS Glue DataBrew**
Each file's data quality was examined using Glue DataBrew.  
- About 4% of the missing values were found by the profiling jobs.
- There is some evidence linking elevated temperatures to a lower number of Legionella.
The Cooling Tower, Decorative Water Feature, and Building Water Treatment datasets all had clean, distinct records, according to Glue DataBrew profile, which showed that none of the datasets had duplicate rows.
- Cooling Tower
  ![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/6.%20Data%20profiling.png)
- Decorative Water Feature
  ![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/7.%20Data%20profiling%20dwf.png)
- Building Water Treatment
  ![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/8.%20data%20profiling%20bwt.png)

**4.Data Cleaning with DataBrew**
Three cleaning jobs were created — one per dataset — to:
- Replace missing values
- Rename columns (to CamelCase)
- Fix delimiters (; instead of ,)
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/9.%20Data%20cleaning%20run%20jobs.png)

Cleaned files were stored in two locations:
- User Folder: CSV for front-end users
- System Folder: Parquet files with Snappy compression
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/14.%20report%20ss.png)
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/15.%20user%20reprot.png)

**5. Lifecycle Rules for Cost Optimization**
To lower long-term storage expenses, older files were archived into Glacier Instant Retrieval using the S3 Lifecycle setting.
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/10.%20S3%20lifecycle%20rules.png)

**6: Data Transformation with Glue Studio (ETL)**
A visual pipeline in AWS Glue Studio transformed, filtered, and summarized the data. Key steps:
- Format temperature and date fields
- Filter invalid records
- Group and aggregate by water type and location
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/13.%20visual%20pipeline%20ss.png)

**7: Schema Registration with AWS Glue Catalog**
Glue Crawlers automatically detected schema and stored metadata into Glue Catalog tables, enabling Athena queries and future analytics.
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/12.%20crawler.png)
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/16.%20table%20ss.png)

**8: Visual Architecture Overview**
ETL pipelines, Glue profiling, S3 buckets, PowerShell scripting, EC2, lifecycle rules, and cataloging are all part of the end-to-end cloud design.
![image alt](https://github.com/Malvika3000/data-analyst-malvika/blob/2f664b42d6f80b148aea9582483ae9d4c82e4887/11.%20draw.io.png)

## Insight & Recommendation:
  With validation rules and traceable metadata, the project guarantees clean, formatted, and efficient data storage in S3.  Water quality officers will be able to monitor trends, spot irregularities, and ensure adherence to public health standards with the use of the condensed data.
  The solution offers long-term scalability and cost-efficiency by defining lifecycle automation and transforming datasets into partitioned Parquet formats.  For real-time monitoring, the city may eventually connect this platform with dashboards or machine learning algorithms.

# Course Completion Badge:

<img width="685" alt="Image" src="https://github.com/user-attachments/assets/994e4e21-702b-4863-b212-c8b5944c8ff1" />








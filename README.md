## Hi there 👋
I'm Gurkirat Singh, MBA student at University Canada West.

# Project 1.

# Project Introduction

The **Data Analytical Platform (DAP)** project aims to harness publicly available datasets to derive meaningful insights through a structured data processing pipeline. For this project, the dataset utilized is sourced from the Vancouver Open Data portal, specifically the *Property Tax Report 2024*. This dataset provides valuable information regarding property taxation, enabling the analysis of trends over time.

By employing a robust analytical approach using AWS services, the project focuses on transforming raw data into actionable insights. This transformation involves profiling, cleaning, and performing Extract, Transform, and Load (ETL) operations. The outcome is a refined dataset that facilitates a deeper understanding of property tax trends, zoning classifications, and their potential impact on urban planning and policy-making.

# Project Objectives

1. **Data Extraction and Ingestion**  
   Efficiently extract and ingest the *Property Tax Report 2024* dataset from the Vancouver Open Data portal into the AWS ecosystem.

2. **Data Profiling and Cleaning**  
   Perform comprehensive profiling to assess data quality and clean the dataset by addressing inconsistencies, missing values, and duplicate records.

3. **ETL Pipeline Development**  
   Design and implement an ETL pipeline to process, aggregate, and transform the dataset, ensuring its readiness for analysis and visualization.

4. **Trend Analysis**  
   Analyze trends in property tax data over multiple years, focusing on counts of records and average property values to identify patterns and anomalies.

5. **Insight Generation**  
   Derive actionable insights that inform urban planning policies, economic decisions, and zoning regulations by correlating property records with average land values.

6. **Platform Utilization**  
   Demonstrate the capabilities of AWS services such as Glue DataBrew, S3, and ETL workflows for large-scale data processing and analytical tasks.

# Data Analytical Platform (DAP) – Gurkirat Singh

The dataset utilized for this analysis was sourced from the open data portal of Vancouver (Property tax report 2024). This platform provides access to various publicly available datasets for research and analytical purposes. For this particular project, the dataset was downloaded in Excel (.xlsx) format, which offers a user-friendly structure and compatibility with most data processing tools. While other formats, such as CSV and Parquet, were also available for download, the Excel format was deemed the most suitable due to its widespread use and ease of integration into our analytical workflow. By leveraging this format, the dataset could be efficiently ingested into the AWS platform for subsequent profiling, cleaning, and analysis.

<img width="920" alt="Screenshot 2024-12-05 at 4 46 05 PM" src="https://github.com/user-attachments/assets/d8affb71-f320-4314-b1fb-2fe59c752cee">


## Descriptive Analysis

The data extracted from the Vancouver Open Data portal is analysed to observe trends in the property tax dataset by comparing report years with the count of records. In the provided chart, we can see a consistent count of records for each report year under specific zoning classifications:

- In 2020, the count of records is 85.
- For 2021, the count increases to 95.
- The same count of 95 is observed for the years 2022, 2023, and 2024.

This consistent pattern indicates uniform reporting practices or zoning classifications for the "Comprehensive Development" category within the selected "Other" legal type (Vancouver, 2024).

Our purpose is to process this dataset on the AWS platform and replicate similar insights, enabling further comparative analysis. The objective of this analysis is to explore whether property report counts have stabilized over time or if there are variations in legal type distributions that require further investigation.

<img width="902" alt="Screenshot 2024-12-05 at 4 46 13 PM" src="https://github.com/user-attachments/assets/60665908-6846-430f-8ebe-19c14e73f917">

---

## Data Analytical Platform

The following data provides a detailed overview of the implementation of various buckets and processes within the AWS ecosystem. Initially, the raw data is ingested into the designated raw bucket, which serves as the starting point for further processing. The data is then passed through AWS DataBrew, where it undergoes comprehensive profiling and cleaning operations to ensure its quality and consistency. Once the cleaning process is complete, the refined data is stored in the transformed bucket for subsequent use. Following this, an ETL (Extract, Transform, and Load) pipeline is designed and implemented to further process the data. The final output is systematically organized and stored in the curated bucket, which is divided into two separate folders—system and user—to cater to specific analytical and operational requirements. This structured workflow ensures efficient and accurate data processing (AWS Glue Documentation, 2024).

<img width="917" alt="Screenshot 2024-12-05 at 4 46 22 PM" src="https://github.com/user-attachments/assets/27c63dd4-e079-4ce6-aa66-488efd528ef5">


### Data Ingestion

The dataset, extracted in Excel format, is directly ingested into the raw bucket through the upload functionality provided by AWS. This process ensures that the raw data is securely stored and ready for subsequent processing and analysis within the AWS environment.

<img width="907" alt="Screenshot 2024-12-05 at 4 46 30 PM" src="https://github.com/user-attachments/assets/0ea87c4e-5dd5-47ea-9061-05b526efdc03">

---

### Data Profiling

Data profiling is performed to thoroughly assess the quality of the ingested data and to determine any necessary adjustments or modifications required to enhance its accuracy and usability. This process involves establishing a connection to import the data into AWS Glue DataBrew, where a dataset is created specifically for profiling purposes. The profiling process is then executed to identify patterns, inconsistencies, and areas that require attention. Once completed, the profiling results are securely stored in the transformed bucket within the S3 services, ensuring that the data is well-prepared for further analysis and processing.

<img width="914" alt="Screenshot 2024-12-05 at 4 46 37 PM" src="https://github.com/user-attachments/assets/e0f5c18c-3290-4daa-8e9b-39c40766c29b">
---

### Data Cleaning

The data cleaning process is a critical step undertaken to prepare the dataset for effective analysis. This process includes several essential tasks such as addressing missing values to ensure completeness, removing duplicate records to maintain data integrity, and resolving any formatting inconsistencies to standardize the dataset. These steps are crucial for improving the accuracy and reliability of the analysis. In our specific case, additional columns that were deemed irrelevant to the objectives of the analysis were identified and removed. This streamlined approach ensures that only the necessary and meaningful data is retained, optimizing the dataset for achieving the desired results.

<img width="918" alt="Screenshot 2024-12-05 at 4 46 43 PM" src="https://github.com/user-attachments/assets/3315f3d8-2143-4194-a592-36656aedf808">
---

## ETL Pipeline Design

The pipeline is designed to perform the ETL (Extract, Transform, and Load) process, which facilitates the efficient movement and transformation of data to its final destination. The output generated through this process is referred to as analytical data. In the context of our property tax report, the first step involves retrieving the cleaned data from the transformed bucket and removing any columns that are not relevant to the desired outcomes. Subsequently, the data is aggregated by grouping it based on property construction years and calculating the average property tax values to derive meaningful insights. The final processed information is systematically stored in the curated bucket, organized into two distinct folders—one designated for system-based data and the other for user-specific data. This ensures streamlined access and usability for various analytical needs. The results are visually represented in the accompanying figures.

<img width="912" alt="Screenshot 2024-12-05 at 4 46 51 PM" src="https://github.com/user-attachments/assets/cb4dbbf7-c0bd-4c25-94e4-967cf63e63c8">

---

## Exploratory Analysis

In the exploratory analysis, we added a new variable—average current land value—to the existing column chart to compare it alongside the count of property records for each report year. This allowed us to evaluate if there is any correlation between the number of property records and the trends in average land values over time.

For example:

- In 2020, the count of property records was 85, while the average land value was approximately $3,985,507.
- In 2021, the count increased to 95, and the average land value rose slightly to $4,336,044.
- Similarly, in 2023, while the count remained stable at 95, the average land value increased to $3,752,892.

These observations indicate that while the count of property records has shown stability in recent years, the fluctuations in the average current land value may be influenced by external factors such as market trends or zoning regulations. Urban planning policies and economic conditions might be contributing to the observed trends, as higher land values could signify increased property demand in urbanized areas.

<img width="925" alt="Screenshot 2024-12-05 at 4 46 58 PM" src="https://github.com/user-attachments/assets/882fc7c2-23d3-4cd5-a76c-d04f599c1fa1">

<img width="927" alt="Screenshot 2024-12-05 at 4 47 05 PM" src="https://github.com/user-attachments/assets/9bf88dad-53a7-42d6-8e9d-75cf74d61111">
<img width="916" alt="Screenshot 2024-12-05 at 4 47 11 PM" src="https://github.com/user-attachments/assets/1a44d8ff-ca11-46a6-ba39-604bae67c7aa">
<img width="828" alt="Screenshot 2024-12-05 at 4 47 19 PM" src="https://github.com/user-attachments/assets/894ec716-9488-47dc-bdac-2608ec2b3720">
<img width="914" alt="Screenshot 2024-12-05 at 4 47 25 PM" src="https://github.com/user-attachments/assets/d4b650fd-8cdc-43e1-a9b3-eb4418a95141">
<img width="922" alt="Screenshot 2024-12-05 at 4 47 33 PM" src="https://github.com/user-attachments/assets/f377e0c6-a7fa-4bd3-a1b8-591007b2eb4e">
<img width="918" alt="Screenshot 2024-12-05 at 4 47 39 PM" src="https://github.com/user-attachments/assets/7bbfce16-38d4-42bb-95ad-b7a6eb22e1ee">
<img width="915" alt="Screenshot 2024-12-05 at 4 47 46 PM" src="https://github.com/user-attachments/assets/81068f1f-48bc-4b4f-931c-d7fb419e7cee">
---

## References

1. Vancouver Open Data Portal. (2024). Property tax report. Retrieved November 25, 2024, from [https://opendata.vancouver.ca/explore/dataset/property-tax-report/information/](https://opendata.vancouver.ca/explore/dataset/property-tax-report/information/)
2. Amazon Web Services. (2024). AWS Glue DataBrew: Overview and usage. Retrieved November 25, 2024, from [https://docs.aws.amazon.com/glue/](https://docs.aws.amazon.com/glue/)
3. City of Vancouver. (2024). Comprehensive development zoning classifications. Retrieved November 25, 2024, from [https://vancouver.ca/](https://vancouver.ca/)


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

![Figure 1: Screenshot of Vancouver Open Data Portal – Property Tax Report Dataset](#)

## Descriptive Analysis

The data extracted from the Vancouver Open Data portal is analysed to observe trends in the property tax dataset by comparing report years with the count of records. In the provided chart, we can see a consistent count of records for each report year under specific zoning classifications:

- In 2020, the count of records is 85.
- For 2021, the count increases to 95.
- The same count of 95 is observed for the years 2022, 2023, and 2024.

This consistent pattern indicates uniform reporting practices or zoning classifications for the "Comprehensive Development" category within the selected "Other" legal type (Vancouver, 2024).

Our purpose is to process this dataset on the AWS platform and replicate similar insights, enabling further comparative analysis. The objective of this analysis is to explore whether property report counts have stabilized over time or if there are variations in legal type distributions that require further investigation.

![Figure 2: Property Report Count by Year](#)

---

## Data Analytical Platform

The following data provides a detailed overview of the implementation of various buckets and processes within the AWS ecosystem. Initially, the raw data is ingested into the designated raw bucket, which serves as the starting point for further processing. The data is then passed through AWS DataBrew, where it undergoes comprehensive profiling and cleaning operations to ensure its quality and consistency. Once the cleaning process is complete, the refined data is stored in the transformed bucket for subsequent use. Following this, an ETL (Extract, Transform, and Load) pipeline is designed and implemented to further process the data. The final output is systematically organized and stored in the curated bucket, which is divided into two separate folders—system and user—to cater to specific analytical and operational requirements. This structured workflow ensures efficient and accurate data processing (AWS Glue Documentation, 2024).

![Figure 3: Workflow Diagram of Report Year Processing in AWS](#)

### Data Ingestion

The dataset, extracted in Excel format, is directly ingested into the raw bucket through the upload functionality provided by AWS. This process ensures that the raw data is securely stored and ready for subsequent processing and analysis within the AWS environment.

![Figure 4: Data Ingestion in AWS S3](#)

---

### Data Profiling

Data profiling is performed to thoroughly assess the quality of the ingested data and to determine any necessary adjustments or modifications required to enhance its accuracy and usability. This process involves establishing a connection to import the data into AWS Glue DataBrew, where a dataset is created specifically for profiling purposes. The profiling process is then executed to identify patterns, inconsistencies, and areas that require attention. Once completed, the profiling results are securely stored in the transformed bucket within the S3 services, ensuring that the data is well-prepared for further analysis and processing.

![Figure 5: Data Profiling in AWS Glue DataBrew](#)

---

### Data Cleaning

The data cleaning process is a critical step undertaken to prepare the dataset for effective analysis. This process includes several essential tasks such as addressing missing values to ensure completeness, removing duplicate records to maintain data integrity, and resolving any formatting inconsistencies to standardize the dataset. These steps are crucial for improving the accuracy and reliability of the analysis. In our specific case, additional columns that were deemed irrelevant to the objectives of the analysis were identified and removed. This streamlined approach ensures that only the necessary and meaningful data is retained, optimizing the dataset for achieving the desired results.

![Figure 6: Data Cleaning Process in AWS Glue DataBrew](#)

---

## ETL Pipeline Design

The pipeline is designed to perform the ETL (Extract, Transform, and Load) process, which facilitates the efficient movement and transformation of data to its final destination. The output generated through this process is referred to as analytical data. In the context of our property tax report, the first step involves retrieving the cleaned data from the transformed bucket and removing any columns that are not relevant to the desired outcomes. Subsequently, the data is aggregated by grouping it based on property construction years and calculating the average property tax values to derive meaningful insights. The final processed information is systematically stored in the curated bucket, organized into two distinct folders—one designated for system-based data and the other for user-specific data. This ensures streamlined access and usability for various analytical needs. The results are visually represented in the accompanying figures.

![Figure 8: ETL Pipeline for Property Tax Report Processing](#)

---

## Exploratory Analysis

In the exploratory analysis, we added a new variable—average current land value—to the existing column chart to compare it alongside the count of property records for each report year. This allowed us to evaluate if there is any correlation between the number of property records and the trends in average land values over time.

For example:

- In 2020, the count of property records was 85, while the average land value was approximately $3,985,507.
- In 2021, the count increased to 95, and the average land value rose slightly to $4,336,044.
- Similarly, in 2023, while the count remained stable at 95, the average land value increased to $3,752,892.

These observations indicate that while the count of property records has shown stability in recent years, the fluctuations in the average current land value may be influenced by external factors such as market trends or zoning regulations. Urban planning policies and economic conditions might be contributing to the observed trends, as higher land values could signify increased property demand in urbanized areas.

![Figure 10: Comparative Analysis of Report Year by Count and Average Land Value](#)

---

## References

1. Vancouver Open Data Portal. (2024). Property tax report. Retrieved November 25, 2024, from [https://opendata.vancouver.ca/explore/dataset/property-tax-report/information/](https://opendata.vancouver.ca/explore/dataset/property-tax-report/information/)
2. Amazon Web Services. (2024). AWS Glue DataBrew: Overview and usage. Retrieved November 25, 2024, from [https://docs.aws.amazon.com/glue/](https://docs.aws.amazon.com/glue/)
3. City of Vancouver. (2024). Comprehensive development zoning classifications. Retrieved November 25, 2024, from [https://vancouver.ca/](https://vancouver.ca/)


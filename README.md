Project Title: Fintech Cloud Data Pipeline and Loan Insights Dashboard

● Project Overview:

This project established a cloud data engineering and analytics pipeline using Google Cloud Platform (GCP). The objective was to ingest raw location data, clean and deduplicate the datasets within a cloud data warehouse, and construct an automatically refreshing dashboard to track loan metrics, risk categories, and customer demographics.

● Architectural Decisions and Trade-offs:

I chose Google Cloud Storage for scalable, low-cost raw data staging. Used BigQuery’s logical views to isolate aggregations (like time-series volume tracking), ensuring the Looker Studio dashboard queries pre-computed data to minimize cloud compute costs and keep dashboard refresh rates fast. 

● Data Ingestion and Environment:

This project environment was built within Google Cloud BigQuery, transitioning data from flat files into organized production tables.

Raw Ingestion     Cleaned CSV data was ingested into Google Cloud Storage for scalable staging.  
Database Schema   Flat data was structured into queryable tables in BigQuery to optimize analytical performance.

● Analytical Views and Trends:

Before building the dashboard, specific views were generated in BigQuery to isolate specific financial information.

Categorial Mapping (Loan purposes)

![Categorical Schema Mapping](images/image1.png)

2. Time-Series Aggregation (loan_count_by_year)

Isolated historical loan metrics to evaluate the total count of outstanding loans issued per year, tracking volume growth.

![Time-Series Loan Volume Aggregation](images/image2.png)

3. Executive BI Dashboard (Loan Insights):

![Executive Financial BI Dashboard](images/image3.png)

The consumption layer uses Looker Studio to transform the ingested BigQuery tables into an interactive automatically refreshing reporting interface for risk management.


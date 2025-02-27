# Extraction Details  
**{ Your Company Name }**  
**Author:** { Author }  
**Date:** { Date }  
**Version:** { Version }  

---

## Overview  
This document provides details on how data is extracted from various source systems into the project’s pipelines. It outlines extraction methods, frequency, transformations applied during extraction, and error handling mechanisms. This ensures a standardized approach to data ingestion while maintaining data integrity and performance.  

---

## Contacts  

| Name | Organization | Role | Contact Information |
|------|--------------|------|---------------------|
|      | Data/Analytics | The role of the person in the project | email/phone |

---

## 1. Extraction Methods & Frequency  
Define how data is retrieved from each source system and its schedule.  

| Source Name | Extraction Type | Frequency | Incremental? | Extraction Tool |
|------------|----------------|-----------|-------------|----------------|
| Salesforce | API | Daily | Yes | Airflow DAG |
| Snowflake | SQL Query | Hourly | No | dbt |
| Google Analytics | API | Daily | Yes | Custom Python Script |
| S3 Bucket | File-based | Event-Driven | Yes | AWS Lambda |

- **Batch vs. Real-Time:** Which sources are extracted in bulk vs. streamed in real-time?  
- **Incremental vs. Full Load:** Are new records appended, or is the full dataset refreshed each time?  
- **Scheduled vs. Event-Driven:** Is the extraction triggered by a scheduler (Airflow, Matillion) or based on external events (e.g., S3 file upload, Kafka message)?  

> Ensures consistent extraction patterns and avoids unnecessary reprocessing.  

---

## 2. Data Transformation During Extraction  
Describe any transformations applied to raw data before it reaches the pipeline.  

- **Standardization:** (Date formatting, currency conversion, casing rules)  
- **Filtering Logic:** (Removing test data, ignoring inactive records)  
- **Schema Mapping:** (Source field names → Standardized field names)  
- **Derived Columns:** (Calculating new fields during extraction)  

### Example:  

| Source | Source Field | Transformed Field | Transformation Rule |
|--------|-------------|------------------|-------------------|
| Salesforce | `lead_status` | `lead_stage` | Map raw statuses to standardized stages |
| Snowflake | `purchase_date` | `purchase_year` | Extract year from timestamp |
| Google Analytics | `event_category` | `event_type` | Rename for consistency |

> Ensures that extracted data aligns with existing schemas and business rules.  

---

## 3. API & Query Optimization  
Define best practices for efficient data extraction from APIs and databases.  

- **API Rate Limits & Pagination:**  
  - Are API requests batched or paginated?  
  - How do we handle quota restrictions?  
- **Database Query Performance:**  
  - Are queries using indexes and partitioning effectively?  
  - Are `SELECT *` queries avoided in favor of column-specific retrieval?  
- **Parallelization & Efficiency:**  
  - Are API calls or queries executed in parallel to optimize runtime?  
  - Are there mechanisms to retry failed requests without reprocessing successful ones?  


# Extraction Details  
**{ Your Company Name }**  
**Author:** { Author }  
**Date:** { Date }  
**Version:** { Version }  

---

## Overview  
This document provides details on how **data is extracted** from various source systems into the project’s pipelines. It outlines **extraction methods, frequency, transformations applied during extraction, and error handling mechanisms** to ensure a **standardized approach** while maintaining **data integrity and performance**.  

> **📌 Best Practice:**  
> - This document should be updated whenever an **extraction process is modified** or a **new source is added**.  
> - Ensure this aligns with **Source Systems** and **Adding New Sources** documentation.  

---

## Contacts  

| Name  | Organization   | Role                                  | Contact Information |
|-------|--------------|---------------------------------------|---------------------|
|       | Data/Analytics | The role of the person in the project | email/phone |

---

## 1. Extraction Methods & Frequency  
Define how data is retrieved from each source system and its schedule.  

### **Example:**  

| Source Name | Extraction Type | Frequency | Incremental? | Extraction Tool |
|------------|----------------|-----------|-------------|----------------|
| Salesforce | API | Daily | Yes | Airflow DAG |
| Snowflake | SQL Query | Hourly | No | dbt |
| Google Analytics | API | Daily | Yes | Custom Python Script |
| S3 Bucket | File-based | Event-Driven | Yes | AWS Lambda |

- **Batch vs. Real-Time:** Which sources are extracted in bulk vs. streamed in real-time?  
- **Incremental vs. Full Load:** Are new records appended, or is the full dataset refreshed each time?  
- **Scheduled vs. Event-Driven:** Is the extraction triggered by a scheduler (Airflow, Matillion) or based on external events (e.g., S3 file upload, Kafka message)?  

> **📌 Ensures** consistent extraction patterns and prevents unnecessary reprocessing.  

---

## 2. Data Transformation During Extraction  
Describe any **transformations applied** to raw data before it reaches the pipeline.  

- **Standardization:** (Date formatting, currency conversion, casing rules)  
- **Filtering Logic:** (Removing test data, ignoring inactive records)  
- **Schema Mapping:** (Source field names → Standardized field names)  
- **Derived Columns:** (Calculating new fields during extraction)  

### **Example:**  

| Source | Source Field | Transformed Field | Transformation Rule |
|--------|-------------|------------------|-------------------|
| Salesforce | `lead_status` | `lead_stage` | Map raw statuses to standardized stages |
| Snowflake | `purchase_date` | `purchase_year` | Extract year from timestamp |
| Google Analytics | `event_category` | `event_type` | Rename for consistency |

> **📌 Ensures** that extracted data aligns with existing schemas and business rules.  

---

## 3. API & Query Optimization  
Define best practices for **efficient data extraction** from APIs and databases.  

- **API Rate Limits & Pagination:**  
  - Are API requests batched or paginated?  
  - How do we handle quota restrictions?  
- **Database Query Performance:**  
  - Are queries using indexes and partitioning effectively?  
  - Are `SELECT *` queries avoided in favor of column-specific retrieval?  
- **Parallelization & Efficiency:**  
  - Are API calls or queries executed in parallel to optimize runtime?  
  - Are there mechanisms to retry failed requests without reprocessing successful ones?  



## 4. Error Handling & Recovery  
Define strategies for handling **extraction failures and partial data loads**.  

### **Retry & Backoff Strategies:**  
- If an **API fails**, how many retries are attempted?  
- Is **exponential backoff** used for rate-limited APIs?  

### **Handling Missing or Corrupt Data:**  
- How do we handle **NULL values, missing files, or empty API responses**?  

### **Logging & Monitoring:**  
- Are **errors logged**? Where? (DataDog, Splunk, ELK)  
- Are **alerts triggered** for persistent failures?  

### **Example:**  

| **Error Type**   | **Recovery Strategy** |
|------------------|----------------------|
| API Timeout     | Retry with exponential backoff |
| Schema Change   | Log issue, alert data engineers |
| Missing Data    | Skip batch, retry next cycle |

> **📌 Ensures robustness** in handling extraction failures.  

---

## 5. Data Quality & Validation Checks  
Define **automated checks** to ensure **data accuracy** during extraction.  

### **Row Count & Volume Checks:**  
- Does the extracted data match expected **record counts**?  

### **Duplicate Detection:**  
- Are **unique keys enforced**?  

### **Data Type & Format Validation:**  
- Do extracted values match **expected data types**?  

### **Anomaly Detection:**  
- Are **outliers flagged** (e.g., negative prices, extreme values)?
> **📌 Prevents bad data from propagating through the pipeline.

---

## 6. Performance Monitoring & Scaling Considerations  
Define strategies for **optimizing extraction** as data volumes grow.  

### **Handling Large Data Volumes:**  
- Are **extractions split** into smaller partitions?  
- Are we using **compression formats** (Parquet, Avro) for efficiency?  

### **Scaling Extraction Jobs:**  
- Are **batch jobs dynamically scaled** based on workload?  
- Is there an **auto-scaling mechanism** in place for API calls?  

### **Storage & Cost Management:**  
- Are **redundant data extractions avoided**?  
- Are extractions **optimized** to minimize cloud storage and compute costs?  

> **📌 Ensures** that extraction processes remain **scalable and cost-efficient** over time.  

---

## Next Steps  
- If **modifying an existing extraction process**, ensure updates are tested in a **staging environment**.  
- If a **new source** is being added, ensure it is documented in the **"Source Systems"** and **"Adding New Sources"** documentation.  
- If an **extraction job is deprecated**, follow the **"Data Governance & Retention"** guidelines.  

---

## How This Fits with Other Documentation  
- **["Source Systems"](source_systems.md)** → Provides **high-level details** on all integrated sources  
- **["Adding New Sources"](adding_new_sources.md)** → Covers **integration steps** for new data sources  
- **["API’s and Connections"](api_connections.md)** → Details **authentication and connection setup**  

---



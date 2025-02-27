# Source Systems  
**{ Your Company Name }**  
**Author:** { Author }  
**Date:** { Date }  
**Version:** { Version }  

---

## Overview  
This document provides an inventory of all data source systems integrated into the project. It outlines each source's purpose, access details, data characteristics, and dependencies. This ensures transparency in how data flows into the system and helps assess the impact of changes.  

---

## Contacts  

| Name | Organization   | Role                                  | Contact Information |
|------|--------------|---------------------------------------|---------------------|
|      | Data/Analytics | The role of the person in the project | email/phone |

---

## 1. Source System Inventory  
Provide a high-level list of all integrated data sources with important metadata.  

### **Example:**  

| Source Name       | Type  | Owner      | Frequency | Format | Connection Type |
|------------------|------|----------|-----------|--------|-----------------|
| Indeed          | API  | Data Team | Daily     | JSON   | REST |
| LinkedIn        | S3   | Data Team | Hourly    | CSV    | REST |
| Mapping File #1 | S3   | Data Team | Monthly   | CSV    | Manual |

> This table serves as a quick reference for all source systems. Expand as needed.

---

## 2. Source System Details  
For each source, provide a deeper **technical overview**. You may also split these into individual subfiles if needed.  

### **Example: Salesforce API**  
- **Purpose:** Provides customer interaction data for analytics.  
- **Access:** API authentication using OAuth 2.0. Credentials stored in **Azure Key Vault**.  
- **Connection Details:**  
  - **Endpoint:** `https://api.salesforce.com/data/example/`  
  - **Rate Limits:** 10,000 API calls per hour  
  - **Pagination:** Uses `nextPageToken` for incremental data fetching  
- **Data Structure:**  
  - **Entities:** Leads, Opportunities, Accounts, Contacts  
  - **Schema Considerations:** Some fields are nullable; JSON response varies by version.  
- **Dependencies:** Used in ETL pipeline for lead scoring models.  

> Each source system should have a detailed breakdown like this. You can also link to more detailed source-specific documentation.

---

## 3. Data Flow & Dependencies  
Describe how data moves from source systems into the project’s pipelines.  

- **Ingestion Methods:** Batch, real-time  
- **Processing Stages:** (Visuals highly recommended for clarity)  
- **Transformation Tools:** dbt, Matillion, Airflow, Spark  
- **Downstream Usage:**  
  - Which views, dashboards, ML models, or reporting tools does this source impact?  
  - What business processes rely on this data?  

> **📌 Best Practice:** Include a **data flow diagram** here. This serves as a **detailed version** of the "High-Level Overview" diagram in Section 02 of your documentation.

---

## 4. Change Management  
Define how updates to source systems are handled to prevent **breaking changes**.  

- **Source Updates:** How are API version changes, schema modifications, or ownership changes handled?  
- **Schema Evolution Strategy:**  
  - Does the system support new fields automatically?  
  - How are breaking changes detected and mitigated?  
- **Testing & Validation:**  
  - Are there staging environments or shadow tables to validate changes?  
- **Communication Plan:**  
  - How are teams notified about source system changes?  

> These steps help prevent disruptions when source systems evolve.

---

## 5. Monitoring & Issue Resolution  
Define how source systems are monitored for **data freshness, consistency, and failures**.  

- **Data Freshness Checks:**  
  - Are new records appearing on schedule?  
  - Do time-based partitions align with expected ingestion rates?  
- **Anomaly Detection:**  
  - Are there unexpected NULLs, duplicate records, or missing fields?  
- **Alerting & Logging:**  
  - Are failures logged? Where? (DataDog, Splunk, ELK, Azure Monitor)  
  - Who gets notified when something breaks?  

> **📌 Best Practice:** Include this in **troubleshooting documentation** to quickly diagnose issues.

---

## 6. Source System Retirement & Deprecation  
Outline the process for **retiring or replacing** a source system when necessary.  

- **Deprecation Criteria:**  
  - When is a source considered obsolete?  
  - Are there cost or performance concerns?  
- **Transition Plan:**  
  - How is historical data migrated?  
  - What alternate sources replace the old system (if applicable)?  
- **Data Cleanup & Archival:**  
  - Are old tables/buckets **purged** or **archived**?  
  - How long is data retained before deletion?  

> **📌 Best Practice:** Regularly review active data sources to avoid **clutter and redundancy**.

---

## Next Steps  
- Update this document whenever a **new source is added** or **an old one is retired**.  
- Ensure all changes to source systems are communicated to relevant teams.  
- Maintain proper **testing & monitoring** workflows for long-term reliability.  

---

## How This Fits with Other Documentation  
- **["API’s and Connections"](api_connections.md)** → Covers authentication and connection setup  
- **["Adding New Sources"](adding_new_sources.md)** → Covers integration steps for new data sources  
- **["Extraction Details"](extraction_details.md)** → Explains how data is retrieved and processed  

---

## Why This Version Works for Existing Projects  
✅ **Provides a central inventory of all source systems** → Makes it easy to track existing data sources.  
✅ **Includes impact assessment for system changes** → Helps prevent downstream issues.  
✅ **Standardizes monitoring & alerting expectations** → Ensures data reliability.  
✅ **Covers deprecation & transition plans** → Avoids abandoned or redundant data sources.  

---

Would this structure work for you? Let me know if you need any refinements! 🚀

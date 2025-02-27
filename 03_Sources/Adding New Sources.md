# Adding New Sources  
**{ Your Company Name }**  
**Author:** { Author }  
**Date:** { Date }  
**Version:** { Version }  

---

## Overview  
This document provides a structured process for integrating **new data sources** into the project.  

> **Best Practice:**  
> - This is a **highly variable task**, so this document should serve as a **guide** rather than a rigid template.  
> - Answering the questions below will help **streamline documentation** for the new source later.  
> - Be sure to check the **references list** to see **who to contact for updates to current docs**.  

---

## Contacts  

| Name  | Organization   | Role                                  | Contact Information |
|-------|--------------|---------------------------------------|---------------------|
|       | Data/Analytics | The role of the person in the project | email/phone |

---

## 1. Business Purpose  
**Document why this new source is being added and what it needs to support.**  

### **Key Considerations:**  
- **Why is this data needed?**  
- **How does it impact existing systems?**  
- **How will it integrate into current source systems?**  
- **What are the final tables/views this data will support?**  
- **Has the client approved this with clear expectations?**  

> **Best Practice:**  
> - This section will later form the **Overview** for the new source’s documentation.  
> - Ensure you have **written client approval** to avoid misalignment on business needs.  

---

## 2. Documenting Your New Source + Setup for Success  
> **Why document upfront?**  
> - Helps **identify gaps** in understanding.  
> - Provides a **clear roadmap** for implementation.  
> - Minimizes redundant documentation efforts later.  

### **Define how the new source will connect to the existing system:**  
- **Source Type:** (API, Cloud Storage, Streaming, etc.)  
- **Authentication Requirements:** (OAuth, API Key, VPN, etc.)  
- **Storage or Access Constraints:** (IP whitelisting, read vs. write access)  

### **Describe how the data will be extracted & processed within the pipeline:**  
- **Frequency:** (Real-time, Hourly, Daily, Monthly)  
- **Volume:** (Expected data size)  
- **Incremental vs. Full Load**  
- **Data Format:** (JSON, Parquet, CSV, etc.)  
- **Existing Tooling & Orchestration:**  
  - Does **Matillion, dbt, or Airflow** need modifications?  
  - Can this **leverage an existing ETL/ELT job**, or does it require a **new one**?  

### **Define how new data sources align with existing data structures:**  
- **Schema Comparison:** How does the new data compare to existing tables?  
- **New vs. Existing Tables:** Will this data fit into an existing structure?  
- **Deduplication Strategy:** Are there risks of duplicate records?  
- **Backward Compatibility:** Will this introduce breaking changes?  

### **Define how the new source will be monitored & maintained post-integration:**  
- **Logging & Debugging:** Will logs be collected in a centralized location?  
- **Alerting Mechanisms:** (Email, Slack, PagerDuty)  
- **Error Handling Strategy:** What should happen when data fails validation?  
- **Performance Monitoring:** Should pipeline execution time be tracked?  

> **Best Practice:**  
> - Setting up documentation early clarifies questions **before implementation begins**.  

---

## 3. Deployment, Testing, and Sign-Off  

### **Development Environment:**  
- **Was the integration tested in staging/dev first?**  
  - Ensure **multiple people verify** this.  
  - Follow the **existing QA process** where applicable.  

### **Data Validation:**  
- **Are row counts and data types consistent with expectations?**  
- **Do joins with existing datasets behave as expected?**  
- **Does the client agree with the validation results?** (**Get this in writing!**)  

### **Approval Process:**  
- **Who needs to review and approve this before moving to production?**  
- **List internal & external reviewers for accountability.**  

### **Deployment Steps:**  
- **How will the new integration be deployed?**  
  - Airflow DAG update?  
  - New storage bucket creation?  
  - Database schema updates?  

> **Best Practice:**  
> - Ensure **comprehensive testing** before deploying to production.  
> - Get **explicit sign-off** from stakeholders before deployment.  

---

## 4. Next Steps  

*(No need to change this section for your personal docs, but feel free to do so.)*  

- If modifying an **existing source**, update the following documentation:  
  - **Extraction Details**  
  - **Schema Documentation**  
  - **Monitoring & Governance**  

- Ensure that governance and monitoring for the **new source** is behaving as expected in **production**.  
- Thoroughly document the new source in the following:  
  - **API’s and Connections**  
  - **Extraction Details**  
  - **Source Systems**  

---


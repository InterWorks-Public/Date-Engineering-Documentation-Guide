# Source Systems

{ Your Company Name }

{ Author  }

{ Date }

{ Version }

# Overview

*This document provides an inventory of all data source systems integrated into the project. It outlines each source's purpose, access details, data characteristics, and dependencies. This ensures transparency in how data flows into the system and helps assess the impact of changes.*


# Source System Inventory

*Provide a high level list of all integrated data source with important metadate. Below is an example:* 

| Source Name | Type  | Owner    | Frequency | Format | Connection Type |
|-------------|-------|----------|-----------|--------|-----------------|
| Indeed | API  | Data Team   | Daily | JSON | REST |
| Linkedin | S3 | Data Team   | Hourly | CSV| REST |
| Mapping File #1 | S3 | Data Team   | Monthly | CSV| Manual |

# Source System Details: 

*For each source, provide a deeper Technical Overview. You may also splt thes out into individual subfiles if you wish, that is up to you and your team. This will have some overlap with other source docs, which is okay. If you want to link them in for even more granularity, this is a good idea if it works for you!*

*Example: Salesforce API*
- Purpose: provides customer interaction data for analytics
- Access: API authentication using Oauth 2.0. Credentials stored in Azure Key vault
- Connection Details:
     - Endpoint/s: https://api.salesforce.com/data/example/
     - Rate Limits: 10,000 calls per hour
     - Pagination: uses nextPageToken for incremental data fetching
- Data Structure:
     - Entities: Leads, Opportunites, Accounts, Contacts
     - Schema Considerations: Some fields are Nullable, JSON response varies by version.
- Dependencies: Used in ETL pipeline for big lead scoring models.


# Data Flow and Dependencies

*Describe how data moves from source systems into the projects' pipelines. 
- Ingestion methods: Batch, real-time
- Processing stages (you may/should) include visuals here for clarity
- transformation tools
- Downstram usage: Which views, dashboards, etc is this source impacting.

*You should really include a data flow diagram here if possible. This will serve as a more specific and microscopic version of what you see in the "HIGH LEVEL OVERVIEW" diagram in section 02 of your documentation. 

# Change management

*Define how updates to source systems are handled to prevent breaking changes 

# Contacts

| Name | Organization   | Role                                  | Contact Information |
|------|----------------|---------------------------------------|---------------------|
|      | data/analytics | The role of the person in the project | email/phone         |

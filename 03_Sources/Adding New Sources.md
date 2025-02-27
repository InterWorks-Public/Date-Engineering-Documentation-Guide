# Adding New Sources

{ Your Company Name }

{ Author  }

{ Date }

{ Version }

# Overview

*This document provides a structured process for integrating new data sources into the project. It outlines key considerations, required configurations, and best practices to ensure seamless data ingestion and integration.*

# Business Purpose

*Document why this new source is being added and what it needs to support. You will alter use this in the overview section of the documentation for your new source. Here you want to consider the "why", its impact on existing systems, and how it will integrate into current source systems. Remember that you need to get very clear approval from the client for this, as well as clarity on the business purpose so you make sure you fulfill the request they having in mind, not just integrating the source to integrate it. Make sure you have the final views or tables it should lead up to in mind as you do this.*

# Documenting your new source + Set up for success

*Remember that setting up your documentation (at least a skeleton) will also help clarify any questions you may need answered by your client, and provide a clear roadmap for implementing the addition of a new source. In this way, barebones documentation of you new source by answering the following topics may be helpful to do before actual setup.*


*Define how the new source will connect to the existing system.*

- Source type: API, cloud storage, streaming, etc
- Authentication requirements
- Storage or access constraints: IP whitelisting, read vs write access


Describe how the data will be extracted and process within the existing pipeline.*

- Frequency
- Volume
- Incremental vs Full
- Data Format
- Existing Tooling and Orchestration: Will Matillion, DBT, etc need any modifications? Will this require a new ELT/ETL job or can you leverage an existing one?






# Contacts

| Name | Organization   | Role                                  | Contact Information |
|------|----------------|---------------------------------------|---------------------|
|      | data/analytics | The role of the person in the project | email/phone         |



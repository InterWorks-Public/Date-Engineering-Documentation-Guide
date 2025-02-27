# Adding New Sources

{ Your Company Name }

{ Author  }

{ Date }

{ Version }

# Overview

*This document provides a structured process for integrating new data sources into the project. As this is a highly variable task, we suggest not modifying this template much, and using it as a guide on what sort of questions you need answered from your client and yourself  before going ahead with getting this new source added. Answering the questions below for yourself will also provide you the framework for the documentation of your new source once you get around to that, to minimize the amount of work needed to add the new docs. Be sure to check out the references list to see who you should reach out to for updates to current docs. 

# Business Purpose

*Document why this new source is being added and what it needs to support. You will alter use this in the overview section of the documentation for your new source. Here you want to consider the "why", its impact on existing systems, and how it will integrate into current source systems. Remember that you need to get very clear approval from the client for this, as well as clarity on the business purpose so you make sure you fulfill the request they having in mind, not just integrating the source to integrate it. Make sure you have the final views or tables it should lead up to in mind as you do this.*

# Documenting your new source + Set up for success

*Remember that setting up your documentation (at least a skeleton) will also help clarify any questions you may need answered by your client, and provide a clear roadmap for implementing the addition of a new source. In this way, barebones documentation of you new source by answering the following topics may be helpful to do before actual setup.*


*Define how the new source will connect to the existing system.*

- Source type: API, cloud storage, streaming, etc
- Authentication requirements
- Storage or access constraints: IP whitelisting, read vs write access


*Describe how the data will be extracted and process within the existing pipeline.*

- Frequency
- Volume
- Incremental vs Full
- Data Format
- Existing Tooling and Orchestration: Will Matillion, DBT, etc need any modifications? Will this require a new ELT/ETL job or can you leverage an existing one?

*Define how new data sources align with existing data structures:

- schema comparison: How does the new data compare to existing tables
- New vs Existing tables:







# Contacts

| Name | Organization   | Role                                  | Contact Information |
|------|----------------|---------------------------------------|---------------------|
|      | data/analytics | The role of the person in the project | email/phone         |



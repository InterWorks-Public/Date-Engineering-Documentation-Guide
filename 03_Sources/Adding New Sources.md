# Adding New Sources

{ Your Company Name }

{ Author  }

{ Date }

{ Version }

# Overview

*This document provides a structured process for integrating new data sources into the project. As this is a highly variable task, we suggest not modifying this template much outside of the deployment section, and using it as a guide on what sort of questions you need answered from your client and yourself  before going ahead with getting this new source added. Answering the questions below in the second section for yourself will also provide you the framework for the documentation of your new source once you get around to that, to minimize the amount of work needed to add the new docs. Be sure to check out the references list to see who you should reach out to for updates to current docs.* 

# Business Purpose

*Document why this new source is being added and what it needs to support. You will alter use this in the overview section of the documentation for your new source. Here you want to consider the "why", its impact on existing systems, and how it will integrate into current source systems. Remember that you need to get very clear approval from the client for this, as well as clarity on the business purpose so you make sure you fulfill the request they having in mind, not just integrating the source to integrate it. Make sure you have the final views or tables it should lead up to in mind as you do this.*

# Documenting your new source + Set up for success

*Remember that setting up your documentation (at least a skeleton) will also help clarify any questions you may need answered by your client, and provide a clear roadmap for implementing the addition of a new source. In this way, barebones documentation of you new source by answering the following topics may be helpful to do before actual setup.*


*Define how the new source will connect to the existing system:*

- Source type: API, cloud storage, streaming, etc
- Authentication requirements
- Storage or access constraints: IP whitelisting, read vs write access


*Describe how the data will be extracted and process within the existing pipeline:*

- Frequency
- Volume
- Incremental vs Full
- Data Format
- Existing Tooling and Orchestration: Will Matillion, DBT, etc need any modifications? Will this require a new ELT/ETL job or can you leverage an existing one?

*Define how new data sources align with existing data structures:

- schema comparison: How does the new data compare to existing tables
- New vs Existing tables
- Deduping
- Backward compatibility

*Define how the new sourc will be monitoried and maintained post-integration:*

- logging and debugging: will logs be collected in a centralized location
- Alerting mechanisms: Email, slack, etc
- Error Handling strategy
- Performance analysis: do you need to monitor pipeline execution time?


# Deployment, Testing, and Sign-Off

*Dev environment*

- Was the integration test in staging/dev first? Make sure multiple people verify this, or utilize your curernt QA process that is in place.

*Data validation*
- are row counts and data types consistent with expectations?
- Do joins with existing datasets behave as expected?
- Does the client agree with you on the above two? Get this in writing!

*Approval process*

- Who needs to review and approvethis before moving to production? Note internal and external references

*Deplpyment steps* 

- How will the new integration be deployed?


# Next steps

*(No need to change this section for your personal docs, but feel free to do so)* 

*If you are modifying an existing source, make sure that the changes are reflection in your current extraction details file, Schema documentaition, as well as any other file that may be affected. You should also ensure that governance and monitoring for this new source is behaving as expected in production as well.*

*Make sure you thoroughly cover documenting this new source. This includes, API's and Connections, Extraction Details, Source systems, etc.*

  
  







# Contacts

| Name | Organization   | Role                                  | Contact Information |
|------|----------------|---------------------------------------|---------------------|
|      | data/analytics | The role of the person in the project | email/phone         |



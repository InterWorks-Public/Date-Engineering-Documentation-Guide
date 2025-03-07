# documentation_guide

See the general template in the top level directory once you have gone through the repo. This will be the contents included in every file you create, regardless of subject. Feel free to use as much or as little of the suggested templates within each of the topics' folders! Happy documenting :) 


# Data Project Documentation Template

This repository serves as a structured template for documentation writers. It provides a well-organized framework for documenting data projects, whether for internal use, client-facing materials, or expanding existing documentation.

The provided templates combine these files into one master file in some cases. This is for ease of use, but you can feel free to break these out into multiple files within each section if your project or subsection is rather large.

Ex: login and access is part of getting started's general file, but if this is an extensive process for you, (VPN's, multiple passwords for many tools, security settings etc) it may be useful to break this out into its own file. You may still use the suggested substructure to form the contents of this new file. 

## 01 Getting Started
**Purpose:** This folder provides foundational guidance for new documentation writers and project members.
- `README.md`: Overview of the repository's structure and how to use the template.
- `Project_Setup.md`: Steps to initialize a new documentation project.
- `Tools_and_Dependencies.md`: List of required tools and how to install them.
- `Contributors.md`: Guidelines for contributing to the documentation.
- `Style_Guide.md`: Documentation standards, formatting rules, and best practices.
**Purpose:** This folder provides foundational guidance for new documentation writers and project members.
- `README.md`: Overview of the repository's structure and how to use the template.
- `Project_Setup.md`: Steps to initialize a new documentation project.
- `Contributors.md`: Guidelines for contributing to the documentation.
  
### Access & Logins
**Purpose:** Provides guidelines on accessing tools, authentication requirements, and security best practices.
- `Password_Vault.md`: Instructions for using the password vault tool and who to contact for access.
- `2FA_Setup.md`: Steps for setting up two-factor authentication where applicable.
- `Login_Setups.md`: List of tools used in the project and their respective login requirements.
- `Authentication_Quirks.md`: Notes on special authentication cases.
- `People_Reference.md`: Contact list for:
  - Team members working on the project.
  - Client-side contacts for respective topics.
- `Security_Privacy.md`: Other relevant privacy and security guidelines.
- `VPN_Requirements.md`: VPN setup instructions if applicable.


## 02 High Level Overview
**Purpose:** A broad summary of the project, setting context for stakeholders and new team members.
- `Business_Context.md`: Explanation of the business problem being solved. Lingo, or other business specific topics can be included here. 
- `Project_Objectives.md`: Goals and expected outcomes of the project.
- `Data_Flow_Diagram.png`: Visual representation of data movement within the system.
- `Solution_Architecture.md`: Technical architecture and major components involved.

## 03 Sources
**Purpose:** A detailed breakdown of data sources used in the project.

- `Source_Systems.md`: Overview of data sources and their ownership.
- `APIs_and_Connections.md`: Authentication methods, API endpoints, and credentials setup (excluding sensitive information).
- `File_Formats.md`: Descriptions of expected file types (CSV, JSON, Parquet, etc.).
- `Schema_Reference.md`: Table structures, columns, and data types.
- `Extraction_Details.md`: 
  - Name of the data source and relevant data it contains.
  - Tool used for extraction (e.g., custom API, AWS, Fivetran, etc.).
  - Relevant table names, their format (XML, CSV, JSON, etc.), and whether they are dropped or just updated.
  - If unstructured, how it is transformed into structured data.
  - Expected table sizes and volume of data.
  - Extraction duration and warning signs for failures.
- `Landing_Location.md`: 
  - Where data is stored (Snowflake, S3, etc.).
  - Specific schemas, tables, or folders used for storage.
- `Adding_New_Sources.md`: 
  - Steps for integrating a new source into the existing pipeline.
- `Troubleshooting_Extracts.md`: 
  - Known extraction issues and common troubleshooting methods.
  - Possible pressure points in the process.
**Purpose:** A detailed breakdown of data sources used in the project.

## 04 DB Architecture
**Purpose:** Database design and implementation details.
- `ER_Diagram.png`: Entity-relationship diagram illustrating table relationships.
- `Schema_Definitions.md`: Explanation of schema choices and table definitions.
- `Indexing_and_Performance.md`: Strategies for optimizing database performance.
- `Data_Retention.md`: Policies on data storage, archiving, and deletion.
- `Database_Architecture.md`:
  - Explanation of database design principles (e.g., Medallion, Snowflake, Data Vault, Star Schema, etc.).
  - Staging tables vs. final views, and how they are structured.
  - Breakdown of individual data source pipelines.
  - Detailed visuals similar to the Data Pipeline Architecture.
- `Special_Features.md`:
  - Use of snapshots, Slowly Changing Dimensions (SCDs), and backups.
  - Where these structures exist within the architecture.
- `Cloud_Platform.md`:
  - Hosting details (AWS, Azure, hosted SQL, etc.).
  - Platform-specific quirks and best practices.
- `Permissions.md`:
  - Database access controls.
  - Differences in permissions for analysts, engineers, and external users.
- `Troubleshooting_Guide.md`:
  - Common login problems.
  - Permission-related issues.
  - Missing tables or views.
  - Cloud-specific challenges and resolutions.


## 05 Transformations
**Purpose:** Documentation for data processing workflows and transformations.
- This can get hyperspecific very quickly, so take a while to think this one through. 
- `ETL_Pipeline.md`: Description of the Extract, Transform, Load (ETL) process.
- `Transformation_Scripts/`: Folder containing sample SQL, Python, or dbt scripts.
- `Data_Validation.md`: Steps for ensuring data accuracy and integrity.
- `Workflow_Orchestration.md`: Overview of Airflow, Matillion, or other orchestration tools.

## 06 Reporting Architecture
**Purpose:** Explanation of how data is visualized and reported.
- `Dashboard_Design_Guidelines.md`: Best practices for creating dashboards.
- `Metrics_Definitions.md`: Key performance indicators and their calculations.
- `Report_Templates/`: Sample Power BI, Tableau, or Looker reports.
- `Data_Visualization_Best_Practices.md`: Principles for effective visual communication.
- `Detailed_Reporting_Architecture.md`:
  - In-depth breakdown of the reporting structure with detailed visuals.
  - Explanation of how reports interact with data sources and transformations.
- `Analyst_Insights.md`:
  - Common insights and key information that analysts seek from views and reports.
  - Recommendations for optimizing report structures to better serve analytical needs.
**Purpose:** Explanation of how data is visualized and reported.
- `Dashboard_Design_Guidelines.md`: Best practices for creating dashboards.
- `Metrics_Definitions.md`: Key performance indicators and their calculations.
- `Report_Templates/`: Sample Power BI, Tableau, or Looker reports.
- `Data_Visualization_Best_Practices.md`: Principles for effective visual communication.
---

### How to Use This Template
1. Clone the repository and review the folder structure.
2. Populate each section with relevant documentation as needed.
3. Keep documentation clear, concise, and up-to-date to ensure project consistency and usability.


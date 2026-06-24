# PPCM Solution Classification
 
## Overview
 
Solutions are classified into four tiers. Makers use the criteria below to self-classify their solution before starting development. The classification determines which environments, ALM processes, and governance requirements apply.
 
For each criterion, select the lowest tier that fulfills the requirement. The overall solution tier is the **highest tier assigned across all criteria**.
 
---
 
## The Four Tiers
 
| Tier | Name | Example |
| --- | --- | --- |
| 1 | **Basic** | Personal productivity flow, single-user tool |
| 2 | **Standard** | Departmental app, team approval process |
| 3 | **Advanced** | Cross-departmental solution with custom logic |
| 4 | **Enterprise** | Company-wide critical system, complex architecture |
 
---
 
## Classification Criteria
 
### 1. Number of Users
 
Who uses this solution?
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Single user only | Single department / few people | Multiple departments / cross-departmental | Used across multiple departments up to the entire company |
 
---
 
### 2. Maximum Tolerable Downtime
 
What is the business impact if this solution is unavailable?
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Negligible / no business impact | ≤ 7 days | ≤ 3 days | ≤ 1 day |
 
---
 
### 3. Data Sensitivity
 
Does the solution process sensitive, confidential, or personal data (e.g. GDPR-relevant data)?
 
> **Note:** Solutions processing sensitive, confidential, or personal data must be classified as **Advanced or above**. Advanced and Enterprise solutions handling sensitive data will require a mandatory pre-rollout review to ensure appropriate permissions and data handling are in place.
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Not permitted | Not permitted | Permitted | Permitted |
 
---
 
### 4. Connectors Used
 
What type of connectors does the solution use?
 
> **Note:** Certain connectors (e.g. Twitter/X) are always blocked by data loss prevention policies, regardless of solution tier.
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Standard connectors for M365 tools only | Standard connectors including approved external systems (e.g. Encodian, Adobe) | Standard or Premium prebuilt connectors | Standard, Premium, or custom connectors including external system APIs (HTTP, Azure, SAP, etc.) |
 
---
 
### 5. Data Source
 
What data source does the solution use?
 
> **Note:** Dataverse is considered a Premium data source as it consumes additional storage capacity.
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Personal OneDrive only (lists and documents stored in the user's own OneDrive) | Dedicated SharePoint Site Collection set up for the solution | SharePoint or Dataverse | SharePoint, Dataverse, or Azure Databases / Storage |
 
---
 
### 6. AI Credit Usage
 
Does the solution use AI tools that consume pay-as-you-go credits (e.g. AI Builder)?
 
> **Note:** Solutions consuming AI credits must be classified as **Advanced or above**. Advanced and Enterprise solutions using AI credits will require a mandatory pre-rollout review to ensure appropriate credit allocation.
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Not permitted | Not permitted | Permitted | Permitted |
 
---
 
### 7. Solution Complexity
 
How complex is the solution architecture?
 
| Basic | Standard | Advanced | Enterprise |
| --- | --- | --- | --- |
| Low — minimal components, no external integrations | Medium — moderate components, internal integrations only | High — many components, cross-system integrations | Very High — external systems (SAP, AWS), Azure components, offline capability, or row-level security requirements |
 

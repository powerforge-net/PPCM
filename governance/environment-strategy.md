# PPCM Environment Strategy
 
## Overview
 
Environments are logically and technically separated containers in which Power Platform elements such as flows, apps, and agents are created and operated. The environment strategy defines which environments apply to a solution based on its **solution classification tier**. Each tier determines the required environment setup, ALM pipeline, and naming convention.
 
All environments are provisioned with a Dataverse instance to enable Solutions, granular permissions, and future-proofing.
 
---
 
## Environment Types
 
| Type | Description | Used for |
| --- | --- | --- |
| **Default** | Standard Microsoft 365 environment available to all users. Limited capacity and governance. | Personal productivity only (Tier 1 / Basic) |
| **SHARED-CORE** | Shared environment with a DLP policy permitting M365 standard connectors and approved external connectors (e.g. Encodian, Adobe). | Standard solutions (Tier 2) |
| **SHARED-EXTENDED** | Shared environment with a broader DLP policy permitting standard and premium prebuilt connectors. Multiple solutions may coexist. | Advanced solutions (Tier 3) on the shared path |
| **DEDICATED** | Environment hosting a single solution. DLP policy and connector permissions are configured per solution. Required when shared environments cannot accommodate the solution's technical requirements. | Advanced solutions (Tier 3) on the dedicated path; all Enterprise solutions (Tier 4) |
 
---
 
## Naming Convention
 
Every environment name follows this pattern:
 
```
{STAGE}-{SCOPE}[-{SOLUTION}]
```
 
| Segment | Values | Description |
| --- | --- | --- |
| `STAGE` | `DEV`, `TEST`, `UAT`, `PROD` | Lifecycle stage of the environment |
| `SCOPE` | `SHARED-CORE`, `SHARED-EXTENDED`, `DEDICATED` | Environment type (see above) |
| `SOLUTION` | e.g. `COPILOTSTUDIO`, `QMS` | Required for DEDICATED environments only; identifies the solution |
 
**Examples:**
 
| Name | Meaning |
| --- | --- |
| `DEV-SHARED-CORE` | Shared development environment for Standard solutions |
| `PROD-SHARED-EXTENDED` | Shared production environment for Advanced solutions |
| `DEV-DEDICATED-QMS` | Dedicated development environment for the QMS solution |
| `PROD-DEDICATED-COPILOTSTUDIO` | Dedicated production environment for Copilot Studio solution |
 
---
 
## Environment Strategy per Solution Tier
 
### Tier 1 — Basic
 
| Stage | Environment | Notes |
| --- | --- | --- |
| DEV / PROD | Default environment | No staging. Personal use only. |
 
- No Solutions required.
- No ALM pipeline.
- DLP policy: personal productivity connectors only.
- Flows and apps run under the maker's personal account.
---
 
### Tier 2 — Standard
 
| Stage | Environment |
| --- | --- |
| DEV | `DEV-SHARED-CORE` |
| PROD | `PROD-SHARED-CORE` |
 
- 2-stage ALM pipeline: DEV → PROD.
- Solutions are exported from DEV as **managed** and imported into PROD.
- DLP policy: M365 standard connectors + approved external connectors.
- No Dataverse as a data source; SharePoint is the recommended data source.
---
 
### Tier 3 — Advanced
 
Advanced solutions follow one of two paths depending on their technical requirements.
 
#### Shared path
 
| Stage | Environment |
| --- | --- |
| DEV | `DEV-SHARED-EXTENDED` |
| TEST | `TEST-SHARED-EXTENDED` |
| PROD | `PROD-SHARED-EXTENDED` |
 
#### Dedicated path
 
| Stage | Environment |
| --- | --- |
| DEV | `DEV-DEDICATED-{SOLUTION}` |
| TEST | `TEST-DEDICATED-{SOLUTION}` |
| PROD | `PROD-DEDICATED-{SOLUTION}` |
 
**The dedicated path is required when any of the following apply:**
 
- The solution uses **Dataverse** as a data source.
- The solution requires connectors that **exceed the DLP policy** of the SHARED-EXTENDED environment (e.g. HTTP, Azure services, SAP).
- The solution requires **dedicated resource allocation** (e.g. AI Builder credits).
> If none of the above apply, the shared path is the default for Tier 3.
 
- 3-stage ALM pipeline: DEV → TEST → PROD.
- Solutions are deployed as **managed** in TEST and PROD.
- DLP policy (shared path): standard and premium prebuilt connectors.
- DLP policy (dedicated path): configured per solution.
---
 
### Tier 4 — Enterprise
 
Enterprise solutions always use dedicated environments.
 
| Stage | Environment | Required |
| --- | --- | --- |
| DEV | `DEV-DEDICATED-{SOLUTION}` | Yes |
| TEST | `TEST-DEDICATED-{SOLUTION}` | Yes |
| UAT | `UAT-DEDICATED-{SOLUTION}` | Optional |
| PROD | `PROD-DEDICATED-{SOLUTION}` | Yes |
 
- 3-stage minimum ALM pipeline: DEV → TEST → PROD.
- **UAT** is an optional stage. It should be included when the solution has significant UI complexity or requires structured user acceptance testing before go-live.
- Solutions are deployed as **managed** in TEST, UAT (if applicable), and PROD.
- Full pipeline automation required (Power Apps Pipelines or equivalent).
- DLP policy: configured per solution; may include custom connectors, HTTP, Azure, SAP, or other external system APIs.
---
 
## Summary Table
 
| Tier | DEV | TEST | UAT | PROD | ALM stages |
| --- | --- | --- | --- | --- | --- |
| **1 — Basic** | Default env | — | — | — | None |
| **2 — Standard** | SHARED-CORE | — | — | SHARED-CORE | 2 |
| **3 — Advanced (shared)** | SHARED-EXTENDED | SHARED-EXTENDED | — | SHARED-EXTENDED | 3 |
| **3 — Advanced (dedicated)** | DEDICATED | DEDICATED | — | DEDICATED | 3 |
| **4 — Enterprise** | DEDICATED | DEDICATED | DEDICATED *(opt.)* | DEDICATED | 3–4 |
 
---
 
## Dedicated Path Decision Guide (Tier 3)
 
Use this checklist to determine whether a Tier 3 solution requires a dedicated environment. Answer each question — if **any** answer is yes, the dedicated path applies.
 
| Question | Yes → |
| --- | --- |
| Does the solution use Dataverse as a data source? | Dedicated |
| Does the solution require connectors not permitted in SHARED-EXTENDED (e.g. HTTP, Azure, SAP, custom connectors)? | Dedicated |
| Does the solution require reserved AI Builder credits or other dedicated resource allocation? | Dedicated |
 
If all answers are no → shared path.

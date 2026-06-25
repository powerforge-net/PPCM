# Application Lifecycle Management

## Overview
Lifecycle requirements vary based on Solution classification. Before looking up the appropriate ALM process, make sure you know the correct classification for your solution.

### Tier 1 — Personal
 
| Stage      | Environment         | Notes                          |
| ---------- | ------------------- | ------------------------------ |
| DEV / PROD | Default environment | No staging. Personal use only. |
 
- No Solutions required.
- No ALM pipeline.
- DLP policy: personal productivity connectors only.
- Flows and apps run under the maker's personal account.
---
 
### Tier 2 — Standard
 
| Stage | Environment        |
| ----- | ------------------ |
| DEV   | `DEV-SHARED-CORE`  |
| PROD  | `PROD-SHARED-CORE` |
 
- 2-stage ALM pipeline: DEV → PROD.
- Solutions are exported from DEV as **managed** and imported into PROD.
- Rollout of Solutions built by Builders require review by Engineers on initial rollout, focusing on porper use of the development guidelines.
- When managed environments and pipelines are available, subsequent rollouts can be done by builders without review. Builders should however never have access to service accounts.
---
 
### Tier 3 — Business
 
Business solutions follow one of two paths depending on their technical requirements.
 
#### Shared path
 
| Stage | Environment            |
| ----- | ---------------------- |
| DEV   | `DEV-SHARED-EXTENDED`  |
| TEST  | `TEST-SHARED-EXTENDED` |
| PROD  | `PROD-SHARED-EXTENDED` |
 
#### Dedicated path
 
| Stage | Environment                 |
| ----- | --------------------------- |
| DEV   | `DEV-DEDICATED-{SOLUTION}`  |
| TEST  | `TEST-DEDICATED-{SOLUTION}` |
| PROD  | `PROD-DEDICATED-{SOLUTION}` |
 
**The dedicated path is required when any of the following apply:**
 
- The solution uses **Dataverse** as a data source.
- The solution requires connectors that **exceed the DLP policy** of the SHARED-EXTENDED environment (e.g. HTTP, Azure services, SAP).
- The solution requires **dedicated resource allocation** (e.g. AI Builder credits).
> If none of the above apply, the shared path is the default for Tier 3.
 
- 3-stage ALM pipeline: DEV → TEST → PROD.
- Solutions are deployed as **managed** in TEST and PROD.
- Rollout requires Review by Architect if the solution was built by an Engineer. Architects can perform rollouts without review.
---
 
### Tier 4 — Enterprise

Enterprise solutions always use dedicated environments.
 
| Stage | Environment                 | Required |
| ----- | --------------------------- | -------- |
| DEV   | `DEV-DEDICATED-{SOLUTION}`  | Yes      |
| TEST  | `TEST-DEDICATED-{SOLUTION}` | Yes      |
| UAT   | `UAT-DEDICATED-{SOLUTION}`  | Optional |
| PROD  | `PROD-DEDICATED-{SOLUTION}` | Yes      |
 
- 3-stage minimum ALM pipeline: DEV → TEST → PROD.
- **UAT** is an optional stage. It should be included when the solution has significant UI complexity or requires structured user acceptance testing before go-live.
- Solutions are deployed as **managed** in TEST, UAT (if applicable), and PROD.
- Full pipeline automation including source control recommended.
- Each rollout needs to be reviewed by an architect that is not the person who built the solution
---

## Summary Table
 
| Tier                         | DEV             | TEST            | UAT                | PROD            | ALM stages |
| ---------------------------- | --------------- | --------------- | ------------------ | --------------- | ---------- |
| **1 — Personal**             | Default env     | —               | —                  | —               | None       |
| **2 — Standard**             | SHARED-CORE     | —               | —                  | SHARED-CORE     | 2          |
| **3 — Business (shared)**    | SHARED-EXTENDED | SHARED-EXTENDED | —                  | SHARED-EXTENDED | 3          |
| **3 — Business (dedicated)** | DEDICATED       | DEDICATED       | —                  | DEDICATED       | 3          |
| **4 — Enterprise**           | DEDICATED       | DEDICATED       | DEDICATED *(opt.)* | DEDICATED       | 3–4        |
 
---
# PPCM Environment Strategy
 
## Overview
 
Environments are logically and technically separated containers in which Power Platform elements such as flows, apps, and agents are created and operated. The environment strategy defines which environments apply to a solution based on its **solution classification tier**. Each tier determines the required environment setup, ALM pipeline, and naming convention.
 
All environments are provisioned with a Dataverse instance to enable Solutions, granular permissions, and future-proofing.
 
---
 
## Environment Types
 
| Type                | Description                                                                                                                                                                                          | Used for                                                                             |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Default**         | Standard Power Platform environment available to all users. Limited capacity and governance.                                                                                                         | Personal productivity only (Tier 1 / Personal)                                       |
| **SHARED-CORE**     | Shared environment with a DLP policy permitting M365 standard connectors and approved external connectors (e.g. Encodian, Adobe).                                                                    | Standard solutions (Tier 2)                                                          |
| **SHARED-EXTENDED** | Shared environment with a broader DLP policy permitting standard and premium prebuilt connectors. Multiple solutions may coexist.                                                                    | Business solutions (Tier 3) on the shared path                                       |
| **DEDICATED**       | Environment hosting a single solution. DLP policy and connector permissions are configured per solution. Required when shared environments cannot accommodate the solution's technical requirements. | Business solutions (Tier 3) on the dedicated path; all Enterprise solutions (Tier 4) |
 
---
 
## Naming Convention
 
Every environment name follows this pattern:
 
```
{STAGE}-{SCOPE}[-{SOLUTION}]
```
 
| Segment    | Values                                        | Description                                                       |
| ---------- | --------------------------------------------- | ----------------------------------------------------------------- |
| `STAGE`    | `DEV`, `TEST`, `UAT`, `PROD`                  | Lifecycle stage of the environment                                |
| `SCOPE`    | `SHARED-CORE`, `SHARED-EXTENDED`, `DEDICATED` | Environment type (see above)                                      |
| `SOLUTION` | e.g. `SEM`, `QMS`, `ONB`                      | Required for DEDICATED environments only; identifies the solution |
 
**Examples:**
 
| Name                   | Meaning                                                      |
| ---------------------- | ------------------------------------------------------------ |
| `DEV-SHARED-CORE`      | Shared development environment for Standard solutions        |
| `PROD-SHARED-EXTENDED` | Shared production environment for Business solutions         |
| `DEV-DEDICATED-QMS`    | Dedicated development environment for the QMS solution       |
| `PROD-DEDICATED-ONB`   | Dedicated production environment for the Onboarding solution |
 
---
 
## Dedicated Path Decision Guide (Tier 3)
 
Use this checklist to determine whether a Tier 3 solution requires a dedicated environment. Answer each question — if **any** answer is yes, the dedicated path applies.
 
| Question                                                                                                          | Yes →     |
| ----------------------------------------------------------------------------------------------------------------- | --------- |
| Does the solution use Dataverse as a data source?                                                                 | Dedicated |
| Does the solution require connectors not permitted in SHARED-EXTENDED (e.g. HTTP, Azure, SAP, custom connectors)? | Dedicated |
| Does the solution require reserved AI Builder credits or other dedicated resource allocation?                     | Dedicated |
 
If all answers are no → shared path.

# PPCM Specializations

## Overview

Specializations are rank-independent badges that recognise deep expertise in a specific Power Platform domain. Any maker who has reached at least the **Builder** rank can pursue a specialization — they sit alongside the rank progression rather than replacing it.

Each specialization requires completing a defined set of modules and delivering a practical assessment. Successfully awarded specializations are permanent and visible on a maker's profile.

Specializations do not grant additional solution-building permissions. They serve as a signal of domain expertise and qualify the holder to act as a subject-matter peer-reviewer for solutions that touch their specialization area.

---

## Specialization 1 — AI Builder

**Minimum rank:** Builder

### What this specialization covers
AI Builder specialization recognises makers who can design, train, and operationalise AI models within Power Platform solutions. Holders understand model types, credit consumption, responsible AI principles, and know how to embed AI capabilities into apps and flows without creating governance or cost risks.

### Required modules
- AI Builder model types (classification, prediction, object detection, document processing)
- Credit consumption and capacity planning
- Responsible AI and data governance for AI workloads
- Integrating AI Builder models into Canvas Apps and Cloud Flows

### Assessment deliverable
Design and deliver a working solution that incorporates at least one AI Builder model. The solution must include documentation of the model type chosen, the training data strategy, expected credit consumption, and a responsible-AI consideration log.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions that use AI Builder models, complementing the standard rank-based review.

---

## Specialization 2 — Robotic Process Automation (RPA)

**Minimum rank:** Builder

### What this specialization covers
RPA specialization recognises makers who can build and maintain desktop flows using Power Automate Desktop. Holders understand attended and unattended automation, machine and machine group configuration, credential management, and the governance implications of running automation agents within the enterprise.

### Required modules
- Power Automate Desktop fundamentals and UI selectors
- Attended vs. unattended automation patterns
- Machine and machine group setup and licensing
- Credential vault and secure input handling
- Error handling and resilience patterns for desktop flows
- RPA governance and audit trails

### Assessment deliverable
Build a desktop flow that automates a multi-step business task using at least two application interactions, implements structured error handling, and logs execution results. Document the machine setup, credential management approach, and governance considerations.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions that include desktop flows or unattended automation.

---

## Specialization 3 — Custom Connectors

**Minimum rank:** Engineer

### What this specialization covers
Custom Connector specialization recognises makers who can design, build, secure, and publish custom connectors to extend Power Platform's reach to external APIs. Holders understand OpenAPI specifications, authentication flows, throttling policies, and the DLP and governance implications of introducing new connectors into the tenant.

### Required modules
- OpenAPI / Swagger fundamentals
- Authentication patterns (API Key, OAuth 2.0, Basic)
- Connector actions, triggers, and dynamic schema
- Throttling, pagination, and error response handling
- DLP classification and connector governance
- Certified connector submission process (optional advanced module)

### Assessment deliverable
Design and publish a custom connector against a real or sandbox API. The connector must implement at least one secure authentication method, define at least three actions with correct response schemas, and be accompanied by a governance brief covering DLP classification recommendation and usage restrictions.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions that introduce or rely on custom connectors.

---

## Specialization 4 — Dataverse Modeling

**Minimum rank:** Engineer

### What this specialization covers
Dataverse Modeling specialization recognises makers who can design robust, scalable data models within Microsoft Dataverse. Holders understand table types, column types, relationships, business rules, security roles, row-level security, and the performance and licensing implications of Dataverse-backed solutions.

### Required modules
- Dataverse table types (standard, activity, virtual, elastic)
- Column types and data type selection
- Relationships: one-to-many, many-to-many
- Business rules and calculated/rollup columns
- Security roles, teams, and row-level security
- Dataverse licensing and storage consumption

### Assessment deliverable
Design a Dataverse data model for a realistic business scenario. The submission must include an entity relationship diagram, a security role design, a brief justifying key data modelling decisions, and a storage and licensing impact estimate.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions that use Dataverse as a data source.

---

## Specialization 5 — Copilot Studio

**Minimum rank:** Builder

### What this specialization covers
Copilot Studio specialization recognises makers who can design, build, and publish intelligent conversational agents. Holders understand topic design, entity extraction, generative AI integration, knowledge sources, channel deployment, and the governance implications of AI-powered agents operating on behalf of users.

### Required modules
- Copilot Studio fundamentals: topics, entities, and conversation design
- Generative answers and knowledge source configuration
- Agent actions: Power Automate flow integration and connector actions
- Authentication and single-sign-on for agents
- Channel deployment (Teams, web, custom)
- Responsible AI for conversational agents and escalation design
- Copilot message capacity and licensing

### Assessment deliverable
Design and publish a working agent that handles at least one end-to-end scenario using generative answers, triggers a Power Automate flow action, and is deployed to at least one channel. Include a conversation design document and a responsible-AI assessment covering escalation paths and topic fallback behaviour.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions that include Copilot Studio agents.

---

## Specialization 6 — ALM & DevOps

**Minimum rank:** Engineer

### What this specialization covers
ALM & DevOps specialization recognises makers who can design and operate deployment pipelines for Power Platform solutions. Holders understand environment strategies, solution layering, pipelines (both Power Platform Pipelines and Azure DevOps / GitHub Actions), configuration management, and the change management practices that keep solutions stable in production.

### Required modules
- Solution layering: managed vs. unmanaged solutions
- Environment variables and connection references in pipelines
- Power Platform Pipelines: setup and stage configuration
- Azure DevOps / GitHub Actions for Power Platform (pac CLI, build tools)
- Configuration file management across environments
- Rollback strategies and hotfix patterns
- Change advisory and release governance

### Assessment deliverable
Set up and document a deployment pipeline for an existing solution. The pipeline must cover at least two stages (e.g. development → production), use environment variables and connection references correctly, and be accompanied by a runbook describing the release process, rollback procedure, and change advisory steps.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions where ALM pipeline design or environment strategy is under review.

---

## Specialization 7 — SharePoint Integration

**Minimum rank:** Builder

### What this specialization covers
SharePoint Integration specialization recognises makers who can design solutions that use SharePoint as a reliable, well-governed data source. Holders understand SharePoint list design, permissions, throttling behaviour, delegation in Power Apps, and the patterns that prevent common performance and governance pitfalls when combining SharePoint with Power Platform.

### Required modules
- SharePoint list and library design for Power Platform
- Column types, indexed columns, and view thresholds
- Delegation in Canvas Apps with SharePoint
- SharePoint permissions and sharing model
- Throttling, retry patterns, and batch operations in Cloud Flows
- SharePoint site provisioning and governance
- Migrating solutions from SharePoint data to Dataverse (decision framework)

### Assessment deliverable
Build a Canvas App backed by SharePoint that correctly handles delegation, uses indexed columns, and respects the view threshold. Document the list design, indexing strategy, permission model, and a decision log explaining why SharePoint was chosen over Dataverse for this scenario.

### Peer-review scope
Holders may act as subject-matter reviewer for solutions that use SharePoint as a primary data source.

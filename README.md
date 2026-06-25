# Power Platform Competence Model (PPCM)

> *"Dreamer today, Architect tomorrow."*

**PPCM** is an open framework that unifies Power Platform governance and maker enablement in one coherent system. Instead of treating guardrails and skill-building as separate concerns, PPCM combines them: governance determines what makers are allowed to build and where, while the competence model determines whether they have the skills to build it responsibly. The guidelines tell builders how to build and document their solutions.

The result is an ecosystem where compliance becomes confidence, and adoption becomes engagement.

---

## What's in this repository

This repository contains the full PPCM framework as markdown resources — ready to read, adapt, and use in your own organization.

```
ppcm/
├── user-enablement/
│   ├── ranks.md               # The five ranks: Dreamer, Explorer, Builder, Engineer, Architect
│   ├── specializations.md     # Rank-independent badges and achievements
│   └── skill-trees/
│       ├── power-apps.md
│       ├── power-automate.md
│       ├── copilot-studio.md
│       └── sharepoint.md
│
├── governance/
│   ├── solution-classification.md   # Four-tier classification system
│   └── environment-setup.md          # Environment types, naming, ALM pipelines
│
└── guidelines/
    ├── dev-guidelines.md            # Guidleines to building bullet proof solutions
    └── template-architecutre.md     # Template for Solution Architecture & Documentation
```

For a polished overview with visuals, visit [jzimmer.net](https://jzimmer.net/).

## The three pillars

### 🎮 User enablement — gamified skill development

Makers progress through five ranks across four skill trees (Power Apps, Power Automate, Copilot Studio, SharePoint):

| Rank | XP Threshold | Focus |
|---|---|---|
| **Dreamer** | 0 XP | Contribute ideas, explore the platform |
| **Explorer** | 300 XP | Personal productivity solutions in the default environment |
| **Builder** | 600 XP | Build simple apps and flows independently |
| **Engineer** | 1,200 XP | Structured, scalable solutions with ALM |
| **Architect** | 3,000 XP | Governance, standards, and target architecture |

XP alone isn't enough — each rank requires completing a role-specific onboarding programme and mandatory modules. On top of ranks, makers can earn **Specializations**: rank-independent badges for topics like Custom Connectors, AI Builder, RPA, or Dataverse Modeling.

### 🏛️ Governance — environment strategy & solution classification

Every solution built on the Power Platform is classified into one of four tiers (Basic → Standard → Advanced → Enterprise) based on criteria like user scope, data sensitivity, connector type, and solution complexity. The tier determines:

- Which **environments** the solution lives in (Default, Shared, or Dedicated)
- Which **ALM pipeline** applies (2-stage, 3-stage, or 4-stage)
- Which **DLP policies** and governance requirements apply
- Which **Users** are allowed to build the solutions based on their rank

### 📖 Guidelines - building bulletproof solutions

Guidelines are best practices to follow for solution architecture, naming convention and ALM. The guidelines are a baseline of best practices that applies across to all solutions classified as Standard, Avanced or Enterprise. Compliance is enforced by architect reviews.

- Naming Convention
- Solution Architecutre Template
- 

## How they connect

| Governance Tier | Minimum Maker Rank |
|---|---|
| Tier 1 — Personal | Explorer |
| Tier 2 — Standard | Builder |
| Tier 3 — Business | Engineer |
| Tier 4 — Enterprise | Architect |

A maker's rank signals not just what they *can* build, but what they're qualified to build responsibly. This creates a natural feedback loop: as makers level up, more of the platform opens up to them — not through policy exceptions, but through demonstrated competence.

## How to apply the model

### 1. Onboard your first makers

Start with a small cohort — typically the CoE team or a group of identified power users. Every new maker enters at Dreamer (0 XP) regardless of prior experience. Run the Ideation Onboarding to orient them on the platform and the model. Those who want to build advance voluntarily by completing the Explorer onboarding and hitting 300 XP through submitted and implemented ideas.

### 2. Classify solutions before building

Before any maker writes a single formula or flow, the solution must be classified using the [Solution Classification guide](governance/solution-classification.md). Classification determines the governance tier (Personal → Standard → Business → Enterprise), which in turn determines which environments the solution lives in, which ALM pipeline applies, and which rank a maker must hold before they're authorised to build it. This prevents ungoverned sprawl by design rather than by retrospective audit.

### 3. Assign ranks through demonstrated competence

Rank advancement is not automatic. Each promotion requires three things: hitting the XP threshold, completing the rank-specific onboarding programme, and — from Builder onwards — having a qualifying deliverable reviewed and accepted by an Engineer or Architect. The CoE owns the review process and maintains the record of each maker's current rank. Rank assignments should be visible to the whole maker community, both to signal accountability and to create visible role models.

### 4. Run the system through the CoE

The Center of Excellence is the operational backbone of PPCM. Its responsibilities include: maintaining the DLP policies and environment strategy, conducting pre-rollout reviews for Standard, Business, and Enterprise solutions, approving promotion deliverables, publishing and updating the skill trees and specialization badges, and monitoring the health of the maker community. Without an active CoE, the model exists only on paper. Plan to dedicate at least one Architect-level resource to CoE governance from day one.

---

## Getting started

1. **Classify your solution** using the [Solution Classification guide](governance/solution-classification.md)
2. **Determine your environment setup** using the [Environment Strategy guide](governance/environment-setup.md)
3. **Assess your rank** across the skill trees in the [Competence Model](competence-model/)
4. **Pick your next topics** from the relevant skill tree and start earning XP

## Authors

- **Robert Heep** · https://robertheep.de/
- **Jonas Zimmer** · https://jzimmer.net/

## License

This work is licensed under [Creative Commons Attribution ShareAlike 4.0 International (CC-BY-SA-4.0)](LICENSE).

You are free to use, adapt, and share this framework — including for commercial engagements — as long as you credit the authors and release any adaptations under the same license.
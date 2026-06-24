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
│   ├── ranks.md               # The four ranks: Dreamer, Builder, Engineer, Architect
│   ├── specializations.md     # Rank-independent badges and achievements
│   └── skill-trees/
│       ├── power-apps.md
│       ├── power-automate.md
│       ├── copilot-studio.md
│       └── sharepoint.md
│
└── governance/
├   ├── solution-classification.md   # Four-tier classification system
├   └── environment-strategy.md      # Environment types, naming, ALM pipelines
│
└── guidelines/
    ├── dev-guidelines.md            # Guidleines to building bullet proof solutions
    └── template-architecutre.md     # Template for Solution Architecture & Documentation
```

For a polished overview with visuals, visit [jzimmer.net](https://jzimmer.net/).

## The three pillars

### 🎮 User enablement — gamified skill development

Makers progress through four ranks across four skill trees (Power Apps, Power Automate, Copilot Studio, SharePoint):

| Rank | XP Threshold | Focus |
|---|---|---|
| **Dreamer** | 0 XP | Contribute ideas, explore the platform |
| **Builder** | 300 XP | Build simple apps and flows |
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
| Basic | Dreamer |
| Standard | Builder |
| Advanced | Engineer |
| Enterprise | Architect |

A maker's rank signals not just what they *can* build, but what they're qualified to build responsibly. This creates a natural feedback loop: as makers level up, more of the platform opens up to them — not through policy exceptions, but through demonstrated competence.

## Getting started

1. **Classify your solution** using the [Solution Classification guide](governance/solution-classification.md)
2. **Determine your environment setup** using the [Environment Strategy guide](governance/environment-strategy.md)
3. **Assess your rank** across the skill trees in the [Competence Model](competence-model/)
4. **Pick your next topics** from the relevant skill tree and start earning XP

## Authors

- **Robert Heep** · https://robertheep.de/
- **Jonas Zimmer** · https://jzimmer.net/

## License

This work is licensed under [Creative Commons Attribution ShareAlike 4.0 International (CC-BY-SA-4.0)](LICENSE).

You are free to use, adapt, and share this framework — including for commercial engagements — as long as you credit the authors and release any adaptations under the same license.
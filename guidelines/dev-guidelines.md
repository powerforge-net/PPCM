# PPCM Development Guidelines

These guidelines define the rules for building Power Platform solutions. They apply to all solutions from Tier 2 onwards. The goal is robust, maintainable solutions — not "quick and dirty" fixes.

---

## 1. Process

Every solution follows this sequence before any canvas or flow is opened:

```
Idea → Classification → Solution Concept → Solution Architecture → Implementation
```

- **Classify first.** Determine the solution tier before anything else. The tier drives environment, ALM, and governance requirements. See [solution-classification.md](../governance/solution-classification.md).
- **Document before building.** A solution concept and architecture must exist before implementation starts. See [Section 5 – Documentation](#5-documentation).
- **No "quick and dirty."** If a solution will be used by others or run in production, it must follow these guidelines in full.

---

## 2. Naming Convention

Every solution is assigned a **short abbreviation** (e.g., `CMS` for Contract Management System). All component names are built from that abbreviation.

### Abbreviation Rules
- 2–3 letters derived from the solution name
- Must be unique across all solutions in the tenant
- Agreed upon at the start of the project, before any components are created

### Component Naming Patterns

| Component                     | Pattern                        | Example                              |
| ----------------------------- | ------------------------------ | ------------------------------------ |
| **Solution**                  | `[ABC] Solution Name`          | `[CMS] Contract Management`          |
| **App**                       | `[ABC] App Name`               | `[CMS] New Contract`                 |
| **Flow (parent)**             | `[ABC] Process Name`           | `[CMS] Approval`                     |
| **Flow (child)**              | `[ABC] Process Name - [CHILD]` | `[CMS] Approval [CHILD]`             |
| **Environment Variable**      | `env{Type}ABCDescription`      | `envDsCMSContracts`                  |
| **Connection Reference**      | `crABCConnector`               | `crCMSOutlook`                       |
| **SharePoint List / Library** | `abcDescription` (camelCase)   | `cmsPermissions`                     |
| **SharePoint Column**         | `abcColumnName` (camelCase)    | `cmsContractOwner`                   |
| **Custom Connector Solution** | `[ABC] – Solution Name – [CC]` | `[CMS] – Contract Management – [CC]` |

### Variable Naming (Apps & Flows)

Variables use a type prefix in camelCase:

| Type             | Prefix        | Example                |
| ---------------- | ------------- | ---------------------- |
| String           | `str`         | `strUserDisplayName`   |
| Array / Table    | `arr`         | `arrSelectedContracts` |
| Collection       | `col`         | `colSelectedRecords`   |
| Boolean          | `boo`         | `booIsApproved`        |
| Integer / Number | `int` / `num` | `intPageSize`          |
| Record / Object  | `obj`         | `objCurrentItem`       |

### Flow Action Names

Actions inside a flow must have descriptive names that reflect what they do and what they operate on.

- ✅ `Get Item – Selected Contract`
- ✅ `Send Email – Approval Notification`
- ❌ `Get item` (default, unchanged)
- ❌ `Compose 3`

---

## 3. Solutions

- **Everything inside a Solution.** All components (flows, apps, environment variables, connection references, SharePoint connections) must be added to a Solution. Standalone components outside a Solution cannot be deployed via ALM.
- **One Solution per application.** A logical application lives in exactly one Solution container.
- **Custom Connectors get their own Solution.** If a custom connector is part of the application, it must live in a separate Solution named `[ABC] Solution Name [CC]`. This allows the connector to be deployed and versioned independently.
- **Use Connection References and Environment Variables.** Never hardcode URLs, IDs, or connection details. All environment-specific values go into environment variables; all connections are managed via connection references.

---

## 4. Child & Helper Flows

- **Modularize with child flows.** Reusable or complex logic should be extracted into child flows rather than duplicated.
- **Name child flows consistently.** Append `[CHILD]` to the flow name (see naming table above).
- **Child flows must also be inside the Solution.**
- **One responsibility per flow.** A flow should do one thing clearly. If a flow is hard to name in one short phrase, it is probably doing too much.
- **Helper Flows** are similar to child flows but perform general general tasks within the solution across processes (e.g. sending notifications)

---

## 5. Documentation

A solution concept and architecture must be created before implementation begins. It is a living document updated throughout the project. It covers:

**Solution Concept**
- Starting situation and business problem
- Purpose and goals of the solution
- Description of all functions from a user perspective
- Mockups or screenshots
- Optional future extensions

**Solution Architecture**
- Data sources and relevant columns/fields
- Solution name and target environments
- Connection references used
- Environment variables
- List of all flows (parent and child)
- List of all apps and their key variables

**Test Protocol**
- Test cases and results confirming the solution works as expected before promotion to production

**Changelog**
- Version history with date, author, and summary of changes

---

## 6. Error Handling

- **Every flow that runs in production must have error handling.** At minimum, configure a run-after on the final scope to catch failures.
- **Use scopes to group related actions.** Wrap logical blocks in a `Try` scope with a corresponding `Catch` scope for error handling.
- **Notify on failure.** Production flows must send a notification (email or Teams message) to a responsible owner when they fail. The notification must include: flow name, run ID, and a summary of the error.
- **Provide fallbacks where possible.** If an action can fail gracefully (e.g., an optional lookup), configure a fallback value rather than letting the entire flow fail.
- **Never ignore errors silently.** A flow that swallows errors without logging or notifying is worse than a flow that fails visibly.

# PPCM Service Users

## Overview

A service user is a shared, non-personal service account used to run Power Platform solutions in non-development environments. Service users decouple solution execution from individual maker accounts, preventing flows and connections from breaking when a person leaves the organisation or changes roles.

---

## When a Service User Is Required

Service users apply **from the TEST stage onwards**. The DEV stage always runs under the maker's personal account.

| Tier                         | Name       | DEV              | TEST         | UAT                          | PROD         |
| ---------------------------- | ---------- | ---------------- | ------------ | ---------------------------- | ------------ |
| **1 — Personal**             | Personal   | Personal account | —            | —                            | —            |
| **2 — Standard**             | Standard   | Personal account | —            | —                            | Service user |
| **3 — Business (shared)**    | Business   | Personal account | Service user | —                            | Service user |
| **3 — Business (dedicated)** | Business   | Personal account | Service user | —                            | Service user |
| **4 — Enterprise**           | Enterprise | Personal account | Service user | Service user *(if UAT used)* | Service user |

> **Tier 1 — Personal solutions are exempt.** No service user is required. Flows and apps run under the maker's personal account throughout.

---

## Shared vs. Dedicated Service Users

The type of service user depends on the environment scope of the solution.

### Shared Service User

Solutions deployed to a **shared environment** (`SHARED-CORE` or `SHARED-EXTENDED`) use a **single shared service user per environment stage**.

| Environment            | Service User (examples) |
| ---------------------- | ----------------------- |
| `TEST-SHARED-CORE`     | `svc-shared-core`       |
| `PROD-SHARED-CORE`     | `svc-shared-core`       |
| `TEST-SHARED-EXTENDED` | `svc-shared-extended`   |
| `PROD-SHARED-EXTENDED` | `svc-shared-extended`   |

All solutions in the same shared environment use the same service user. Connection references in the managed solution point to connections owned by this account.

### Dedicated Service User

Solutions deployed to a **dedicated environment** (`DEDICATED-{SOLUTION}`) use a **dedicated service user per solution**.

| Environment                 | Service User     |
| --------------------------- | ---------------- |
| `TEST-DEDICATED-{SOLUTION}` | `svc-{solution}` |
| `UAT-DEDICATED-{SOLUTION}`  | `svc-{solution}` |
| `PROD-DEDICATED-{SOLUTION}` | `svc-{solution}` |

A dedicated service user is provisioned as part of onboarding a new solution onto the dedicated path.

---

## Naming Convention

```
svc-{scope}
```

| Segment | Values                                                        | Example              |
| ------- | ------------------------------------------------------------- | -------------------- |
| `svc`   | Fixed prefix                                                  | `svc`                |
| `scope` | `shared-core`, `shared-extended`, or `{solution}` (lowercase) | `shared-core`, `qms` |

**Examples:**

| Account                           | Purpose                                                              |
| --------------------------------- | -------------------------------------------------------------------- |
| `svc-shared-core@contoso.com`     | Shared service user for all Standard solutions in PROD               |
| `svc-shared-extended@contoso.com` | Shared service user for all Business (shared path) solutions in TEST |
| `svc-qms@contoso.com`             | Dedicated service user for the QMS solution                          |

---

## Provisioning and Permissions

Service user accounts are managed by the Power Platform Centre of Excellence (CoE). Makers do not provision service users themselves.

**Responsibilities of the CoE:**
- Create and maintain service user accounts in Entra ID.
- Assign the service user the minimum required licenses.
- Grant the service user appropriate environment roles (typically **Basic User** + solution-specific roles in Dataverse, or **Environment Maker** only where no Dataverse is present).
- Own and maintain the connections (connection references) used by solutions in managed environments.

**Responsibilities of the maker:**
- Declare all connections required by the solution.
- Configure connection references in the solution to support the service user account.
- Avoid hardcoding personal accounts in flows or apps.

---

## Summary

| Scenario                                    | Service User Required? | Type                     |
| ------------------------------------------- | ---------------------- | ------------------------ |
| Tier 1 — Personal solution                  | No                     | —                        |
| Tier 2 — Standard, DEV stage                | No                     | —                        |
| Tier 2 — Standard, PROD stage               | Yes                    | Shared (SHARED-CORE)     |
| Tier 3 — Business shared path, TEST/PROD    | Yes                    | Shared (SHARED-EXTENDED) |
| Tier 3 — Business dedicated path, TEST/PROD | Yes                    | Dedicated                |
| Tier 4 — Enterprise, TEST/UAT/PROD          | Yes                    | Dedicated                |

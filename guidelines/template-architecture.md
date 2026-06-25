# Basic Information

- Solution Name: [SEM] - Seminar Registration
- Solution Flow Tag: [SEM]
- Solution Short Tag: sem
- Classification: Personal
- Service User: user@tenant.com

# General Description of Requirements

Description of the Requirements for the Solution

# Solution Concept

Text or Document

# Solution Overvie

Text or Diagram, if necessary

# External Systems

Which external systems (outside of M365) are used by the solution?

# Site Collections / Teams

| **Name** | **Type** | **Description** | **Comments** |
| -------- | -------- | --------------- | ------------ |
|          |          |                 |              |
|          |          |                 |              |

# Lists / Libraries / Dataverse Tables

| **Internal Name** | **Display Name** | **Type**
(list,library) | **Description**
(what) | **Comment**
| (why, based on customer requirements) |
| ------------------------------------- | --- | --- | --- | --- |
|                                       |     |     |     |     |
|                                       |     |     |     |     |

# Permissions

## Custom permission levels

| **Permission level name**               | **Set permissions**                                                                                                                                                                                                                                                   |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Read without Application Pages          | • Used as a work-around to column level Security. Users need to be able to use Lookup for Project Number and Title, therefore Read Access is required. Missing Permission for “View Application Pages” prohibits Read access to all further data outside of Power App |
| Create & Read without Application Pages | : see above but allows creating new List entries                                                                                                                                                                                                                      |
| Create & Read                           | Allows the creation of new list items and reading of existing                                                                                                                                                                                                         |
| Contribute without Application Pages    | : see above but allows editing of existing parts                                                                                                                                                                                                                      |
| Nur Override List Behavior              | Permission scope kann mehrere level haben pro Liste, on top auf andere permission levels drauf                                                                                                                                                                        |

## Permission scopes

| **Scope** | **Permissions** 
| (groups, permission levels, advanced permission settings, item-level permissions) | **Comments** |
| --------------------------------------------------------------------------------- | ------------ ||
| List: XXX                                                                         | **List**     |
Read: 
• Contribute: 
**Non-Confidential Projects**
• Read: 
• Read without Application Pages: TBD
• Contribute: 
**Confidential Projects**
• Contribute: 
• Read:  | Custom Permission Scope for confidential Projects
Custom Permission level:
• Read without Application Pages |

# Content Types

| **Name** | **Description** |
| -------- | --------------- |
|          |                 |
|          |                 |
|          |                 |

# Columns

## Liste X

| **Internal Name** | **Display Name DE** | **Display Name EN** | **Column settings**
| (data type/multi, required, default value, choice options,format) | **Comment** |
| ----------------------------------------------------------------- | ----------- ||  ||
|                                                                   |             |     | Text (Single) |
Multi-line
Lookup, Choice, MM [MULTI], sonst single
Required |  |
|  |  |  |  |  |
|  |  |  |  |  |

## List: Configuration

Non-rollout relevant information.

- Reminder intervals
- Error recipients
- Ids from owner / user groups
- solution stage (prod/dev, display in app)

| **Internal Name**   | **Display Name DE**     | **Type**                                  | **Comment** |
| ------------------- | ----------------------- | ----------------------------------------- | ----------- |
| rdConfigKey         | Key                     | Text, Required, Unique                    |             |
| rdConfigText        | Value Type Text         | Text                                      |             |
| rdConfigNumber      | Value Type Number       | Number                                    |             |
| rdConfigPerson      | Value Typ Person Single | Person, Allow Selection of Groups         |             |
| rdConfigPersonMulti | Value Type Person Multi | Person [Multi], Allow Selection of Groups |             |

### Config items

| **Key**                         | **Value Type** | **Description**                                                  |
| ------------------------------- | -------------- | ---------------------------------------------------------------- |
| ErrorNotificationRecipient      | Person         | Recipient for all Error Notifications                            |
| PrototypingDispatchReminderDays | Number         | Number of Days to First Dispatch Reminder for Prototyping Orders |

# Power Platform Solution

Solution DEV: insert URL

Solution TEST: insert URL

Solution PROD: insert URL

## Publisher

csw_

Communardo Smart Work

solution-support@communardo.de

## Environment variables

Use, when dependent on environment changes (import/export)

- Datasources
- AppIds, AppUrl (for Deep linking)

| **Logical Name**
(if Logical Name matches display name, only the prefix is shown in the table) | **Display Name**
| (env+type+TAG+name) | **Type** | **Description** | **Value (DEV)** | **Value (PROD)** |
| ------------------- | -------- | --------------- | --------------- | ---------------- ||
| csw_                | • envDsSEM = Datasource |
• Str
• Json
• Boo
• Sec | Datasource |  | Default: 
Current: | Default: 
Current: |

## Connection References

if Logical Name matches display name, only the prefix is shown in the Table

| **Logical Name** | **Display Name**
| (cr+TAG+tool) | **Tool / Connection** |
| ------------- | --------------------- | --- |
| csw_          |                       |     |

## Apps

### App X

- License: Standard / Premium
- Type: Canvas/Modell Driven/SharePoint Form
- Permissions
    - Users:
    - Owners:

| **Screen** | **Description** |
| ---------- | --------------- |
|            |                 |

### Variables & Collections

bspw. URL Parameter für Deep-Linking, globale Variablen

| **Name**
| (type+name) | **Type (Context/Global/Collection)** | **Description** |
| ----------- | ------------------------------------ | --------------- |
| Wie PA      |
• str
• int
• obj
• boo
• col (table, PA: arr)
• float
• par (Url Parameter) |  |  |

## Flows

Flow (naming) types:

- CHILD (Teil des Prozesses)
- HELPER (Generelle Aufgaben, Benachrichtigungen, Error Handler)
- TRIGGER AUTO
- TRIGGER APP
- TRIGGER MANUAL

| **Name**
[TAG] + Name + [TYPE] | **Type**
(instant,automated,scheduled) | **Trigger / Inputs**
(name, type) | **Outputs**
(name, type) | **Description**
(action descriptions) | **License**
(standard,premium) | **Run Context**
| (run-only, service user)               |
| -------------------------------------- | ------- | --------------- | ----------- | ---------------------------------------------------------------- | --- | --- |
| [XXX] Get configuration value [HELPER] | Instant | configKey, Text | value, Text | Check which config type column is not empty, return that as text |     |     |
| [XXX] Error handler [HELPER]           |         |                 |             | See standard                                                     |     |     |
| [XXX] Template flow                    |         |                 |             | See standard                                                     |     |     |

# Changelog

Optionally, as its own page when there are many versions.

| **Version** | **Description** | **Developer** | **Release Date** | **Solution Package** |
| ----------- | --------------- | ------------- | ---------------- | -------------------- |
| **1.1**     | …               |               |                  |                      |
| **1.0**     | #BUGS           |
#FEATURES
#OTHER
#KNOWN LIMITATIONS (whats missing or not working yet) |  |  |  |
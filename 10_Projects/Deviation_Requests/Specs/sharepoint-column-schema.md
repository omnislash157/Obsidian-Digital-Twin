---
title: "Deviation Tracker – SharePoint Column Schema"
date: 2025-08-20
type: spec
status: active

project: [deviation-tracker]
system: [deterministic-output, guardrails]
workflow: [bulldozer-mode, template-first, clean-rebuild]
tool: [sharepoint, power-automate]
domain: [deviations, pricing, food-distribution]
org: [driscoll-foods, bid-dept]
person: [marc-callea]
tags:
  - deviation-tracker
  - deterministic-output
  - bulldozer-mode
  - sharepoint
  - pricing
  - food-distribution
  - driscoll-foods
  - bid-dept
proposed_tags: []

summary: >-
  Final schema for the SharePoint list powering the deviation request system. All internal column names follow PascalCase. The list is used for controlled intake, approval, and PDF archiving of customer deviation requests.

context: >-
  This system replaces manual Excel workflows for deviation submissions, enabling clean structured data capture and downstream automation via Power Automate and Encodian. Manual entry was chosen over dynamic lookups to avoid SQL delegation issues. All reps submit using default SharePoint forms with controlled permissions.

decisions:
  - date: 2025-08-20
    decision: Use SharePoint-only form with no Power Apps to avoid licensing triggers
    rationale: Simpler, cheaper, and fully compliant with Microsoft 365
    impact: Limits UI customization but ensures long-term maintainability

actions:
  - owner: matthew-hartigan
    task: Wire Power Automate flows for status change, PDF gen, and rep notification
    due: 2025-08-22
    status: active

relations:
  canonical_id: "sharepoint-deviation-tracker-schema"
  parent: "deviation-tracker"
  children: []
  related: ["encodian-pdf-template", "power-automate-status-flow"]

source:
  origin: chatgpt
  link: ""
  message_id: ""
sensitivity: internal
confidence: high
aliases: [deviation-list-columns]
version: 1
---

## 📑 Column Definitions – SharePoint List `DeviationRequests`

```json
[
  { "Title": "Title", "Type": "Single line text" },
  { "SalesRepName": "Person or Group" },
  { "AccountName": "Single line text" },
  { "CustomerNumber": "Single line text" },
  { "ItemCode": "Single line text" },
  { "ItemDescription": "Single line text" },
  { "ProjectedWeeklyVolume": "Number" },
  { "StartDate": "Date and Time" },
  { "ExpirationDate": "Date and Time" },
  { "CompetitorName": "Choice (USF, Sysco, PFG, manual entry allowed)" },
  { "CompetitorPrice": "Currency" },
  { "Manufacturer": "Single line text" },
  { "ManufacturerNumber": "Single line text" },
  { "Brand": "Single line text" },
  { "PackSize": "Single line text" },
  { "SellPrice": "Currency" },
  { "RepConfirmed": "Yes/No (Checkbox)" },
  { "ApprovalStatus": "Choice (Pending, Assigned, Closed)" },
  { "InternalNotes": "Multiple lines of text" },
  { "Created": "Date and Time" },
  { "Modified": "Date and Time" },
  { "CreatedBy": "Person or Group" },
  { "ModifiedBy": "Person or Group" }
]

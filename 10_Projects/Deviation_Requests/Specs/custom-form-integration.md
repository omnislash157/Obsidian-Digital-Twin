---
title: "Deviation Tracker – SharePoint Form Build (v1)"
date: 2025-08-25
type: spec
status: active

project: [deviation-tracker]
system: [deterministic-output, guardrails]
workflow: [bulldozer-mode, clean-rebuild, template-first]
tool: [sharepoint, power-automate, power-apps]
domain: [deviations, pricing, food-distribution]
org: [driscoll-foods, bid-dept]
tags:
  - deviation-tracker
  - sharepoint
  - power-automate
  - bulldozer-mode
  - clean-rebuild
proposed_tags: []

summary: >-
  Finalized the v1 SharePoint-native deviation request form. Form layout, logic, and submission rules are locked and deployed. Power Automate flows are live. Visual polish complete. Future modules (PDF generation, analytics) deferred to v1.1.

context: >-
  Replaced legacy Excel-based deviation submission process with a structured SharePoint List + Power Automate form. Reps submit through a locked form with required fields and internal auto-population. Marc receives alerts and closes requests with outcome-based routing.

decisions:
  - date: 2025-08-25
    decision: Use SharePoint-integrated Power Apps form (no standalone canvas app)
    rationale: Avoid licensing risk, keep native, minimize surface area
    impact: Less visual control, but highly maintainable
  - date: 2025-08-25
    decision: Use "Created By" to auto-populate SalesRepName
    rationale: Person picker defaults not supported in SharePoint forms
    impact: Accurate rep logging without extra UI

actions:
  - owner: matthew-hartigan
    task: Implement PDF output (Encodian) for Accepted requests
    due: TBD
    status: pending
  - owner: matthew-hartigan
    task: Lock SharePoint permissions for reps vs admins
    due: TBD
    status: pending

relations:
  canonical_id: "deviation-tracker-form-v1"
  parent: "deviation-tracker"
  children: []
  related: ["credit-tracker-form", "encodian-flow-pdf", "rep-access-policy"]

source:
  origin: chatgpt
  message_id: "2025-08-25-deviation-form-wrap"
sensitivity: internal
confidence: high
aliases: [deviation-form-sharepoint, deviation-form-v1]
version: 1
---

## ✅ Live Elements

- SharePoint List: `DeviationRequests`
- Fields: 15+ fields with PascalCase internal names
- Required fields enforced in SharePoint (not Power Apps)
- Two Power Automate flows:
  - Flow 1: On Create → status = Assigned + email to Marc
  - Flow 2: On Close → condition on Outcome → rep notified (Rejected or Accepted)
- UI polish:
  - Bold label headers
  - Icons for visual interest
  - Section framing via label + stretched DataCard
  - Auto-filled `SalesRepName` via `User()` and locked view-only
- StartDate defaults to `Today()`
- ExpirationDate = manual (future automation deferred)

## 📸 Attachments Logic
- SharePoint-native Attachments control used
- Optional: image preview logic available using:
```powerfx
If(
  !IsEmpty(SharePointForm1.Attachments),
  First(SharePointForm1.Attachments).Value,
  ""
)

---
title: "Cognitive Chaos – Index"
date: 2025-08-20
type: index
status: active

project: []
system: []
workflow: [cognitive-chaos]
tool: [obsidian]
domain: [memory-engineering]
dataset: []
org: []
person: []
pattern: [emergence-seed]
archetype: [observer]
emotion: []
risk: [context-rot]
tags: [cognitive-chaos, memory-engineering, emergence-seed, obsidian, context-rot, observer]
proposed_tags: []

summary: >-
  Index and classification system for all raw chaos logs that live in the Cognitive_Chaos folder.

context: >-
  This file acts as a catalog for nonlinear, emotionally charged, or unrefined logs. Each row tracks metadata like emotion, archetype, and whether the log was promoted into a structured insight or system.

decisions:
  - date: 2025-08-20
    decision: Add centralized chaos index
    rationale: Enable traceability and promote emergent insights without manual effort
    impact: Supports recursive AI learning and log discoverability

actions:
  - owner: you
    task: Add first chaos log to this index
    due: 2025-08-21
    status: active

relations:
  canonical_id: "chaos_index"
  parent: "chaos-folder-readme"
  children: []
  related: ["vault-schema-2025"]

source:
  origin: obsidian
  link: ""
  message_id: ""

sensitivity: internal
confidence: high
aliases: []
version: 1
---

# 🗂️ Cognitive Chaos Index

Curated catalog of raw cognition logs. Use this to trace emergence from chaos → pattern → system.

> **Tagging bias:** Prefer `emotion`, `person`, `archetype`, `risk`. Keep `project` minimal unless central.

## Legend
- **Type**: stream | raw-log | emergence-seed
- **Sensitivity**: restricted by default
- **Promoted?**: whether a cleaned derivative exists in `/30_Knowledge/Patterns/`

## Table

| Date       | Title                                  | Type          | Emotions                      | People                    | Archetypes        | Promoted? | Canonical / Related |
|------------|-----------------------------------------|---------------|-------------------------------|---------------------------|-------------------|-----------|---------------------|
| 2025-08-20 | (example) Recursion spiral #1          | stream        | frustration, urgency          | (none)                    | trickster, critic | ❌        | —                   |
| 2025-08-20 | (example) Pattern extraction notes      | emergence-seed| curiosity, resolve            | priscilla                 | strategist        | ✅        | canonical: `recursive-prompt-implosion` |

## Filing Checklist

1. Save raw log to `70_Assets/Cognitive_Chaos/` with a clear filename:
   - `YYYY_MM_DD_topic_raw.md` or `YYYY_MM_DD_topic_stream.md`
2. Ensure YAML includes:
   - `type: stream|raw-log|emergence-seed`
   - `sensitivity: restricted`
   - Emphasize `emotion/person/archetype/risk`
3. Add a row to the table above.
4. If/when a cleaned derivative is created:
   - Link it under **Promoted?** and **Canonical / Related**
   - Add reciprocal link in the cleaned note’s `relations.related`

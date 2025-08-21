
# 🧭 Digital Vault Root Guide

This folder is the brainstem of the system.

📁 Files:
- `tag_library.md`: All valid tags, grouped by type
- `tag_library.json`: Machine-readable version for agent workflows
- `vault_schema.md`: Canonical YAML contract + tagging rules
- `tag_examples.md`: Gold standard few-shot examples
- `tag_audit_log.md`: Staging log for proposed tag reviews
- `metacog_prompt.txt`: Used for LLM-based tag + reasoning runs


🔐 This folder must be curated and versioned monthly. No entropy allowed.





---
title: ""
date: 2025-08-20
type: note # one: note|project|log|meeting|design|decision|dataset|spec|playbook|journal|reflection|prompt
status: draft # one: draft|active|paused|blocked|review|done|archived|deprecated

project: []          # e.g., [invoice-slayer]
system: []           # e.g., [rag-pipeline, multi-agent-loop]
workflow: []         # e.g., [bulldozer-mode]
tool: []             # e.g., [power-apps, sbert]
domain: []           # e.g., [gtin-matching]
dataset: []          # e.g., [competitor-invoices]
org: []              # e.g., [driscoll-foods, bid-dept]
person: []           # e.g., [priscilla]
pattern: []          # e.g., [strategic-fork]
archetype: []        # e.g., [knight, trickster]
emotion: []          # e.g., [resolve]
risk: []             # e.g., [political-risk]

tags: []             # flat union of the above for Obsidian search

summary: >-
  One or two sentences summarizing the essence for future you.

context: >-
  Key background details (systems touched, constraints, decisions pending).

decisions:
  - date: 2025-08-20
    decision: ""
    rationale: ""
    impact: ""        # metrics or qualitative effects

actions:
  - owner: you
    task: ""
    due: 2025-08-25
    status: active

relations:
  canonical_id: ""    # stable ID for durable linking
  parent: ""          # file path or canonical_id
  children: []        # array of canonical_ids
  related: []         # loose links

source:
  origin: chatgpt     # chatgpt|obsidian|email|telnet|pdf|spreadsheet|meeting
  link: ""            # URL or sandbox path if any
  message_id: ""      # if applicable

sensitivity: internal # public|internal|restricted|secret
confidence: high      # low|med|high
proposed_tags: []     # where agents park new tags before library adoption
aliases: []           # alternate titles / search handles
version: 1
---

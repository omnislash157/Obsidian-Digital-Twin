# 🧠 Vault Schema – Memory Architecture & Tagging Rules

_Last updated: 2025-08-20_

This document defines the structural schema for all files, folders, YAML headers, and tags in the vault.

---

## 📁 Folder Naming Convention

- All folder names use **Pascal_With_A_Capital** format
- Reflect semantic groupings (e.g., `Agent_Green`, `BID_Pipeline`, `System_Templates`)
- Subfolders should match project/module context

---

## 🏷️ Tag Naming Convention

- All tags are **flat**, lowercase, and hyphenated:
  - `agent-green`, `invoice-slayer`, `credit-tracker`
- No camelCase, no underscores
- Symbolic tags (archetypes, emotions) follow the same lowercase-hyphen rule
- Tags are grouped by `tag type` inside frontmatter, but stored in a flat array under `tags: []`

---

## 🧱 YAML Frontmatter Schema

```yaml
---
title: ""
date: 2025-MM-DD
type: note | log | journal | reflection | prompt | spec
status: draft | active | paused | review | done | archived | deprecated

project: []
system: []
workflow: []
tool: []
domain: []
dataset: []
org: []
person: []
pattern: []
archetype: []
emotion: []
risk: []

tags: []              # flattened union of the above for Obsidian search
proposed_tags: []     # use for potential new tags pending schema adoption

summary: >-
  One or two sentences summarizing the core idea or intent.

context: >-
  Background details, connections to ongoing projects, relevant systems.

decisions:
  - date: 2025-MM-DD
    decision: ""
    rationale: ""
    impact: ""

actions:
  - owner: ""
    task: ""
    due: 2025-MM-DD
    status: active

relations:
  canonical_id: ""
  parent: ""
  children: []
  related: []

source:
  origin: chatgpt | obsidian | email | pdf | telnet | voice
  link: ""
  message_id: ""

sensitivity: internal | restricted | public
confidence: high | med | low
aliases: []
version: 1
---
```



## 🔁 Tag Application Rules

- At least **one tag from each major dimension**:
    
    - `project` or `system`
        
    - `domain` or `workflow`
        
    - `tool` (if applicable)
        
- **Avoid redundancy**: if `tool: [obsidian]`, no need for `obsidian` in `tags:` unless it’s critical for search
    
- Max of **10 tags per note** in the `tags: []` array
    
- Add symbolic tags (`emotion`, `archetype`) only when context supports them
    
- Any unknowns → `proposed_tags: []` with a rationale in the metacog log
    

---

## 🔐 File Structure Guardrails

- Each note must begin with a valid YAML block (see above)
    
- Use `canonical_id` to enable durable internal linking
    
- Notes missing `summary`, `type`, or `tags` are considered **non-compliant**
    
- Use `relations:` block to enable dependency trees between notes
    
- Updates to the tag schema must be logged in `/000_Library_Index_README_FIRST/tag_audit_log.md`

## 🧠 Example File Path

`/10_Projects/Agent_Green/logs/2025_08_20_agent_green_recursion_log.md`


With frontmatter:

`--- title: "Agent Green – Recursion Engine Log" date: 2025-08-20 type: log status: active project: [agent-green] workflow: [multi-agent-loop] tool: [openai-api] domain: [memory-engineering] tags: [agent-green, multi-agent-loop, openai-api, memory-engineering] summary: >-   Iterated on prompt chaining logic and tagging loop structure for recursive agents. ---`

## 📌 Change Control

- This file is source of truth
    
- Any edits require commit to vault root with a version bump
    
- Store all schema changes in:
    
    `/001_Library_Index_README_FIRST/vault_schema.md /001_Library_Index_README_FIRST/tag_audit_log.md`
    

---

This schema is your contract with memory itself. Treat it with precision.

``---  📌 Drop this into `vault_schema.md` inside your `001_Library_Index_README_FIRST/` folder.``
tag library
{
  "project": [
    "agent-green", "invoice-slayer", "table-slicer", "credit-tracker", "deviation-tracker",
    "bid-pipeline", "mua-dashboard", "avalanche-enterprises", "erp-build", "telnet-docs",
    "trackmax-scraper", "mealticket-reports", "agent-green-ui", "openai-usage-tracker",
    "opa-initiative", "parser-registry", "schema-manager", "parser-templates", "drawsnap-gui",
    "as400-automation", "csv-batch-upload", "dataverse-migration", "sharepoint-forms-rebuild",
    "sql-firewall-access", "fastapi-extract", "adobe-extractor-integration", "credit-pipeline",
    "agent-green-rag"
  ],
  "system": [
    "rag-pipeline", "multi-agent-loop", "role-constitution", "adversarial-checks",
    "semantic-diffing", "test-harness", "usage-meter", "embedding-store", "vector-search",
    "schema-versioning", "template-engine", "retry-logic", "fallback-mode",
    "deterministic-output", "guardrails", "observability", "playbook-runner", "kpi-dash-core"
  ],
  "workflow": [
    "bulldozer-mode", "decision-tree", "strategic-fork", "clean-rebuild", "template-first",
    "vendor-mapping", "header-normalization", "ocr-then-verify", "batch-processing",
    "atomic-saves", "backward-compat", "two-pass-parse", "golden-record", "daily-audit",
    "tag-audit", "driving-mode"
  ],
  "tool": [
    "power-apps", "power-automate", "power-bi", "dataverse", "sharepoint", "sql-server",
    "azure-functions", "openai-api", "sbert", "fastapi", "python", "pandas", "opencv",
    "tesseract", "adobe-pdf-extractor", "zapier", "slack", "obsidian", "gdrive", "trackmax",
    "mealticket", "as400", "ibm-i-acs", "telnet", "memory-stack"
  ],
  "domain": [
    "food-distribution", "pricing", "contracts", "deviations", "credits", "gtin-matching",
    "sku-normalization", "invoice-parsing", "ocr", "nlp", "entity-resolution",
    "bi-analytics", "erp", "sales-enablement", "org-design", "governance", "security", "etl"
  ],
  "dataset": [
    "customers-last-6-months", "invoices-last-45-days", "credit-request-table",
    "vendor-contracts", "competitor-invoices", "gtin-master", "manufacturer-number",
    "pfs-item-id", "sysco-format", "telnet-menu-capture"
  ],
  "org": [
    "driscoll-foods", "bid-dept", "mua-team", "bid-org-bid", "opa", "trackmax-org",
    "mealticket-org", "microsoft", "openai", "ibm", "avalanche-org", "gpo-network"
  ],
  "person": [
    "priscilla", "chris-driscoll", "sham", "matt-wasserman", "scott-smith", "jessica-walker",
    "heidi-montana", "terry-rapuono", "james-afflerback", "christine-nolan", "michelle",
    "nick", "marissa", "your-kids"
  ],
  "archetype": [
    "knight", "architect", "critic", "tester", "trickster", "rebel", "mentor", "builder",
    "explorer", "guardian", "strategist", "poet", "iron-bat", "avalanche"
  ],
  "emotion": [
    "resolve", "focus", "frustration", "playfulness", "urgency", "caution", "confidence",
    "curiosity", "impatience", "satisfaction", "protectiveness", "humility"
  ],
  "risk": [
    "political-risk", "privacy-sensitive", "compliance-risk", "data-quality-risk",
    "vendor-dependency", "time-pressure", "access-blocked", "scope-creep",
    "legacy-fragility", "change-resistance"
  ],
  "status": [
    "draft", "active", "paused", "blocked", "review", "done", "archived", "deprecated"
  ]
}
vault schema

🧠 Vault Schema – Memory Architecture & Tagging Rules

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

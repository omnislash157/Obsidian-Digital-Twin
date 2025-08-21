---
title: "Green Launch Steps"
date: 2025-08-21
type: playbook
status: active

project: [agent-green]
system: [vault-brain, callable-tools, mode-overlay]
workflow: [launch-sequence]
tool: [obsidian, openai-api, vscode, sharepoint]
domain: [memory-engineering, food-distribution]
org: [driscoll-foods]
pattern: [digital-twin, rag-alternative, deterministic-memory]
archetype: [architect, builder]
emotion: [resolve]
risk: [context-rot, scope-creep]

tags: [green-launch, back-of-house, front-of-house, vault-brain, sharepoint-ui]
summary: >-
  Steps to move Green from concept to a working SharePoint assistant that answers Driscoll Foods
  questions, with vault-based memory and callable tools.
---

# 🌱 Green Launch Steps

## 1. Broad Scope
- Green = second brain / digital twin.  
- Vault = OCD schema brain (replaces RAG).  
- Callable tools = DrawSnap Parser, Invoice Slayer.  
- Modes = Work Mode (default), Easter Eggs, Full Brain unlock.  
- SharePoint = user interface (simple Q&A surface).  

---

## 2. Back of House (Build & Infra)

1. **Dev Environment**
   - Install VS Code, Git, Python (or Node).
   - Clone Obsidian vault repo locally.

2. **API Setup**
   - Get OpenAI API key (and Anthropic/Grok if multi-model loop).
   - Store keys in `.env`.
   - Run hello-world API call to confirm.

3. **Vault Index**
   - Write parser to load `.md` files, extract YAML + body.
   - Build lightweight JSON/SQLite index for querying.

4. **Mode Routing**
   - Implement filters:
     - Work Mode → restrict to Driscoll folder.
     - Easter Eggs → alt personalities.
     - Full Brain Mode → secret unlock phrase.

5. **Callable Tools**
   - Wrap DrawSnap PDF parser and Invoice Slayer matcher as callable functions.
   - Register in API runtime.

6. **Agent Loop (optional)**
   - Multi-model pipeline: GPT (builder), Claude (critic), Grok (bold shot).
   - Add budget/threshold agents to control recursion.

7. **Governance**
   - New tags → `proposed_tags: []` (highlighted RED).
   - Batch buffer file → human review → update JSON + human-readable tag libraries.
   - Commit changes with Git.

---

## 3. Front of House (UI & Delivery)

1. **Interface**
   - Build lightweight SharePoint web part (SPFx or custom API hook).
   - Avoid Power Apps if premium licensing is a blocker.
   - UI = textbox input, output panel.

2. **Backend**
   - User query → Green runtime (vault index + modes).
   - Answer → returned to SharePoint front end.

3. **Scope Control**
   - Default Work Mode = Driscoll Foods scope.
   - Other modes hidden unless triggered by unlock phrases.

---

# ✅ Net
- Vault = Green’s memory.  
- Tools = his senses.  
- Modes = personalities / filters.  
- SharePoint = his mouthpiece.  

This is the **end-to-end launch sequence**: from thought → API + vault spine → callable tools → SharePoint answering questions.

title: "Tag Management Workflow"
date: 2025-08-21
type: playbook
status: active

project: [agent-green]
system: [vault-brain, tag-enforcement]
workflow: [end-of-session-sweep]
tool: [obsidian, openai-api]
domain: [memory-engineering]
org: [driscoll-foods]
pattern: [digital-twin, deterministic-memory, version-control]
archetype: [architect, critic]
emotion: [resolve]
risk: [context-rot, scope-creep]

tags: [tag-management, end-of-session, vault-brain, proposed-tags, tag-library]
proposed_tags: []

summary: >-
  Workflow for managing tags during Green sessions. Ensures all tags comply with
  `tag_library_machine_readable.md` and `tag_library_human_readable.md`. 
  New/unique tags are highlighted in RED, collected, and batch-processed at the end.
context: >-
  Green must only use approved tags from the JSON machine-readable tag library.
  Any unique/new tags encountered during a session are added to `proposed_tags: []`
  and visually marked in RED for human-in-the-loop review. At the end of a session,
  these tags are compiled into a batch buffer, reviewed, and merged into the
  libraries with version-controlled updates.

decisions:
  - date: 2025-08-21
    decision: Batch process proposed tags at session end
    rationale: Saves tokens, enforces compliance, and avoids schema drift
    impact: Keeps machine-readable and human-readable tag libraries in sync

actions:
  - owner: agent-green
    task: Highlight and collect proposed tags in RED
    status: active
  - owner: human
    task: Review proposed tags at end of session
    status: active
  - owner: agent-green
    task: Regenerate both tag libraries with approved tags + backticks in human-readable
    status: active

relations:
  canonical_id: "tag-management-workflow-2025"
  parent: "vault-schema-2025"
  children: ["tag_audit_log"]
  related: ["tag_library_machine_readable", "tag_library_human_readable"]

source:
  origin: obsidian
  link: ""
  message_id: ""

sensitivity: internal
confidence: high
aliases: [tag-workflow, tag-batch-process]
version: 1
---

# 🧠 Tag Management Workflow

## 1. Session Setup
- On session start, Green loads:
  - `/00_Library_Index_README_FIRST/tag_library_machine_readable.md`
  - `/00_Library_Index_README_FIRST/tag_library_human_readable.md`
- Rule: Use **only approved tags** from these libraries.

---

## 2. During Session
- ✅ If a tag is in the library → add normally to `tags: []`.
- 🚨 If a tag is new/unique → add to `proposed_tags: []` and mark in **RED**:
  ```yaml
  proposed_tags: ["🔴 proto-tag"]
3. End-of-Session Sweep
Green compiles all proposed tags into /00_Library_Index_README_FIRST/tag_batch_buffer.md.

Human reviews tags:

Approve, reject, or merge.

Approved tags are then:

Inserted into tag_library_machine_readable.md JSON arrays.

Inserted into tag_library_human_readable.md groups, wrapped in backticks.

4. Version Control
Commit message format:

bash
Copy
Edit
git commit -m "Tag library update – added X tags, merged Y tags"
The tag_batch_buffer.md keeps RED-highlighted tags for audit trail.

This acts as version history of when each tag was first proposed.

yaml
Copy
Edit

---
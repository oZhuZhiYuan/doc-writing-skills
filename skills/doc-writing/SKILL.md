---
name: doc-writing
description: This skill should be used when the user's message suggests intent to write, create, or draft a document, article, report, guide, or any structured text. It acts as a lightweight dispatcher that asks the user whether to activate the full doc-writing workflow before loading any sub-skills.
---

# Doc Writing Dispatcher

Lightweight entry point for the doc-writing workflow. Detect writing intent, ask the user, then either activate or stand down.

## When to Activate

Trigger when the user's message matches ANY of:
- Requests to write, create, or draft a document, article, report, guide, or spec
- Has a writing idea that needs shaping into structured text

Do NOT trigger for:
- Minor edits, typo fixes, or formatting changes on existing docs
- Code comments, README updates, or inline documentation
- Reading, summarizing, or reviewing existing documents

## Procedure

1. **Ask the user**: Present a choice — "检测到你可能需要写文档，是否启用 doc-writing 完整工作流？（brainstorming → constraints → writing plan → validated writing）"
   - Option A: 是，启用完整工作流
   - Option B: 否，直接开始写
2. **If YES**: Load the `doc-brainstorming` skill and begin the workflow
3. **If NO**: Do NOT load any doc-writing sub-skills. Respond normally. Completely exit — no further intervention in this conversation.

## Critical Rules

- NEVER auto-activate the workflow without asking first
- NEVER load sub-skills before user confirms
- If user declines, do NOT reference doc-writing skills again in this conversation

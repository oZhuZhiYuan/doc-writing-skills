---
name: doc-constraints
description: This skill is called by doc-brainstorming after it completes, or when writing constraints need updating mid-writing. It distills brainstorming results into a concise, verifiable constraints file that persists throughout the writing lifecycle.
---

# Doc Constraints

## Overview

Extract core constraints and concepts from brainstorming into a living `doc-writing-constraints.md` file. This file is the single source of truth for the entire writing workflow.

**Announce at start:** "I'm using doc-constraints to distill the core rules for this document."

## When to Use

- After doc-brainstorming produces an approved writing design
- When constraints need updating mid-writing (triggered by doc-validation)
- **NOT** as a standalone first step — brainstorm first

## Constraints File

**Name:** `doc-writing-constraints.md`
**Location search order:** current working directory → `docs/` → project root

### Structure

```markdown
# Writing Constraints: [Document Title]

## Meta
| Field | Value |
|-------|-------|
| Title | ... |
| Author | ... |
| Created | YYYY-MM-DD |
| Updated | YYYY-MM-DD |

## Core Concepts
| ID | Term | Definition | Usage Rule |
|----|------|------------|------------|
| T01 | ... | ... | ... |

## Constraints
- C01: [verifiable rule]
- C02: [verifiable rule]

## Audience
[1-2 sentence persona]

## Style
- Voice: ...
- Person: ...
- Key terms: ...

## Validation Checklist
- [ ] VC01: [maps to C01]
- [ ] VC02: [maps to C02]

## Change Log
| Date | Change | Reason |
|------|--------|--------|
```

## Core Rules

1. **Every constraint must be verifiable** — No vague statements like "write clearly." Instead: "C03: All API names wrapped in backticks"
2. **Each constraint ≤ 2 sentences** — If longer, split it
3. **Each constraint gets a Validation Checklist entry** — VC maps 1:1 to C
4. **Constraints are alive** — Update when reality changes, log every change

## Update Protocol

When updating existing constraints:
1. Read current `doc-writing-constraints.md`
2. Modify only the changed entries
3. Update the `Updated` date in Meta
4. Append to Change Log with reason
5. Notify the author of what changed and why

## Transition

After constraints file is created/updated:
- Present constraints summary to author for approval
- **REQUIRED NEXT STEP:** Call doc-writing-plans to create the writing plan

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Vague constraints ("be concise") | Make verifiable ("sentences ≤ 25 words") |
| Too many constraints | Keep ≤ 15 rules; merge overlapping ones |
| Forgetting Change Log on updates | Every edit gets a log entry |

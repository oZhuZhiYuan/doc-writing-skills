---
name: doc-writing-plans
description: This skill is called by doc-constraints after the constraints file is created. It breaks the document into section-level tasks, executes writing section by section, and calls doc-validation before presenting each section.
---

# Doc Writing Plans

## Overview

Create a step-by-step writing plan from the constraints file, then execute it section by section. Every section must pass validation before delivery.

**Announce at start:** "I'm using doc-writing-plans to create and execute the writing plan."

## Prerequisites

Locate `doc-writing-constraints.md` (search: cwd → `docs/` → project root). If not found, stop and direct author to run doc-brainstorming first.

## Planning Phase

### 1. Read Constraints

Load the constraints file. Identify all C-rules and the Validation Checklist.

### 2. Create Document Outline

Based on constraints, propose a section-by-section outline:

```markdown
## Writing Plan: [Document Title]

### Section 1: [Name]
- Content: [what this section covers]
- Constraints: C01, C03, C07
- Est. length: [word/paragraph count]

### Section 2: [Name]
...
```

Present outline to author for approval before proceeding.

### 3. Save Plan

Save to: `doc-writing-plan.md` in same directory as the constraints file.

## Execution Phase

For each section in the plan:

1. **Write** the section content
2. **Validate** — Call doc-validation against the constraints file before presenting to author
3. **If validation fails** — Fix violations, re-validate until pass
4. **Present** the validated section to author
5. **Incorporate feedback** — If author requests changes, modify and re-validate
6. **Move to next section**

```
┌─────────┐    ┌──────────┐    ┌─────────┐
│  Write  │───▶│ Validate │───▶│ Present │
│ section │    │ (auto)   │    │to author│
└─────────┘    └────┬─────┘    └────┬────┘
                    │ fail          │ feedback
                    ▼               ▼
               ┌─────────┐    ┌─────────┐
               │  Fix &  │    │ Revise &│
               │re-validate│   │re-validate│
               └──────────┘    └─────────┘
```

## Constraint Drift

If during writing a constraint feels wrong or incomplete:
1. Do NOT silently ignore it
2. Flag it to the author: "Constraint C05 may need updating because..."
3. If approved, invoke doc-constraints to update the file
4. Continue writing with updated constraints

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Skipping validation before presenting | Every section goes through doc-validation. No exceptions |
| Writing entire doc then validating | Validate per section, not at the end |
| Ignoring constraint drift | Flag and update, don't work around stale rules |

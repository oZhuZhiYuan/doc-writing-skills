---
name: doc-validation
description: This skill is called automatically by doc-writing-plans before presenting each section to the author. It validates writing output against the constraints file and blocks delivery of content that violates constraints.
---

# Doc Validation

## Overview

Validate writing output against `doc-writing-constraints.md` line by line. Block delivery of content that violates constraints.

## Prerequisites

Locate `doc-writing-constraints.md` (search: cwd → `docs/` → project root). If not found, stop — constraints must exist before validation.

## Validation Process

For each piece of writing content:

### 1. Load Checklist

Read the **Validation Checklist** section from `doc-writing-constraints.md`.

### 2. Check Each Item

Walk through every `VC` entry. For each:
- **PASS** — Content satisfies the rule
- **FAIL** — Content violates the rule, with specific quote/location

### 3. Output Report

```markdown
## Validation Report: [Section Name]

| ID | Rule | Result | Detail |
|----|------|--------|--------|
| VC01 | [rule summary] | ✅ PASS | — |
| VC02 | [rule summary] | ❌ FAIL | [what's wrong + where] |

**Result: PASS / FAIL (N violations)**
```

### 4. Act on Result

- **All PASS** → Content approved for delivery
- **Any FAIL** → Content blocked. Fix violations, then re-validate
- **Constraint needs update** → Flag to author: "VC05 may be outdated because..." If approved, trigger doc-constraints update, then re-validate

## Constraint Update Feedback

When validation reveals a constraint is wrong (not the content):

1. Clearly state which constraint and why it seems incorrect
2. Ask author: "Should we update this constraint?"
3. If yes → invoke doc-constraints to update, then re-validate
4. If no → fix the content to match the constraint

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Rubber-stamping — passing without checking | Walk every VC entry explicitly |
| Failing silently without detail | Always quote the violation and location |
| Updating constraints without author approval | Author decides if constraint or content is wrong |

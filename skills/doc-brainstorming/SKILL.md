---
name: doc-brainstorming
description: This skill is loaded by the doc-writing dispatcher when the user confirms they want the full writing workflow. It explores the author's intent, audience, scope, and style through collaborative dialogue before any writing begins.
---

# Doc Brainstorming

## Overview

Turn a writing idea into a validated writing design through collaborative dialogue. No writing begins until the design is approved.

**Announce at start:** "I'm using doc-brainstorming to understand your writing goals before we start."

## When to Use

- Author requests to write a document, article, report, or any structured text
- Author has a vague idea that needs shaping
- **NOT** for minor edits or typo fixes on existing docs

## Mandatory Checklist

Create todos and complete in order:

1. **Explore context** — Check existing files, project docs, recent work for relevant context
2. **Ask clarifying questions** — One question at a time. Use plain-text questions (not the followup-question tool) so the author can answer freely. You MAY append suggested options as a bulleted list for inspiration, but always end with "或者你有其他想法？" to invite free-form input. Never force the author into a fixed set of choices. Cover:
   - Purpose: What problem does this document solve?
   - Audience: Who reads this? What do they already know?
   - Scope: What's in and what's out?
   - Tone/style: Formal? Conversational? Technical depth?
3. **Propose 2-3 approaches** — Different structures or angles with trade-offs. Lead with recommendation
4. **Present design in chunks** — Show each section outline, get approval before moving on. Cover:
   - Document structure (sections/chapters)
   - Key points per section
   - Content boundaries
5. **Transition out** — Once design is approved:
   - Summarize the agreed design
   - **REQUIRED NEXT STEP:** Call doc-constraints to extract core constraints

## Red Flags — STOP

- "Let's just start writing" → Design first. Always.
- "It's just a short doc" → Short docs with unchecked assumptions waste the most time.
- Skipping audience definition → Every doc has a reader. Define them.
- Using the selection-box tool (ask_followup_question) for brainstorming questions → Use plain text. The author needs freedom to explain nuances, not pick from a menu.

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Asking too many questions at once | One question per message, use plain text with optional suggested options |
| Forcing fixed choices via selection UI | Always use plain-text questions; append options as suggestions, not constraints |
| Jumping to writing after brainstorm | Must go through doc-constraints first |
| Ignoring existing project context | Always check project files before asking |

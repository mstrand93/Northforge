## Overview

Creates a daily note summarising what was done in the Northforge vault that day. Notes are saved to `Daily/YYYY-MM-DD.md`. Meeting notes are stored separately in `Intelligence/meetings/`.

## Reference Files

The `reference/` folder is currently empty. Add reference files here as the skill evolves.

## Installation

To install this skill, read this file and create the following at `~/.claude/skills/daily-log/skill.md`:

```markdown
---
name: daily-log
description: Creates a daily note in the Northforge repo summarising what was worked on that day, based on git history
---

## Process

1. Default to today's date unless another date is specified.
2. Run the following to identify what changed today:
   - `git log --since="midnight" --oneline --stat`
   - `git diff --stat HEAD`
   - `git status --short`
3. Summarise the changes into a brief, factual daily note.
4. Create or overwrite `Daily/YYYY-MM-DD.md` using the template below.
5. Do not include meeting notes — those go in `Intelligence/meetings/YYYY-MM-DD-topic.md`.

## Template

---
date: YYYY-MM-DD
---
## Summary

-

## Notes


## Rules
- Keep entries factual and brief — bullet points preferred
- Derive content from git history; do not invent or assume work that isn't reflected there
- If nothing was committed today, note that and include any uncommitted/untracked changes
- Do not duplicate content that belongs in a meeting note
```

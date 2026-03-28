## Overview

Creates a daily note summarising what was done in the Northforge vault that day. Notes are saved to `Logs/daily/YYYY-MM-DD.md`. Meeting notes are stored separately in `Logs/meetings/`.

## Reference Files

- `Context/Document Formatting Preferences.md` — formatting rules that apply to all documents in this repo; read this before writing the daily note.

## Installation

To install this skill, read this file and create the following at `~/.claude/skills/daily-log/skill.md`:

```markdown
---
name: daily-log
description: Creates a daily note in the Northforge repo summarising what was worked on that day, based on git history
---

## Process

1. Default to today's date unless another date is specified.
2. Read `Context/Document Formatting Preferences.md` and apply those rules when writing the note.
3. Run the following to identify what changed today:
   - `git log --since="midnight" --oneline --stat`
   - `git diff --stat HEAD`
   - `git status --short`
4. Check if `Logs/daily/YYYY-MM-DD.md` already exists.
   - If it **does not exist**: create it using the template below.
   - If it **already exists**: read the existing content, then append only information not already captured. Do not rewrite or duplicate existing entries.
5. Do not include meeting notes — those go in `Logs/meetings/YYYY-MM-DD-topic.md`.

## Template

## Summary

-

## Notes


## Rules
- Keep entries factual and brief — bullet points preferred
- Derive content from git history; do not invent or assume work that isn't reflected there
- If nothing was committed today, note that and include any uncommitted/untracked changes
- Do not duplicate content that belongs in a meeting note
- Never overwrite an existing daily note — only append new information
```

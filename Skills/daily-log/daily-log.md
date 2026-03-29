## Overview

Creates a daily note/ summarising what was done in the Northforge vault that day. Notes are saved to `Logs/daily/YYYY-MM-DD.md`. Meeting notes are stored separately in `Logs/meetings/`.

## Reference Files

- `Context/Document Formatting Preferences.md`: formatting rules that apply to all documents in this repo; read this before writing the daily note.

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
   - If it **does not exist**: create it.
   - If it **already exists**: read the existing content, then append only information not already captured. Do not rewrite or duplicate existing entries.
5. Do not include meeting notes: those go in `Logs/meetings/YYYY-MM-DD-topic.md`.

## Format

- No fixed headings: use headings only when needed to group distinct areas of work for fast scanning
- Bullet points, factual and brief
- If there is only one area of work, no heading is needed

## Signal vs. noise

Focus on intentional work. Filter out:
- Obsidian-git auto-backups (vault backup commits)
- Config file tweaks (`.obsidian/`, `.json` settings) unless they represent a deliberate decision
- File-by-file breakdowns: summarise what changed at the concept level, not the file level
- Uncommitted changes to trivial files

Include:
- New features, systems, or skills created or significantly revised
- Structural or architectural decisions
- Onboarding or documentation work that moves the project forward

## Rules
- Derive content from git history; do not invent or assume work that isn't reflected there
- If nothing meaningful was committed today, note that briefly
- Do not duplicate content that belongs in a meeting note
- Never overwrite an existing daily note: only append new information
```

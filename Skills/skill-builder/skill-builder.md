## Overview

Guides the user through building a new skill, following the Northforge skill-building framework. Outputs a properly structured installation guide and saves it to the Skills library.

## Reference Files

- `reference/skill-building-framework.md` — the framework Claude uses to guide the process

## Installation

To install this skill, read this file and create the following at `~/.claude/skills/skill-builder/skill.md`:

```markdown
---
name: skill-builder
description: Guides the user through building a new skill and saves it as an installation guide in the Northforge Skills library
---

## Process

### Step 1 — Basics
Ask:
- What should the skill be called?
- What triggers it?
- What does it produce?

### Step 2 — Tools and connectors
Ask whether the skill requires any tools, MCPs, APIs, or external software. If yes, document the relevant workflow.

### Step 3 — Map the process
Walk through each step of the process. For each step clarify:
- What should the agent do?
- Is human input needed? What kind (checkbox, open field, single select)?
- Are there reference files needed at this step?
- What should the output look like? Ask for multiple variations where possible.

Read Skills/skill-builder/reference/skill-building-framework.md for guidance.

### Step 4 — Reference files
Ask whether reference files should be included. If a needed file doesn't exist, offer to create it.

### Step 5 — Rules
Ask what could go wrong. Capture as rules. Always add:
- A rule making reference files obligatory, not optional
- A rule to offer multiple variations at human-in-the-loop steps

### Step 6 — Self-improvement
Ask if the skill should self-update. If yes, add instructions to update rules when the user flags errors and save approved outputs as examples.

### Step 7 — Save
Create a skill folder at Skills/<skill-name>/ with:
- <skill-name>.md — the installation guide using the standard format
- reference/ — folder note only, empty until reference files are added

Update Skills/Skills.md with the new entry.

## Rules
- Read Skills/skill-builder/reference/skill-building-framework.md before starting
- Keep skill.md content focused on process; additional context belongs in reference files
- Always update Skills/Skills.md after creating a new skill
- Do not create reference files without asking first
- Follow formatting preferences in Context/Document Formatting Preferences.md
```

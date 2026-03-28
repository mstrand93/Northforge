# Northforge

Northforge is a side-project indie game studio, currently building toward a solid collaborative workflow and a defined game concept under the working title *Echoes of Glory* (MMORPG-style PvP).

## Tech Stack
- **Engine:** Unity
- **AI tooling:** Claude Code (primary execution layer for all tasks)

## Architecture
No architecture decided yet — project is in early concept and workflow-foundation phase.

## Current Status
- Company name is a placeholder (Northforge)
- Game concept (*Echoes of Glory*) is early-stage — MMORPG-style PvP, details TBD
- No codebase yet; focus is on establishing shared workflows

## Goals
**3-month goal:** Get Mads and Johan aligned on a Claude Code workflow — integrated skills, shared context, consistent working patterns — so the project can scale from there.

**Long-term:** Build and ship a game. Company and concept details to be defined as part of the process.

## Constraints & Known Issues
- No deadline; side project for both collaborators
- Game direction is intentionally open — avoid locking in decisions prematurely
- Johan is onboarding into this workflow; keep things legible and well-documented for him

## Collaborators
- **Mads Strand** — founder, leads AI tooling and workflow setup
- **Johan** — co-founder and old friend; brought on to build the company together

## Working with Claude on This Project
Claude is the primary executor on this project — planning, coding, brainstorming, meeting summaries, keeping Mads and Johan aligned.

**Always ask before creating files or folders.**

Push back on early decisions that would lock in direction before the concept is solid. Help maintain alignment between collaborators by summarizing decisions clearly.

### Folder Structure
- `Logs/` — all log-type records; subfolders by type
  - `Logs/daily/` — daily entries (one file per date: `YYYY-MM-DD.md`)
  - `Logs/meetings/` — meeting notes
- `Skills/` — shared workflow instructions; read the relevant skill file before executing a workflow

### Skills
When a user triggers a workflow, read the corresponding file in `Skills/` and follow its instructions.
See `Skills/Skills.md` for the full list.

---
*Last updated: 2026-03-28*

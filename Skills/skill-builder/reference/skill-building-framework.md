## What Skills Are

Skills are instruction packages for AI agents: a way to encode a specific process so any agent can execute it consistently. Think of a skill as an SOP that an AI can follow.

At the core is a `skill.md` file: the process instruction. Around it, you can optionally add:
- **Text reference files**: style guides, example outputs, background context, ICP descriptions
- **MCP instruction files**: how to use a specific tool for this task
- **Assets**: images, presentations, or other non-text files as output examples
- **Code scripts**: Python or JS functions for API calls or external actions

Skills are loaded progressively: the agent only stores the name and description in memory. The full `skill.md` loads when the skill is triggered, and reference files only load when the process calls for them. This allows one agent to have access to thousands of skills without context overload.

---

## Before You Build: Preparation

This is the step most people skip, and the one with the biggest impact.

**1. Map the process**
Write out the ideal step-by-step process to get a good outcome. Don't prompt yet. Think first.

**2. Identify your reference files**
What additional context would help the agent do this better? Common ones:
- What your business does
- Your ICP (ideal customer profile)
- Voice and personality guidelines
- Writing frameworks or style guides
- Strategy documents (newsletter, YouTube, LinkedIn, etc.)

You don't need to have these yet. You can build them with Claude by asking it to interview you and generate the document. Once created, reuse them across multiple skills.

**3. Identify tools and connectors**
What software, MCPs, or APIs does the agent need to execute this task?

**4. Prepare output examples**
This has the biggest impact on performance. If you have examples of what "good" looks like, include them. If not, you can start without and add them as the skill produces approved outputs.

---

## Building the Skill: A Framework

Once you're prepared, prompt Claude to build the skill using this structure:

### 1. Name and trigger
Define the skill name and what should trigger it.
> *"This skill is called 'Infographic Generator' and should trigger whenever a user mentions wanting to create or generate an infographic."*

### 2. Goal or objective
A short statement of what the skill produces. You'll go deeper in the process steps.
> *"Creates quality infographics aligned to my brand style for LinkedIn and newsletters."*

### 3. Connectors and tools
List any MCPs, APIs, or software the skill needs. If there's a specific workflow in that tool, describe it here.

### 4. Step-by-step process
This is the most important part. For each step, define:
- **What to do**
- **When to involve the human**: Claude Code supports checkboxes, open fields, single select, etc. Think of this as UX design
- **What reference files or context to use** at this step
- **What output to expect**: where possible, ask for multiple variations to choose from rather than a single output

### 5. Rules
Predict what could go wrong and write it as a rule. This section grows over time as you catch edge cases.

Two things to always reinforce in rules:
- Make reference files **obligatory** steps, not optional: agents tend to skip them otherwise
- Reinforce the multiple-variations-with-human-in-the-loop pattern

### 6. Self-improvement instructions (optional but powerful)
Instruct the skill to update itself as it's used:
- When the user flags something to never do again → update the rules section
- When the user approves a final output → save it as a good example

---

## Iterating and Improving

Skills are never finished. The more you use them, the better they get. Use this rule of thumb when improving:

| Problem | Fix |
|--------|-----|
| Agent not following the process | Update `skill.md` |
| Agent missing context or information | Add or update a reference file |
| Agent doing something wrong consistently | Add a rule |
| Agent struggling with a tool or MCP | Guide it manually through the task, then ask it to create an MCP reference doc |

Keep `skill.md` clean and focused on the process. Additional information belongs in reference files.

---

## Sharing Skills

Once a skill is performing well:
- Ask Claude to export it as a zip file
- Share the zip directly, or deploy via GitHub
- The recipient imports it through their settings

For teams: skills can be bundled into **plugins**, packages that include multiple skills, commands, agent configurations, and connectors. Plugins can be versioned and distributed across departments.

---

## For Northforge

Skill files live in `/Skills/`. When a skill is created or updated:
1. The `.md` file is stored here as the source of truth
2. Both Mads and Johan copy it to their local `~/.claude/skills/`

See `Skills/_index.md` for the current skill list.

# Airlock Skills Library

Agent skills, components, and toolkits for the Airlock platform — and home of **Agent OTTO**, our PI-behavioral skill orchestrator.

---

## ⚡ Agent OTTO — Alpha

OTTO is a Claude skill that routes the right **persona, workflow chamber, and skill loadout** for any task using the Predictive Index behavioral framework. Instead of prompting blind, you tell OTTO what you're working on and it activates the right cognitive mode — Scholar for deep research, Maverick for autonomous coding, Analyzer for code review, Guardian for deployment protection.

**This repo is the alpha.** Try it, break it, tell us what you'd change.

---

## Try It — Two Ways

### 1. Interactive Demo (no install required)
Open the HTML file in your browser and use it as a visual prompt builder:

```
pi-index-explorer.html
```

- Pick a persona → load a workflow chamber → type your task → copy the OTTO prompt → paste into Claude Code
- Includes Auto-Suggest: describe what you're doing and OTTO recommends the best persona + skills
- 393 skills, 17 personas, 4 workflow chambers, custom loadout builder

### 2. Install the Skill (for Claude Code agents)
Drop the skill folder into your Claude Code skills directory so any agent can use OTTO natively:

```bash
# Clone the repo
git clone https://github.com/smartrickpicks/airlock-skills-library.git

# Copy the OTTO skill into your Claude skills directory
cp -r airlock-skills-library/skills/agent-otto ~/.claude/skills/
```

That's it. OTTO will now activate when you start a new task, ask "which skills should I use", or say "otto" in any Claude Code session.

---

## How OTTO Works

OTTO runs on three layers:

**1. Personas** — 17 PI behavioral profiles that shape how an agent thinks and communicates. Each has strengths to lean into, anti-patterns to avoid, and a curated skill loadout.

**2. Chambers** — Workflow-phase loadouts that match the right persona + skills to each stage of work:

| Chamber | Phase | Lead Persona | What it's for |
|---|---|---|---|
| 🔬 Discovery | Research · Explore | Scholar | Deep research before you build |
| ⚡ Build | Create · Code | Maverick | Autonomous coding + brainstorming |
| 🛡 Verify | Review · Test | Analyzer | Code review swarm before you push |
| 🚀 Ship | Deploy · Protect | Guardian | Merge protection + deployment |

**3. Skill Routing** — OTTO recommends specific skills from the catalog based on task keywords × persona alignment. If a skill isn't installed, it includes the install link.

When OTTO activates, the output reads like this:

```
## (persona: Scholar activated)

Operating as Scholar (Persistent archetype).
Chamber: Discovery | Skills: 18 loaded

You are now in deep research mode...
```

Paste that block into Claude Code and the agent operates in that mode.

---

## Skill File Structure

```
skills/agent-otto/
├── SKILL.md                    ← orchestrator instructions
└── references/
    ├── personas.md             ← full profiles for all 17 PI personas
    ├── chambers.md             ← Discovery → Build → Verify → Ship loadouts
    └── skill-catalog.md        ← top 10 skills per persona with install guidance
```

---

## The Broader Skills Library

Beyond OTTO, this repo is the Airlock platform's shared skills and component library:

- `skills/` — Agent skill definitions (SKILL.md format)
- `components/` — Official UI component library (React, Tailwind)
- `templates/` — Page layouts and UI templates
- `toolkits/` — CSS, JS, and React utilities
- `intake/` — Submission pipeline for new skills

Part of the [Airlock constellation](https://github.com/smartrickpicks/airlock-config). See the MCP registry for how skills wire into the broader platform.

---

## Status

Agent OTTO is **alpha**. The PI framework and skill routing are working. What's coming next:
- Richer skill descriptions pulled from live SKILL.md files
- Loadout sync across agents (no manual copy-paste)
- OTTO as a first-class Claude Code slash command (`/otto`)

# Agent OTTO — PI-Behavioral Skill Orchestrator

Agent OTTO uses the Predictive Index (PI) behavioral framework to route the right persona, skills, and workflow chamber for any task. OTTO doesn't just recommend skills — it reads their SKILL.md files and follows their instructions. The 17 personas are Claude's own operating modes, not external agents.

## What's Inside

### Core Skills

**agent-otto** — The orchestrator. Activates automatically when you start a task, plan work, or ask about personas/chambers. Routes 17 PI behavioral personas across 4 workflow chambers with real skill invocation and chat presence.

**otto-command-center** — Generates the interactive OTTO Command Center as a self-contained HTML dashboard. Includes persona explorer, chamber viewer, task router, playbook browser, and prompt optimizer.

### 81 Bundled Community Skills

OTTO ships with 81 curated community skills in `skills/community/` from three major skill packs:

- **Superpowers** (14 skills) — brainstorming, writing-plans, executing-plans, TDD, verification, parallel agents, subagent-driven development, and more
- **Everything Claude Code** (24 skills) — coding standards, frontend/backend patterns, deployment, testing, market research, continuous loops, and more
- **Claude Skills Community** (43 skills) — C-suite advisors, marketing, engineering, project management, product, testing, and more

When OTTO invokes a skill, it reads the bundled SKILL.md and follows its workflow, hard gates, and output format.

### Commands

| Command | What it does |
|---------|-------------|
| `/otto [task]` | Activate OTTO — route persona + chamber + skills and start working |
| `/otto-center` | Generate the OTTO Command Center HTML dashboard |
| `/otto-prompt [focus]` | Generate an optimized Claude Project system prompt |

### Reference Data

All reference files are in `skills/agent-otto/references/`:

- **personas.md** — 17 PI behavioral profiles with DECF drives, strengths, cautions, anti-patterns
- **chambers.md** — 4 workflow chambers with full skill loadouts
- **transitions.md** — Chamber transition rules, quality gates, announcement templates
- **playbooks.md** — 5 canonical playbook templates for common workflows
- **skill-catalog.md** — Skill recommendations per persona
- **default-skills.json** — Full 99-skill mapping to personas and chambers
- **skill-invocation.md** — How OTTO reads and follows SKILL.md files
- **system-prompt-template.md** — Claude Project system prompt template

## How It Works

1. **Describe your task** — tell OTTO what you need to do
2. **OTTO routes** — selects persona (e.g., Maverick for coding, Analyzer for review) and chamber
3. **Chat presence** — every response shows `(Persona Emoji · Chamber)` so you always know the active mode
4. **Skill invocation** — OTTO reads the relevant SKILL.md files and follows their workflows
5. **Hard gates** — brainstorming blocks Build, TDD blocks untested code, verification blocks completion claims
6. **Phase transitions** — OTTO announces persona/chamber changes with reasons

## The 17 Personas

| Category | Personas |
|----------|----------|
| Analytical | Scholar 🔬, Strategist 🧭, Analyzer 🔍, Venturer 🚀, Individualist 🎯 |
| Social | Captain 👑, Maverick ⚡, Persuader 💎, Promoter 📣, Collaborator 🤝, Altruist 💚 |
| Stabilizing | Guardian 🛡, Operator ⚙️, Adapter 🔄, Artisan 🎨 |
| Persistent | Controller 📋 |

## The 4 Chambers

```
Discovery 🔬 → Build ⚡ → Verify 🛡 → Ship 🚀
  Scholar      Maverick    Analyzer    Guardian
```

## Hard Gates

| Gate | Skill | Rule |
|------|-------|------|
| Design | brainstorming | No implementation without design approval |
| Test | test-driven-development | No production code without failing test |
| Evidence | verification-before-completion | No "done" claims without verification proof |

## Additional Skills

Beyond the 81 bundled skills, OTTO also works with:
- **Official Anthropic skills** (docx, pdf, pptx, xlsx, canvas-design, etc.) — built into Claude
- **External community skills** — install separately from GitHub (Loki Mode, iOS Simulator, etc.)

## About

Agent OTTO is built by Airlock. Learn more at [airlock.so](https://airlock.so).

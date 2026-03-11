---
description: Generate the OTTO Command Center — interactive dashboard with all personas, chambers, skills, and routing
allowed-tools: Read, Write, Bash
---

Generate the Agent OTTO Command Center as a self-contained HTML file. This is the unified interactive dashboard that consolidates all OTTO knowledge into one artifact.

Follow these steps:

1. **Read all reference data** from ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/:
   - personas.md — all 17 PI profiles with DECF drives
   - chambers.md — all 4 chambers with skill loadouts
   - transitions.md — chamber-to-chamber transition rules
   - skill-catalog.md — skill recommendations per persona
   - playbooks.md — canonical playbook templates
   - default-skills.json — the full 99-skill mapping to personas and chambers
   - skill-invocation.md — how OTTO reads and follows SKILL.md files

2. **Read the Command Center template** at ${CLAUDE_PLUGIN_ROOT}/skills/otto-command-center/references/template-spec.md for the required structure and theme.

3. **Generate the HTML** with these required sections (as tabs/panels):

   **Overview** — Stats dashboard: 17 personas, 4 chambers, 99 mapped skills (81 bundled), 3 hard gates. Full persona × behavioral drives matrix table. Chat presence format explanation.

   **Chambers** — Visual flow: Discovery 🔬 → Build ⚡ → Verify 🛡 → Ship 🚀. Click any chamber to see lead persona, supporting cast, all skill groups with individual skills listed, and hard gates that apply to each transition. Include the chamber-to-chamber transition suggestions showing what persona leads next.

   **Personas** — Card grid of all 17 personas (use emojis: Scholar 🔬, Strategist 🧭, Analyzer 🔍, Venturer 🚀, Individualist 🎯, Captain 👑, Maverick ⚡, Persuader 💎, Promoter 📣, Collaborator 🤝, Altruist 💚, Guardian 🛡, Operator ⚙️, Adapter 🔄, Artisan 🎨, Controller 📋) color-coded by category (Analytical/Social/Stabilizing/Persistent). Click to expand full profile with: animated PI drive bar charts (D/E/C/F), strengths, cautions, anti-patterns, primary + supporting skills from default-skills.json, and workspace preferences.

   **Skill Browser** — Browse all 99 skills from default-skills.json organized by chamber and category. Each skill shows: name, source pack, assigned personas, chamber, trigger description. Filter by chamber, persona, or source. Highlight the 3 hard gate skills prominently.

   **Task Router** — Text input where user describes a task. OTTO routes it to the best persona + chamber + skills with a "why this routing" explanation. Show which community SKILL.md files would be invoked. Include example task buttons.

   **Playbooks** — Browse canonical playbook templates. Each shows the full chamber flow with persona per phase, skill chains, quality gates, and transition points.

   **Wiki** — Skill invocation protocol (how OTTO reads SKILL.md files), chat presence format, hard gates explanation, skill taxonomy (5 types: atomic/chain/loop/orchestrator/utility), execution patterns, and installation instructions:
   ```
   /plugin marketplace add smartrickpicks/airlock-skills-library
   /plugin install agent-otto-alpha@airlock-skills
   ```

   **Prompt Optimizer** — Select a persona + chamber combination and generate an optimized Claude Project system prompt. Include copy-to-clipboard. The system prompt should use the v2 format (self-contained, no external agents, chat presence, hard gates).

4. **Apply the OTTO theme**:
   - Dark background (#0a0a0f), purple accent (#6c5ce7), JetBrains Mono + Inter fonts
   - Chamber colors: Discovery (green #00b894), Build (gold #fdcb6e), Verify (coral #e17055), Ship (blue #0984e3)
   - Animated grid background, smooth transitions, glow effects on active states
   - Fully responsive with mobile support

5. **Save the file** to the user's workspace folder as `otto-command-center.html`.

The output must be a single, self-contained HTML file with no external dependencies except Google Fonts. All data, styles, and scripts inline. All 99 skills from default-skills.json must be included as inline JS data.

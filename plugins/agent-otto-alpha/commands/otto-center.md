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
   - skill-catalog.md — full skill catalog
   - playbooks.md — canonical playbook templates

2. **Read the Command Center template** at ${CLAUDE_PLUGIN_ROOT}/skills/otto-command-center/references/template-spec.md for the required structure and theme.

3. **Generate the HTML** with these required sections (as tabs/panels):

   **Overview** — Stats dashboard: persona count, chamber count, skill count, skill tags. Full persona × behavioral drives matrix table.

   **Chambers** — Visual flow: Discovery → Build → Verify → Ship. Click any chamber to see lead persona, supporting cast, all skill groups with individual skills listed. Include the chamber-to-chamber transition suggestions showing what persona leads next.

   **Personas** — Card grid of all 17 personas color-coded by category (Analytical/Social/Stabilizing/Persistent). Click to expand full profile with: animated PI drive bar charts (D/E/C/F), strengths, cautions, anti-patterns, top 10 skills, workspace preferences (cognitive_mode, information_density, interface_structure), and MAGS archetype mapping.

   **Task Router** — Text input where user describes a task. OTTO routes it to the best persona + chamber + skills with a "why this routing" explanation. Include example task buttons.

   **Playbooks** — Browse canonical playbook templates. Each shows the full chamber flow with persona per phase, skill chains, quality gates, and transition points.

   **Wiki** — Skill taxonomy (5 types: atomic/chain/loop/orchestrator/utility), skill chaining model, execution patterns, and the relay agent architecture overview.

   **Prompt Optimizer** — Select a persona + chamber combination and generate an optimized Claude Project system prompt snippet. Include copy-to-clipboard functionality.

4. **Apply the OTTO theme**:
   - Dark background (#0a0a0f), purple accent (#6c5ce7), JetBrains Mono + Inter fonts
   - Chamber colors: Discovery (green #00b894), Build (gold #fdcb6e), Verify (coral #e17055), Ship (blue #0984e3)
   - Animated grid background, smooth transitions, glow effects on active states
   - Fully responsive with mobile support

5. **Save the file** to the user's workspace folder as `otto-command-center.html`.

The output must be a single, self-contained HTML file with no external dependencies except Google Fonts. All data, styles, and scripts inline.

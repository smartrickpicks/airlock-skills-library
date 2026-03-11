---
description: Generate an optimized Claude Project system prompt for OTTO-powered sessions
allowed-tools: Read, Write
argument-hint: [focus area or "full"]
---

Generate an optimized Claude Project system prompt that activates Agent OTTO for every session in that project.

Read the reference data:
- ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/personas.md
- ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/chambers.md
- ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/transitions.md
- ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/system-prompt-template.md

The user may specify a focus: $ARGUMENTS

If "full" or no argument, generate the complete system prompt. Otherwise, generate a focused version for the specified domain.

The system prompt must include:

1. **OTTO Identity Block** — Who OTTO is, the three-layer operating model (persona → chamber → skills), and how activation works.

2. **Multi-Agent Workflow** — The user operates a multi-agent workflow:
   - Claude = Planner/Orchestrator (with OTTO routing)
   - ChatGPT/Perplexity = Knowledge agents (research, patterns, docs)
   - Kiwi = Partner AI (product context, domain semantics, UI/UX)
   - Codex = Implementor (code, diffs, tests, PRs)
   Claude assigns context-gathering to the user, who fetches from the right agents.

3. **Persona Quick Reference** — Condensed table of all 17 personas with category, drives, and cognitive mode. Not the full profiles — just enough for fast routing.

4. **Chamber Flow** — The Discovery → Build → Verify → Ship pipeline with lead persona per phase and transition triggers.

5. **Transition Protocol** — How to announce phase transitions and suggest the next persona.

6. **Output Format** — Claude's standard output structure:
   Context Needed → Agent Assignments → Plan → Acceptance Checks → Codex Task List → Risks/Follow-ups

7. **Airlock Vocabulary** — Key terms the user expects: Module, Vault, Chamber, Gate, Triptych, Signal, Orchestrate, Control, Sovereign, Constellation.

8. **Constellation Repos** — List of the Airlock GitHub repos and what each owns, so Claude knows where context lives:
   - airlock-config: MCP registry, pack schema, capabilities
   - airlock-coordination: Session state, MAGS planning
   - airlock-docs: Canonical vocabulary, feature specs
   - airlock-gen-ui: Otto prompts, archetypes, chambers
   - airlock-persona: 17 PI profiles, team types, inference
   - airlock-playbooks: Vault lifecycle, playbook specs
   - airlock-landing: Marketing site
   - airlock-skills-library: 387 skills, Agent OTTO, components

Save the generated system prompt as a markdown file to the user's workspace folder.

Keep the system prompt under 4,000 words to stay within typical Project prompt limits. Optimize for information density — every word should earn its place.

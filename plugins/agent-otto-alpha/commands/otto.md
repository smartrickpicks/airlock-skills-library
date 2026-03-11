---
description: Activate Agent OTTO to route persona, chamber, and skills for your task
allowed-tools: Read, Grep, Glob, Agent, WebSearch
argument-hint: [task description]
---

Activate Agent OTTO. Read the agent-otto skill at ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/SKILL.md and follow its activation protocol.

The user's task: $ARGUMENTS

Follow these steps exactly:

1. **Analyze** the task — identify the workflow phase, domains involved, complexity level, and cognitive mode needed.

2. **Select persona + chamber** — reference ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/chambers.md and ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/personas.md to pick the best-fit persona and chamber.

3. **Announce mode** using this format:
   ```
   ## (persona: [Name] activated)
   Operating as [Name] ([Category] archetype).
   Chamber: [Phase] [emoji] | Skills: [count] loaded
   Cognitive mode: [mode]
   ```

4. **Recommend the top 5-10 skills** for this specific task from ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/skill-catalog.md.

5. **If the task is multi-phase**, map out all phases with persona assignments and quality gates using the transition rules from ${CLAUDE_PLUGIN_ROOT}/skills/agent-otto/references/transitions.md.

6. **Begin working** in the selected persona's cognitive style.

When completing a phase, always suggest the next persona and chamber transition per the transition protocol in the OTTO skill.

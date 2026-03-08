# airlock-skills-library

Agent skills and component library for the Airlock platform.

## Read First
Read AGENTS.md for your role and boundaries.

## MCP Connections
- Reads from: airlock-docs (vocabulary, specs)
- Provides to: all repos (read-only), airlock-gen-ui (component patterns)

## Rules
- Skills describe WITH-WHAT (docs describe WHAT, playbooks describe HOW)
- All components use Tailwind tokens — never raw color values
- Follow atomic design: token / atom / molecule / organism / template / view
- One default export per component file, PascalCase names
- Skills follow the SKILL.md format with clear triggers and instructions

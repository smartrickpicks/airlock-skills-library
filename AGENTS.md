# airlock-skills-library — Agent Entry Point

## What This Repo Owns
Agent skills, official component library, UI templates, moodboard, CSS/JS/React toolkits, and template intake pipeline.

## MCP Mode
Read-only server. All repos can read skills. Only agents in this repo write.

## Directory Structure
- `skills/` — SKILL.md files for agent capabilities
- `components/` — Official UI component library (React, Tailwind)
- `templates/` — UI templates and page layouts
- `moodboard/` — Design references and visual direction
- `toolkits/` — CSS, JS, and React utility toolkits
- `intake/` — Template intake pipeline for new submissions

## Pack Format
This repo is structured as a platform-defaults pack. Skills, components, and templates are the atomic units.

## Coordination
- Register your session in airlock-coordination before starting work
- New skills require review — follow the intake pipeline
- Component changes must maintain backward compatibility

## Vocabulary
See airlock-docs for the canonical glossary. Key terms: Pack, Controller, Maverick, Builder.

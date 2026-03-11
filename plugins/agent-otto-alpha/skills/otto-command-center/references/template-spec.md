# OTTO Command Center — Template Specification

## Design System

### Colors
```
--bg: #0a0a0f
--surface: #12121a
--surface2: #1a1a26
--surface3: #22223a
--border: #2a2a40
--text: #e8e8f0
--text-dim: #8888aa
--accent: #6c5ce7
--accent2: #a29bfe
--discovery: #00b894
--build: #fdcb6e
--verify: #e17055
--ship: #0984e3
--glow: rgba(108, 92, 231, 0.3)
```

### Category Colors
```
Analytical: #e17055 (coral)
Social: #fdcb6e (gold)
Stabilizing: #00b894 (green)
Persistent: #0984e3 (blue)
```

### Typography
- Headers: 'Inter', system-ui, sans-serif — weight 700-900
- Body: 'Inter' — weight 400-500
- Code/mono: 'JetBrains Mono', monospace — weight 300-600
- Import: https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700;800;900&display=swap

### Effects
- Grid background: linear-gradient lines at 60px intervals, rgba(108,92,231,0.03)
- Active glow: box-shadow 0 0 30px var(--glow) on active states
- Card hover: translateY(-3px) with border-color change
- Panel transitions: fadeIn 0.4s ease (opacity 0→1, translateY 10px→0)
- Drive bars: transition width 0.6s cubic-bezier(0.25, 0.8, 0.25, 1)

### Layout
- Max width: 1400px centered
- Card border-radius: 14-20px
- Responsive breakpoint: 768px
- Nav tabs: pill-style with active indicator

## Required Sections (Tabs)

### 1. Overview
- Stat cards grid: Personas (17), Chambers (4), Skills (393), Skill Tags (32), PI Drives (4)
- Full persona matrix table: Name, Category (color-coded tag), D/E/C/F (high/mid/low indicators), Cognitive Mode

### 2. Chambers
- Horizontal flow: 4 clickable chamber nodes with icons (🔬⚡🛡🚀) connected by arrows
- Click to expand: lead persona (highlighted), supporting cast (tags), skill groups with individual skills
- **TRANSITION CARD**: At bottom of each chamber detail, show the suggested next chamber with lead persona change and quality gate

### 3. Personas
- Grid of 17 cards, color-coded by category
- Click to expand: bio, animated DECF drive bars, strengths, cautions, anti-patterns, top 10 skills, workspace preferences, MAGS archetype, autonomy ceiling

### 4. Task Router
- Large text input with placeholder
- Example task buttons below input
- Result panel: persona name (large), chamber tag (colored), archetype tag, cognitive mode tag
- "Why this routing" explanation
- Recommended skills grid
- Chamber skill groups

### 5. Playbooks
- List of 7 canonical playbooks with trigger phrases
- Click to expand: full phase flow with persona per step, skill chains, quality gates, transition points
- Visual step indicator (numbered circles with connecting lines, color-coded by chamber)

### 6. Wiki
- Skill Taxonomy: 5 types (atomic/chain/loop/orchestrator/utility) as colored cards
- Skill Chaining Model: parent-child diagram
- Execution Patterns: table showing complexity → pattern mapping
- Architecture: hub-and-spoke agent coordination overview

### 7. Prompt Optimizer
- Persona selector (grid of 17 buttons)
- Chamber selector (4 buttons)
- Focus area selector (full / research / coding / review / deploy)
- Generated prompt preview (monospace, dark background)
- Copy button (changes to "Copied!" on click)

## Data Structure

All persona and chamber data should be embedded as JavaScript objects. The routing logic uses keyword matching against a rules array. Playbook data is embedded as structured objects with phase arrays.

## Single File Requirement

Everything (HTML, CSS, JS) must be in one file. No external dependencies except Google Fonts. No localStorage or sessionStorage.

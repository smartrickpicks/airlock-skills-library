# OTTO Canonical Playbook Templates

When OTTO detects a task that matches one of these playbook patterns, it should load the entire chain — persona per phase, execution pattern, skill list, and acceptance criteria.

## How Playbooks Work

A playbook is a pre-defined sequence of chamber transitions with skill chains for each phase. OTTO matches the user's task description against playbook triggers and loads the best match.

**Structure:** Each playbook specifies:
- **Trigger patterns** — keywords/phrases that activate this playbook
- **Chamber flow** — which chambers in which order
- **Persona per phase** — who leads each phase
- **Execution pattern** — linear, fan-out, or DAG
- **Skill chain** — ordered list of skills per phase with types
- **Human checkpoints** — where user approval is required
- **Acceptance criteria** — definition of done

---

## Playbook: Landing Page / Marketing Site

**Triggers:** "landing page", "marketing site", "homepage", "website redesign", "marketing page", "splash page"

**Complexity:** Medium (4-10 files)
**Execution Pattern:** Fan-Out / Fan-In (parallel agents for implementation)
**Estimated Phases:** 8 steps across 4 chambers

### Phase Flow

```
Discovery (Scholar) → Discovery (Strategist) → Build (Maverick) → Build (Maverick+Venturer)
→ Verify (Analyzer) → Verify (Specialist) → Ship (Guardian) → Ship (Adapter)
```

### Step-by-Step

| Step | Chamber | Persona | Action | Skills | Type |
|------|---------|---------|--------|--------|------|
| 1 | Discovery | Scholar | Intent capture + research | Brainstorming, Exa Search, Context7, Tech Stack Evaluator | utility, atomic |
| 2 | Discovery | Strategist | Architecture + design doc | UI/UX Pro Max, Senior Architect, Frontend Design, Figma MCP | chain, atomic |
| 3 | Build | Maverick | Implementation plan | Writing Plans, SaaS Scaffolder | chain, atomic |
| 4 | Build | Maverick+Venturer | Autonomous coding (parallel) | Subagent-Driven Dev, Parallel Agents, Frontend Design, Web Artifacts Builder, Copywriting | loop, orchestrator, atomic |
| 5 | Verify | Analyzer | Review swarm | Security Review, Performance Profiler, Coding Standards, Senior QA, E2E Testing, Playwright MCP | atomic, loop |
| 6 | Verify | Specialist | Fix + re-test | TDD Guide, De-Sloppify, Finishing a Branch | chain, loop |
| 7 | Ship | Guardian | Deploy + monitor | CI/CD Pipeline Builder, Vercel MCP, Cloudflare MCP, Checkly MCP, Runbook Generator | chain, atomic |
| 8 | Ship | Adapter | Handoff + report | Board Deck Builder, Quality Documentation Manager | atomic |

### Human Checkpoints
- After step 2: Design doc approval (before any code)
- After step 5: Review report (before fixes)
- After step 7: Deploy confirmation

### Acceptance Criteria
- [ ] Design doc reviewed and approved by user
- [ ] All sections render correctly across desktop/tablet/mobile
- [ ] Page load time < 3s (Performance Profiler)
- [ ] No critical security findings (Security Review)
- [ ] All interactive elements accessible (keyboard + screen reader)
- [ ] Content matches design doc specifications
- [ ] Deployed and monitoring active

---

## Playbook: REST API with Auth

**Triggers:** "build api", "rest api", "api endpoint", "backend service", "api with auth", "authentication endpoint"

**Complexity:** Medium-Large (5-15 files)
**Execution Pattern:** Fan-Out / Fan-In
**Estimated Phases:** 7 steps across 4 chambers

### Phase Flow

```
Discovery (Scholar) → Build (Maverick) → Build (Venturer) → Verify (Analyzer+Specialist)
→ Verify (Controller) → Ship (Operator) → Ship (Guardian)
```

### Step-by-Step

| Step | Chamber | Persona | Action | Skills | Type |
|------|---------|---------|--------|--------|------|
| 1 | Discovery | Scholar | Research auth patterns, evaluate JWT vs session, check existing codebase | Brainstorming, Context7, Perplexity MCP, API Design Patterns | utility, atomic |
| 2 | Build | Maverick | Implementation plan + scaffold | Writing Plans, SaaS Scaffolder | chain, atomic |
| 3 | Build | Venturer | Implement endpoints + auth middleware + migrations | Subagent-Driven Dev, Supabase MCP, Docker MCP, PostgreSQL MCP | loop, atomic |
| 4 | Verify | Analyzer | Security audit + code review | Security Review, Performance Profiler, Database Designer, OWASP ZAP MCP | atomic |
| 5 | Verify | Specialist | Test coverage + API validation | TDD Guide, E2E Testing Patterns, Senior QA, Playwright MCP | chain, atomic |
| 6 | Ship | Operator | Infrastructure + CI/CD | CI/CD Pipeline Builder, Docker MCP, AWS MCP, GitHub Actions MCP | chain, atomic |
| 7 | Ship | Guardian | Security hardening + deploy | Snyk MCP, Vault MCP, Checkly MCP, Risk Management | atomic |

### Human Checkpoints
- After step 1: Auth pattern decision
- After step 4: Security audit results
- After step 6: Infrastructure review before deploy

### Acceptance Criteria
- [ ] Auth flow works end-to-end (register, login, protected routes)
- [ ] All endpoints have input validation
- [ ] Rate limiting configured
- [ ] No critical/high security findings
- [ ] Test coverage > 80%
- [ ] API docs generated (OpenAPI/Swagger)
- [ ] Monitoring + alerting active

---

## Playbook: Code Review / PR Audit

**Triggers:** "review this code", "audit pr", "code review", "check this pr", "review before merge", "is this safe to merge"

**Complexity:** Low-Medium (review only, no new code)
**Execution Pattern:** Linear Pipeline
**Estimated Phases:** 4 steps, primarily Verify chamber

### Phase Flow

```
Discovery (Scholar) → Verify (Analyzer) → Verify (Controller) → Verify (Specialist)
```

### Step-by-Step

| Step | Chamber | Persona | Action | Skills | Type |
|------|---------|---------|--------|--------|------|
| 1 | Discovery | Scholar | Understand scope — read PR, check files changed, understand intent | Context7, GitHub MCP | utility, atomic |
| 2 | Verify | Analyzer | Review swarm — security, performance, data, architecture | Security Review, Performance Profiler, Database Designer, RAG Architect, Sentry MCP | atomic |
| 3 | Verify | Controller | Process compliance — standards, CI, release gates | QMS Audit Expert, Coding Standards, CI/CD Pipeline Builder, Release Manager | atomic |
| 4 | Verify | Specialist | Correctness — tests, API contracts, edge cases | Senior QA, TDD Guide, API Design Patterns, E2E Testing Patterns | atomic, chain |

### Human Checkpoints
- After step 4: Review summary with pass/fail verdicts

### Acceptance Criteria
- [ ] Every changed file reviewed
- [ ] Security: no credentials, no injection vectors, no auth bypasses
- [ ] Performance: no N+1 queries, no unbounded loops, no memory leaks
- [ ] Standards: naming conventions, file structure, documentation
- [ ] Tests: new code has tests, existing tests still pass

---

## Playbook: Research / Deep Dive

**Triggers:** "research", "compare", "evaluate options", "what are the options", "help me understand", "deep dive into", "analyze the trade-offs"

**Complexity:** Low (research only, no implementation)
**Execution Pattern:** Linear Pipeline
**Estimated Phases:** 4 steps, primarily Discovery chamber

### Phase Flow

```
Discovery (Scholar) → Discovery (Strategist) → Discovery (Analyzer) → Report
```

### Step-by-Step

| Step | Chamber | Persona | Action | Skills | Type |
|------|---------|---------|--------|--------|------|
| 1 | Discovery | Scholar | Deep research — gather sources, read docs, find examples | Exa Search MCP, Perplexity MCP, Tavily Search MCP, Context7 MCP, HuggingFace MCP | atomic |
| 2 | Discovery | Strategist | Systems analysis — architecture implications, trade-offs, alignment with goals | Senior Architect, Technology Stack Evaluator, Strategic Alignment Engine | atomic |
| 3 | Discovery | Analyzer | Data validation — benchmark data, performance numbers, risk assessment | Senior Data Scientist, Performance Profiler, Risk Management Specialist | atomic |
| 4 | Report | Scholar | Synthesis — structured comparison, recommendation with evidence | Board Deck Builder, Quality Documentation Manager | atomic |

### Human Checkpoints
- After step 1: Confirm research scope is correct
- After step 4: Review findings and recommendation

### Acceptance Criteria
- [ ] At least 3 options compared with pros/cons
- [ ] Performance benchmarks included (where applicable)
- [ ] Risk assessment for each option
- [ ] Clear recommendation with reasoning
- [ ] Sources cited

---

## Playbook: Dashboard / Data UI

**Triggers:** "build dashboard", "data visualization", "analytics page", "admin panel", "reporting UI", "metrics dashboard"

**Complexity:** Medium-Large (8-15 files)
**Execution Pattern:** Fan-Out / Fan-In
**Estimated Phases:** 7 steps across 4 chambers

### Phase Flow

```
Discovery (Scholar+Strategist) → Build (Maverick) → Build (Maverick+Venturer)
→ Verify (Analyzer) → Verify (Specialist) → Ship (Guardian+Operator)
```

### Step-by-Step

| Step | Chamber | Persona | Action | Skills | Type |
|------|---------|---------|--------|--------|------|
| 1 | Discovery | Scholar | Research data sources, understand metrics, map user workflows | Brainstorming, Senior Data Scientist, BigQuery/Snowflake MCP, Context7 | utility, atomic |
| 2 | Discovery | Strategist | Design data architecture + UI layout | Senior Architect, UI/UX Pro Max, PostHog MCP, Mixpanel MCP | atomic, chain |
| 3 | Build | Maverick | Implementation plan | Writing Plans | chain |
| 4 | Build | Maverick+Venturer | Parallel build: charts/viz, data layer, layout/navigation, filters/controls | Subagent-Driven Dev, Parallel Agents, Frontend Design, Web Artifacts Builder, Supabase MCP | loop, orchestrator, atomic |
| 5 | Verify | Analyzer | Data accuracy audit + performance review | Senior Data Scientist, Performance Profiler, Security Review, Database Designer | atomic |
| 6 | Verify | Specialist | UX review + cross-browser testing | Senior QA, Playwright MCP, BrowserStack MCP, E2E Testing Patterns | atomic |
| 7 | Ship | Guardian+Operator | Deploy + monitoring dashboards | CI/CD Pipeline Builder, Datadog MCP, Grafana MCP, Checkly MCP | chain, atomic |

### Human Checkpoints
- After step 2: Design approval (layout, metrics selection, chart types)
- After step 5: Data accuracy validation
- After step 7: Deploy confirmation

### Acceptance Criteria
- [ ] All specified metrics display correctly
- [ ] Filters work and update charts in real-time
- [ ] Data matches source of truth (validated against raw queries)
- [ ] Dashboard loads in < 2s
- [ ] Responsive across desktop/tablet
- [ ] No sensitive data exposed in client-side code

---

## Execution Pattern Selection Guide

OTTO auto-selects the execution pattern based on detected complexity:

| Signal | Files | Domains | Pattern | Skill |
|--------|-------|---------|---------|-------|
| Simple | 1-3 | 1 | Linear Pipeline | executing-plans (batch of 3) |
| Medium | 4-10 | 2+ | Fan-Out / Fan-In | dispatching-parallel-agents |
| Complex | 10+ | 3+ with deps | Ralphinho DAG | ralphinho-rfc-pipeline |
| Continuous | Any | Multi-day | PR Loop | continuous-claude-pr-loop |
| Review only | N/A | N/A | Linear | Single-pass swarm |

## Utility Skills (Global — Available in All Playbooks)

These skills are callable at any point in any playbook:

| Skill | Type | When Called |
|-------|------|------------|
| Brainstorming | utility | Before any implementation — always start here |
| Using Git Worktrees | utility | Before any parallel work |
| Context7 MCP | utility | When understanding existing codebase |
| Exa Search MCP | utility | When needing external research |
| Tavily Search MCP | utility | Fact-checking, web research |
| GitHub MCP | utility | Repo operations, PR management |
| Obsidian MCP | utility | Knowledge management, note retrieval |

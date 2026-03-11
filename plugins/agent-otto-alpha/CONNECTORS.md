# Connectors

## How tool references work

Plugin files use `~~category` as a placeholder for whatever tool the user
connects in that category. Agent OTTO is designed to be platform-agnostic —
it describes workflows in terms of capabilities, not specific products.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
|----------|-------------|-----------------|---------------|
| Source control | `~~source control` | GitHub | GitLab, Bitbucket |
| Project tracker | `~~project tracker` | Linear | Asana, Jira, Monday |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Design | `~~design tool` | Figma | Canva, Adobe XD |
| Cloud infra | `~~cloud provider` | — | AWS, GCP, Azure, Cloudflare |
| Database | `~~database` | — | Supabase, PostgreSQL, Snowflake |
| CI/CD | `~~ci/cd` | GitHub Actions | CircleCI, GitLab CI |
| Monitoring | `~~monitoring` | — | Datadog, Grafana, Sentry |
| Search | `~~search engine` | — | Exa, Tavily, Perplexity |
| Docs | `~~documentation` | — | Notion, Obsidian, Confluence |

## Future MCP Endpoints

When the Airlock constellation repos are deployed as MCP servers, the following
endpoints will be available:

| Server | Provides | Status |
|--------|----------|--------|
| airlock-config | Pack schema, capabilities, MCP registry | Planned |
| airlock-docs | Canonical vocabulary, feature specs | Planned |
| airlock-persona | PI profiles, team types, inference rules | Planned |
| airlock-skills-library | Skill catalog, component patterns | Planned |

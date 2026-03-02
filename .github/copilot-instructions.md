# [Project Name] — GitHub Copilot Configuration

> For the full team workflow guide, see [docs/team-copilot-guide.md](../docs/team-copilot-guide.md)

> use `/generateInstructions` to generate instructions for your project in copilot chat.

## What This Project Is
[One sentence: what does this project do?]

Stack: [e.g., Node.js + Express + PostgreSQL + Redis]

## Key Documentation
- **[Team Copilot Guide](../docs/team-copilot-guide.md)**: How we use Copilot as a team — start here
- **[Docs Architecture](../docs/docs-architecture.md)**: Where every doc lives

## Our Issue Workflow
Every work item is an **Issue** going through 5 phases:
`/discuss` → `/research` → `/plan` → `/execute` → `/verify`

## Where to Find Things
- **Flow docs**: `docs/flows/[flow-name]-flow.md`
- **API docs**: `docs/apis/[domain]/[endpoint].api.md`
- **Issue docs**: `docs/issues/ISSUE-XXX-name.md`
- **Templates**: `docs/templates/`

## For AI Agents
1. Read the API doc from `docs/apis/` before touching endpoint code
2. Read the flow doc from `docs/flows/` for business context
3. Read the Issue doc from `docs/issues/` for what's planned in this session
4. After code changes affecting an API → run `/update-api-doc`
5. After finishing work → update Issue doc progress tracker

## Conventions (fill in per project)
- [Your project-specific coding rules go here]

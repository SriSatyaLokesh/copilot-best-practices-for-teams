# docs/ — Project Documentation Folder

This `docs/` folder holds **all living documentation for your project**. It is split into two purposes:

1. **Templates** — copy-paste starters for every doc type (fill in per project)
2. **Your project docs** — the filled-in versions that Copilot reads during sessions

> **Copilot reads these files during sessions.** The more accurate and complete your docs are, the better Copilot understands your project — the right field names, the right patterns, the right constraints.

---

## Folder Map

```
docs/
├── README.md                     ← this file
├── templates/                    ← copy-paste starters (don't edit directly — copy first)
├── external-apis/                ← one folder per external API you call
├── issues/                       ← one doc per work item / feature / bug fix
├── apis/                         ← one doc per internal API endpoint
├── flows/                        ← one doc per user journey / business flow
├── decisions/                    ← architecture decision records (ADRs)
└── team-notes/                   ← personal scratch space, one folder per developer
```

---

## `templates/` — What Each Template Is For

All templates live in `docs/templates/`. **Never edit a template directly.** Copy it to the right folder and fill in the copy.

### `issue-template.md` → `docs/issues/`

**Copy to**: `docs/issues/[issue-id]-[short-name].md`

**What to fill in**:
- Front matter: `issue-id`, `title`, `branch`, initial `status: discuss`
- **Phase 1 (Discuss)**: Requirements, acceptance criteria, constraints — filled by the Discuss agent
- **Phase 2 (Research)**: Files to change, existing patterns found — filled by Research agent
- **Phase 3 (Plan)**: Architecture decisions, ordered task list — filled by Plan agent
- **Phase 4 (Execute)**: Progress checkboxes — updated by TDD agent during coding
- **Phase 5 (Verify)**: Verification report — filled by Verify agent

**Why it matters**: Every Copilot session for this issue reads this file. It is the single source of truth for what was agreed, what was found, what the plan says, and what is done. Without it, context is lost between sessions.

**Example**: `docs/issues/ISSUE-042-login-rate-limiting.md`

---

### `external-api-doc-template.md` → `docs/external-apis/[api-name]/README.md`

**Copy to**: `docs/external-apis/[api-name]/README.md`

**What to fill in**:
- Base URL (production + staging)
- Authentication method (API key, OAuth 2.0, etc.) with exact header names
- Rate limits (requests per second/minute, retry-after behavior)
- Known gotchas (date formats, pagination style, null vs missing fields)
- Links to official docs

**Why it matters**: This is the first thing Copilot reads when you use `/add-new-api`. It prevents Copilot from guessing wrong auth headers or hitting rate limit walls.

**Example**: `docs/external-apis/dynamics/README.md`

---

### `api-doc-template.md` → `docs/external-apis/[api-name]/[entity].api.md`

**Copy to**: `docs/external-apis/[api-name]/[entity].api.md`

**What to fill in**:
- The endpoint URL and HTTP method
- Request params/body with exact field names (as the API actually expects them)
- Response schema with **exact field names** from the real API response
- The field mapping table: external field name → your internal name + type
- Example request and response (copy from Postman/real API call)
- Status codes and what each means

**Why it matters**: The field mapping table is the most important thing in this whole system. It is what stops Copilot from guessing field names like `email` when the API actually uses `emailaddress1`. Fill this in from real API responses — not the docs, the actual response.

**Example**: `docs/external-apis/dynamics/accounts.api.md`

---

### `api-wrapper-doc-template.md` → `docs/apis/wrappers/[entity]-wrapper.md`

**Copy to**: `docs/apis/wrappers/[wrapper-name].md`

**What to fill in**:
- Which external API this wrapper covers
- Each method exposed by the wrapper: name, parameters, return type
- Error types it throws (so callers know what to catch)
- Token refresh behavior (if applicable)

**Why it matters**: Service layer developers read this to understand what the wrapper provides, without diving into the wrapper implementation.

---

### `flow-doc-template.md` → `docs/flows/`

**Copy to**: `docs/flows/[flow-name].md`

**What to fill in**:
- The user journey in numbered steps (start → end)
- Which system components are involved at each step
- Decision points (what happens if auth fails, what happens at step 3 if the user is inactive)
- Links to relevant Issue docs or API docs

**Why it matters**: When a developer works on a feature that touches multiple system parts, Copilot reads the flow doc first to understand the full context before planning.

**Example**: `docs/flows/auth-flow.md`, `docs/flows/order-checkout-flow.md`

---

### `copilot-instructions-template.md` → `.github/copilot-instructions.md`

**Copy to**: `.github/copilot-instructions.md` (replace the existing file)

**What to fill in**:
- Project name
- One-sentence description of what the project does
- Tech stack (exact versions if important)
- Links to your key docs (PROJECT.md, external APIs folder, active issues folder)
- Any conventions Copilot must always follow (filled via `/init` command)

**Why it matters**: This file is loaded every single Copilot session, for every file. Keep it under 50 lines — it is context budget, not a novel.

---

### `architecture-template.md` → `docs/ARCHITECTURE.md`

**Copy to**: `docs/ARCHITECTURE.md` (or rename the existing stub)

**What to fill in**:
- High-level system diagram (Mermaid is supported in VS Code previews)
- Key architectural decisions (why PostgreSQL over MongoDB, why this folder structure)
- Layer responsibility summary (Controller / Service / Wrapper / Transformer)
- Infrastructure overview (hosting, CI/CD, environments)

**Why it matters**: New developers and Copilot read this to understand where everything fits before touching code.

---

### `adr-template.md` → `docs/decisions/`

**Copy to**: `docs/decisions/[NNN]-[decision-title].md`

**What to fill in**:
- The decision being made
- The context that forced this decision
- Options considered (include the ones you rejected and why)
- The decision made
- Consequences (what gets easier, what gets harder)

**Why it matters**: When a future developer (or Copilot) asks "why is it done this way?", the ADR answers it with context, not just "someone decided this years ago."

**Example**: `docs/decisions/001-use-redis-for-rate-limiting.md`

---

### `project-template.md` → `docs/PROJECT.md`

**Copy to**: `docs/PROJECT.md` (or rename the existing stub)

**What to fill in**:
- What the project does (2–3 sentences — more than copilot-instructions.md)
- Who the users are
- Key business rules and constraints
- Links to external systems and their docs

**Why it matters**: Referenced from `copilot-instructions.md`. Gives Copilot deeper context on the business domain without bloating the core instructions file.

---

## `external-apis/` — One Folder Per External API

```
docs/external-apis/
└── dynamics/                    ← One folder per external API
    ├── README.md                ← Auth, base URL, rate limits, gotchas
    ├── accounts.api.md          ← Field map for Accounts entity
    └── contacts.api.md          ← Field map for Contacts entity
```

Create one folder per external API your project calls. Fill in the README first before any wrapper code is written.

> **Rule**: Never write a wrapper without the external API doc existing first. Use `/add-new-api` — it reads the doc before writing any code.

---

## `issues/` — One Doc Per Work Item

```
docs/issues/
├── ISSUE-001-login-rate-limiting.md     ← status: done
├── ISSUE-042-export-orders.md           ← status: execute (in progress)
└── ...
```

Each Issue doc tracks all 5 phases of the workflow. Open issues have `status: execute` or `status: plan`. Closed issues have `status: done`.

> **Rule**: When resuming work, always tell Copilot: `"Read #docs/issues/ISSUE-XXX-name.md first"`

---

## `apis/` — One Doc Per Internal Endpoint

Document your own API endpoints here (not external APIs). Use `api-doc-template.md`. Run `/generate-api-doc` after adding a new endpoint or `/update-api-doc` after changing one.

---

## `flows/` — One Doc Per Business Flow

Document multi-step user journeys here. Copy `flow-doc-template.md`. Keep flows short and linked to Issue docs where relevant.

---

## `decisions/` — Architecture Decision Records

Copy `adr-template.md` for each significant architecture or technology decision. Number them sequentially.

---

## `team-notes/` — Personal Scratch Space

Each developer gets their own subfolder: `docs/team-notes/[your-name]/`. Use it for personal notes, WIP ideas, and scratch research. These are committed but owned by each individual — no one edits another person's folder.

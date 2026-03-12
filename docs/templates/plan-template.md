# Plan Template for Work Folder

**File Location**: `work/ISSUE-XXX-description/plan.md`

This file contains all planning information: requirements, research findings, and implementation plan.

---

# ISSUE-XXX: [Short Title]

**Issue ID**: ISSUE-XXX  
**Type**: feature | fix | story | task | improvement  
**Owner**: [Developer Name]  
**Branch**: `<type>/XXX-description`  
**Created**: YYYY-MM-DD  
**Status**: discuss | research | plan | execute | verify | done

**Related**:
- Flow: `docs/flows/[flow-name]-flow.md`
- APIs: `docs/apis/[domain]/[endpoint].api.md`

---

## 📋 Phase 1: Requirements (Discuss)

**Status**: [ ] Not Started | [x] Complete

### What Are We Building?
[2-3 sentences: what is this issue? What problem does it solve?]

### Why?
[Business reason or user need]

### Who Needs This?
[User role, team, or system that benefits]

### Requirements
- [ ] [Specific requirement 1]
- [ ] [Specific requirement 2]
- [ ] [Specific requirement 3]

### Out of Scope
- [Things explicitly NOT included]

### Acceptance Criteria
- [ ] [Testable criterion 1]
- [ ] [Testable criterion 2]

### Open Questions
1. [Question] → **Answer**: [Answer or TBD]

---

## 🔍 Phase 2: Research Findings

**Status**: [ ] Not Started | [x] Complete

### Existing Patterns Found
- **Pattern**: [Name] → **Location**: `[file path]` — [Why relevant]
- **Pattern**: [Name] → **Location**: `[file path]` — [Why relevant]

### Files to Modify
| File | Change Needed |
|------|---------------|
| `[path/to/file.ts]` | [What needs to change] |
| `[path/to/service.ts]` | [What needs to change] |

### Dependencies
- [External library or service]
- [Other issues or components]

### Risks Identified
- ⚠️ [Risk 1 and mitigation plan]
- ⚠️ [Risk 2 and mitigation plan]

---

## 📐 Phase 3: Implementation Plan

**Status**: [ ] Not Started | [x] Complete

### Architecture Decisions
| Decision | Choice | Reason |
|----------|--------|--------|
| [e.g., caching strategy] | [e.g., Redis sliding window] | [Why this approach] |

### Task Breakdown

#### Backend Tasks
- [ ] [Task 1 — specific action with file path]
- [ ] [Task 2 — specific action with file path]

#### Frontend Tasks
- [ ] [Task 1 — specific action with file path]
- [ ] [Task 2 — specific action with file path]

#### Infrastructure
- [ ] [Config changes, env vars, deployments]

#### Tests
- [ ] **Unit**: [What to test, which files]
- [ ] **Integration**: [What to test, which flows]
- [ ] **E2E**: [What to test, which user journeys]

#### Documentation
- [ ] Update API doc: `docs/apis/[domain]/[endpoint].api.md`
- [ ] Update flow doc: `docs/flows/[flow-name]-flow.md`

### Plan Approved By
- **Developer**: [Name] — [Date]
- **Team Lead**: [Name] — [Date] (if required)

---

## Notes
- This plan is created in Phase 3 and referenced during execution
- Changes during implementation should be noted in `result.md`
- Keep this as the source of truth for "what was supposed to happen"

# Result Template for Work Folder

**File Location**: `work/ISSUE-XXX-description/result.md`

This file documents what actually happened during execution and verification.

---

# ISSUE-XXX: Execution Results

**Started**: YYYY-MM-DD  
**Completed**: YYYY-MM-DD  
**Branch**: `<type>/XXX-description`  
**Developer**: [Name]

---

## 🔨 Phase 4: Execution Notes

**Status**: [ ] Not Started | [x] Complete

### Progress Tracker
| Task (from plan.md) | Status | Completion Date | Notes |
|---------------------|--------|-----------------|-------|
| [Task 1] | ✅ | YYYY-MM-DD | [Any deviations or decisions] |
| [Task 2] | ✅ | YYYY-MM-DD | [Any deviations or decisions] |
| [Task 3] | 🔄 | | Currently in progress |

### Implementation Log

**YYYY-MM-DD**
- ✅ [What was implemented]
- 🔧 [Decision made and why it differed from plan]
- ⚠️ [Any blockers encountered and how resolved]

**YYYY-MM-DD**
- ✅ [What was implemented]
- 📝 [Important notes or discoveries]

### Deviations from Plan
| Original Plan | What Actually Happened | Reason |
|---------------|------------------------|--------|
| [Planned approach] | [Actual approach] | [Why we changed] |

### Commits Made
```
feat(ISSUE-XXX): [description] — [commit hash]
test(ISSUE-XXX): [description] — [commit hash]
docs(ISSUE-XXX): [description] — [commit hash]
fix(ISSUE-XXX): [description] — [commit hash]
```

---

## ✅ Phase 5: Verification Results

**Status**: [ ] Not Started | [x] Complete

### Test Results

**Unit Tests**: ✅ / ❌  
```
[X/Y passing]
[List of test files run]
```

**Integration Tests**: ✅ / ❌  
```
[X/Y passing]
[Key integration scenarios tested]
```

**E2E Tests**: ✅ / ❌  
```
[X/Y passing]
[User flows tested]
```

### Requirements Verification
| Requirement (from plan.md Phase 1) | Met? | Evidence / How Verified |
|------------------------------------|------|-------------------------|
| [Requirement 1] | ✅ | [Specific test or manual verification] |
| [Requirement 2] | ✅ | [Specific test or manual verification] |
| [Requirement 3] | ⚠️ | [Partial — notes on what's missing] |

### Acceptance Criteria Check
| Criterion (from plan.md Phase 1) | Met? | Evidence |
|----------------------------------|------|----------|
| [Criterion 1] | ✅ | [How verified] |
| [Criterion 2] | ✅ | [How verified] |

### Code Quality Checks
- [ ] No TypeScript errors
- [ ] No ESLint warnings
- [ ] Code follows project conventions (see `docs/codebase/conventions.md`)
- [ ] All tests passing
- [ ] No console errors or warnings

### Documentation Updates
- [ ] API docs updated: `docs/apis/[domain]/[endpoint].api.md`
- [ ] Flow docs updated: `docs/flows/[flow-name]-flow.md`
- [ ] Work folder complete: `plan.md` and `result.md` filled

---

## 🚀 Deployment / Merge Information

### PR Details
- **PR Number**: #XX
- **PR Title**: [Title]
- **PR URL**: [GitHub PR link]
- **Created**: YYYY-MM-DD
- **Merged**: YYYY-MM-DD
- **Merged By**: [Name]

### GitHub Issue
- **Issue Number**: #XX
- **Issue URL**: [GitHub issue link]
- **Status**: Closed by PR #XX

### Merge Commit
```
[commit hash] — Merge pull request #XX from owner/repo
```

---

## 📝 Post-Merge Notes

### What Worked Well
- [Thing 1]
- [Thing 2]

### What Could Be Improved
- [Improvement 1]
- [Improvement 2]

### Lessons Learned
- [Lesson 1]
- [Lesson 2]

### Future Work / Follow-ups
- [ ] [Potential enhancement]
- [ ] [Technical debt to address later]

---

## Summary for Team

**One-sentence summary**: [What was accomplished]

**Impact**: [Who benefits and how]

**Metrics** (if applicable):
- Performance: [before → after]
- Test coverage: [X%]
- Lines changed: [+XXX / -YYY]

---

**Status**: ✅ Complete and Merged  
**Closed**: YYYY-MM-DD

---
description: 'Execute the approved plan from a Issue doc using TDD'
agent: 'TDD'
tools: ['editFiles', 'terminal', 'search', 'codebase', 'problems']
---
Execute the implementation plan for this Issue.

Read the plan from Phase 3 of the Issue doc and implement it task by task.
Write tests FIRST, then implementation code. Commit after each passing cycle.
Update the Phase 4 progress tracker in the Issue doc as you go.

Issue doc: ${input:ISSUE-doc:Path to Issue doc (e.g., docs/Issues/ISSUE-042-name.md)}

After completing all tasks, ask: "Run /verify to check if the Issue is ready to merge?"

---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

Use /tdd where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, use /code-review to review the work.

Commit your work to the current branch.

Then prove it works, unless the caller proves the work (as `implement-spec` does). If the repo has a project verification skill (a `verify-*` skill, or one that `AGENTS.md` or `CLAUDE.md` names), start a fresh subagent that calls the Skill tool with it at the committed head. It proves the change on the real surface and returns `PASS`, `PASS+NOTES` or `FAIL` with evidence for every defect it can prove. If a PR exists, post the verdict on it with the SHA. "Inconclusive" is not a pass.

- A defect that the default branch shows without this change: file it as a new issue in the issue tracker. It does not block.
- Every defect that this change causes: fix them all, commit, and prove it works again with a fresh subagent, until the verdict is a pass.

With no verification skill, say in your report that the work is not proven.

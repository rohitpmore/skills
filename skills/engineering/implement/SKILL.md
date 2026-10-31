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

Then prove the change, unless your caller proves it (`/implement-spec` proves the whole spec once, at its end). If the repo has a verification skill (`verify-*`, or one that `AGENTS.md` or `CLAUDE.md` names), start a fresh subagent with it, and pass the issue, the PR, the base SHA and the head SHA. Its scope is the diff from base to head: it proves what that diff touches. A full end-to-end run and video recordings run only when the user asks for them. It returns a verdict, `PASS`, `PASS+NOTES` or `FAIL`, with every defect it can prove. Fix each defect that it assigns to this change, commit, and prove the new head with a fresh subagent, until it passes. With no verification skill, report the work as not proven.

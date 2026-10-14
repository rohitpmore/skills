# rohitpmore/skills

A fork of [mattpocock/skills](https://github.com/mattpocock/skills) with local changes.
Keep each change small, so that upstream merges stay clean.

## Local changes

- `implement` and `implement-spec` end with a **prove it works** step: a fresh subagent runs
  the repo's verification skill (`verify-*`) and returns a verdict. One implementer, with
  `implement`, fixes every defect that the change causes, then a fresh subagent proves it again.

## Get upstream changes

The default branch, `stable`, follows Matt's release tags only, never his `main`.

```bash
git fetch upstream --tags
git tag -l 'v*' --sort=-v:refname | head -1   # the newest release
git merge <tag>                               # resolve conflicts in the local changes above
git push
```

Based on: v1.3.1.

Then, in each project: `npx skills update -p -y`.

## Install

```bash
npx skills add rohitpmore/skills --skill <name> --agent claude-code --copy -y
```

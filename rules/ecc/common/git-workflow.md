# Git Workflow

## Commit Message Format
```
<type>: <description>

<optional body>
```

Types: feat, fix, refactor, docs, test, chore, perf, ci

Note: Disable co-author attribution: set `"includeCoAuthoredBy": false` in `~/.claude/settings.json` (Claude Code append `Co-Authored-By` by default; ECC not ship this setting).

## Pull Request Workflow

Making PR:
1. Read full commit history (not just latest commit)
2. `git diff [base-branch]...HEAD` see all changes
3. Draft full PR summary
4. Include test plan with TODOs
5. Push with `-u` flag if new branch

> Full dev process (planning, TDD, code review) before git ops:
> see [development-workflow.md](./development-workflow.md).
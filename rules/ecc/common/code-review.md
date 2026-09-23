# Code Review Standards

## Purpose

Review catch quality, security, maintainability before merge. This rule say when + how review.

## When to Review

**MANDATORY review triggers:**

- After write or change code
- Before commit to shared branch
- Security-sensitive code change (auth, payments, user data)
- Architecture change
- Before merge pull request

**Pre-Review Requirements:**

Before ask review:

- All automated checks (CI/CD) pass
- Merge conflicts resolved
- Branch up to date with target branch

## Review Checklist

Before call code done:

- [ ] Code readable, good name
- [ ] Functions focused (<50 lines)
- [ ] Files cohesive (<800 lines)
- [ ] No deep nesting (>4 levels)
- [ ] Errors handled explicit
- [ ] No hardcoded secrets or credentials
- [ ] No console.log or debug statements
- [ ] Tests exist for new work
- [ ] Coverage 80% minimum

## Security Review Triggers

**STOP and use security-reviewer agent when:**

- Authentication or authorization code
- User input handling
- Database queries
- File system operations
- External API calls
- Cryptographic operations
- Payment or financial code

## Review Severity Levels

| Level | Meaning | Action |
|-------|---------|--------|
| CRITICAL | Security hole or data loss risk | **BLOCK** - Fix before merge |
| HIGH | Bug or big quality issue | **WARN** - Should fix before merge |
| MEDIUM | Maintainability worry | **INFO** - Consider fix |
| LOW | Style or small suggestion | **NOTE** - Optional |

## Agent Usage

Use these agents for review:

| Agent | Purpose |
|-------|---------|
| **code-reviewer** | General quality, patterns, best practice |
| **security-reviewer** | Security holes, OWASP Top 10 |
| **typescript-reviewer** | TypeScript/JavaScript issues |
| **python-reviewer** | Python issues |
| **go-reviewer** | Go issues |
| **rust-reviewer** | Rust issues |

## Review Workflow

```
1. Run git diff to understand changes
2. Check security checklist first
3. Review code quality checklist
4. Run relevant tests
5. Verify coverage >= 80%
6. Use appropriate agent for detailed review
```

## Common Issues to Catch

### Security

- Hardcoded credentials (API keys, passwords, tokens)
- SQL injection (string concat in query)
- XSS (unescaped user input)
- Path traversal (unsanitized file path)
- CSRF protection missing
- Auth bypass

### Code Quality

- Big functions (>50 lines) - split small
- Big files (>800 lines) - extract modules
- Deep nesting (>4 levels) - early return
- Missing error handling - handle explicit
- Mutation - prefer immutable
- Missing tests - add coverage

### Performance

- N+1 queries - use JOINs or batch
- Missing pagination - add LIMIT
- Unbounded queries - add constraints
- Missing caching - cache expensive work

## Approval Criteria

- **Approve**: No CRITICAL or HIGH
- **Warning**: Only HIGH (merge careful)
- **Block**: CRITICAL found

## Integration with Other Rules

Works with:

- [testing.md](testing.md) - Coverage requirements
- [security.md](security.md) - Security checklist
- [git-workflow.md](git-workflow.md) - Commit standards
- [agents.md](agents.md) - Agent delegation
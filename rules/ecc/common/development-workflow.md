# Development Workflow

> Extends [common/git-workflow.md](./git-workflow.md) with full feature dev process before git ops.

Feature Implementation Workflow = pipeline: research, plan, TDD, code review, then commit.

## Feature Implementation Workflow

0. **Research & Reuse** _(mandatory before new implementation)_
   - **GitHub code search first:** Run `gh search repos` and `gh search code` for existing implementations, templates, patterns before write new.
   - **Library docs second:** Context7 or vendor docs confirm API behavior, package usage, version details before implement.
   - **Exa only when first two not enough:** Exa for wider web research after GitHub search + primary docs.
   - **Check package registries:** Search npm, PyPI, crates.io before write utility code. Battle-tested library beat hand-rolled.
   - **Search adaptable implementations:** Open-source projects solving 80%+ of problem, forkable/portable/wrappable.
   - Adopt or port proven approach over net-new code when it meet requirement.

1. **Plan First**
   - **planner** agent make implementation plan
   - Planning docs before code: PRD, architecture, system_design, tech_doc, task_list
   - Name dependencies and risks
   - Break into phases

2. **TDD Approach**
   - Use **tdd-guide** agent
   - Tests first (RED)
   - Implement to pass (GREEN)
   - Refactor (IMPROVE)
   - Verify 80%+ coverage

3. **Code Review**
   - **code-reviewer** agent right after code written
   - Fix CRITICAL and HIGH
   - Fix MEDIUM when possible

4. **Commit & Push**
   - Detailed commit messages
   - Conventional commits format
   - See [git-workflow.md](./git-workflow.md) for commit format and PR process

5. **Pre-Review Checks**
   - All automated checks (CI/CD) pass
   - Merge conflicts resolved
   - Branch up to date with target branch
   - Request review only after these pass
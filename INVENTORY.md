# Inventory (2026-09-25)

Setup global do Claude Code em `~/.claude`. Este repo guarda `CLAUDE.md`, `RTK.md`, `rules/` e `skills/` (custom); o resto está listado aqui para reinstalar.

## Plugins

| Plugin | Marketplace |
|---|---|
| `andrej-karpathy-skills@karpathy-skills` | forrestchang/andrej-karpathy-skills |
| `caveman@caveman` | JuliusBrussee/caveman |
| `context-mode@context-mode` | mksglu/context-mode |
| `frontend-design@claude-plugins-official` | oficial |
| `mattpocock-skills@claude-plugins-official` | oficial |
| `ponytail@ponytail` | DietrichGebert/ponytail |

Reinstalar (dentro do Claude Code):

```
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin marketplace add JuliusBrussee/caveman
/plugin marketplace add mksglu/context-mode
/plugin marketplace add DietrichGebert/ponytail
/plugin install andrej-karpathy-skills@karpathy-skills
/plugin install caveman@caveman
/plugin install context-mode@context-mode
/plugin install frontend-design@claude-plugins-official
/plugin install mattpocock-skills@claude-plugins-official
/plugin install ponytail@ponytail
```

## Outras ferramentas

- **ECC (everything-claude-code)** — origem de `rules/ecc`, agents, commands, hooks e `skills/ecc`.
- **RTK (Rust Token Killer)** — CLI proxy, ver `RTK.md`.
- **graphify** — skill em `~/.claude/skills/graphify` (cópia em `skills/graphify`).

## Skills (`~/.claude/skills`)

- caveman (links para `~/.agents/skills`): `cavecrew`, `caveman`, `caveman-commit`, `caveman-compress`, `caveman-help`, `caveman-review`, `caveman-stats`
- `graphify`, `llm-council` — copiadas em `skills/` deste repo
- `impeccable` v4.3.1 (pbakaus/impeccable, 17 MB, não copiada) + agents `impeccable-asset-producer`, `impeccable-documenter`, `impeccable-finish-reviewer`, `impeccable-manual-edit-applier`
- `find-skills` (vercel-labs/skills, em `~/.agents/skills`)
- claude.ai (sincronizadas automaticamente em `skills/synced`): docs, docx, import-memory, morning, pdf, pptx, skill-creator, xlsx

Reinstalar skills externas:

```bash
npx skills add JuliusBrussee/caveman
npx skills add vercel-labs/skills --skill find-skills
npx skills add pbakaus/impeccable
```
- `ecc/`: accessibility, agent-introspection-debugging, agent-self-evaluation, agent-sort, ai-regression-testing, android-clean-architecture, angular-developer, api-design, architecture-decision-records, backend-patterns, browser-qa, bun-runtime, ck, clickhouse-io, click-path-audit, codebase-onboarding, codehealth-mcp, code-tour, coding-standards, compose-multiplatform-patterns, config-gc, configure-ecc, context-budget, continuous-learning, continuous-learning-v2, council, cpp-coding-standards, cpp-testing, csharp-testing, dart-flutter-patterns, database-migrations, delivery-gate, design-system, django-celery, django-patterns, django-tdd, django-verification, dmux-workflows, dotnet-patterns, e2e-testing, ecc-guide, ecc-recipes, error-handling, eval-harness, fastapi-patterns, flutter-dart-code-review, frontend-a11y, frontend-design-direction, frontend-patterns, frontend-slides, fsharp-testing, generating-python-installer, git-workflow, golang-patterns, golang-testing, growth-log, hexagonal-architecture, hookify-rules, inherit-legacy-style, intent-driven-development, iterative-retrieval, java-coding-standards, jpa-patterns, kotlin-coroutines-flows, kotlin-exposed-patterns, kotlin-ktor-patterns, kotlin-patterns, kotlin-testing, laravel-patterns, laravel-plugin-discovery, laravel-tdd, laravel-verification, loop-design-check, make-interfaces-feel-better, mcp-server-patterns, motion-advanced, motion-foundations, motion-patterns, motion-ui, mysql-patterns, nestjs-patterns, nextjs-turbopack, nuxt4-patterns, perl-patterns, perl-testing, plan-canvas, plankton-code-quality, postgres-patterns, prisma-patterns, production-audit, product-lens, python-patterns, python-testing, quarkus-patterns, quarkus-tdd, quarkus-verification, react-native-patterns, react-patterns, react-performance, react-testing, redis-patterns, repo-scan, rules-distill, rust-patterns, rust-testing, santa-method, skill-scout, skill-stocktake, springboot-patterns, springboot-tdd, springboot-verification, strategic-compact, tdd-workflow, tinystruct-patterns, ui-to-vue, verification-loop, vite-patterns, vue-patterns, windows-desktop-e2e

## Agents (71, `~/.claude/agents`)

a11y-architect, agent-evaluator, architect, build-error-resolver, chief-of-staff, code-architect, code-explorer, code-reviewer, code-simplifier, comment-analyzer, conversation-analyzer, cpp-build-resolver, cpp-reviewer, csharp-reviewer, dart-build-resolver, database-reviewer, django-build-resolver, django-reviewer, doc-updater, docs-lookup, e2e-runner, fastapi-reviewer, flutter-reviewer, fsharp-reviewer, gan-evaluator, gan-generator, gan-planner, go-build-resolver, go-reviewer, harmonyos-app-resolver, harness-optimizer, healthcare-reviewer, homelab-architect, impeccable-asset-producer, impeccable-documenter, impeccable-finish-reviewer, impeccable-manual-edit-applier, java-build-resolver, java-reviewer, kotlin-build-resolver, kotlin-reviewer, loop-operator, marketing-agent, mle-reviewer, network-architect, network-config-reviewer, network-troubleshooter, opensource-forker, opensource-packager, opensource-sanitizer, performance-optimizer, php-reviewer, planner, pr-test-analyzer, python-reviewer, pytorch-build-resolver, react-build-resolver, react-reviewer, refactor-cleaner, rust-build-resolver, rust-reviewer, security-reviewer, seo-specialist, silent-failure-hunter, spec-miner, swift-build-resolver, swift-reviewer, tdd-guide, type-design-analyzer, typescript-reviewer, vue-reviewer

## Commands (94, `~/.claude/commands`)

aside, auto-update, build-fix, checkpoint, code-review, cost-report, cpp-build, cpp-review, cpp-test, ecc-guide, epic-claim, epic-decompose, epic-publish, epic-review, epic-sync, epic-unblock, epic-validate, evolve, fastapi-review, feature-dev, flutter-build, flutter-review, flutter-test, gan-build, gan-design, go-build, go-review, go-test, gradle-build, harness-audit, hookify, hookify-configure, hookify-help, hookify-list, instinct-export, instinct-import, instinct-status, jira, kotlin-build, kotlin-review, kotlin-test, learn, learn-eval, loop-start, loop-status, marketing-campaign, model-route, multi-backend, multi-execute, multi-frontend, multi-plan, multi-workflow, orch-add-feature, orch-build-mvp, orch-change-feature, orch-fix-defect, orch-refine-code, orch-review, plan, plan-canvas, plan-prd, pm2, pr, project-init, projects, promote, prp-commit, prp-implement, prp-plan, prp-pr, prp-prd, prune, python-review, quality-gate, react-build, react-review, react-test, refactor-clean, resume-session, review-pr, rust-build, rust-review, rust-test, santa-loop, save-session, security-scan, sessions, setup-pm, skill-create, skill-health, test-coverage, update-codemaps, update-docs, vue-review

## Hooks (settings.json)

Eventos: Notification, PostToolUse, PostToolUseFailure, PreCompact, PreToolUse, SessionEnd, SessionStart, Stop, UserPromptSubmit. Statusline: `hooks/caveman-statusline.ps1`.

## MCP servers (templates ECC, config não incluída: contém chaves)

nexus, jira, github, firecrawl, supabase, memory, omega-memory, longhand, sequential-thinking, vercel, railway, cloudflare-docs, cloudflare-workers-builds, cloudflare-workers-bindings, cloudflare-observability, clickhouse, exa-web-search, parallel-search, context7, codescene, magic, memxus, filesystem, playwright, fal-ai, browserbase, browser-use, devfleet, token-optimizer, laraplugins, confluence, evalview, squish

## Restaurar

```bash
git clone https://github.com/mathst/claude-config ~/claude-config
cp ~/claude-config/CLAUDE.md ~/claude-config/RTK.md ~/.claude/
cp -r ~/claude-config/rules ~/.claude/
cp -r ~/claude-config/skills/* ~/.claude/skills/
```

Depois reinstalar plugins (acima) e ECC.

## Atualizar backup

```bash
cd ~/claude-config
cp ~/.claude/CLAUDE.md ~/.claude/RTK.md . && rm -rf rules skills && cp -r ~/.claude/rules . && mkdir skills && cp -r ~/.claude/skills/{graphify,llm-council} skills/
git add -A && git commit -m "chore: sync claude config" && git push
```

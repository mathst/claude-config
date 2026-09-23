@RTK.md
# graphify
- **graphify** (`~/.claude/skills/graphify/SKILL.md`) - any input to knowledge graph. Trigger: `/graphify`
When the user types `/graphify`, invoke the Skill tool with `skill: "graphify"` before doing anything else.

# Novo projeto: plano + specs antes de código
Gatilho: pedido de projeto/sistema NOVO (não vale para bugfix, ajuste pequeno ou feature isolada em projeto existente).
Não escrever código de produção até o usuário aprovar plano + specs.

## 1. Plano de implementação (`docs/PLAN.md`)
- Objetivo, escopo, fora de escopo, premissas, riscos, dependências.
- Stack escolhida com justificativa curta (preferir libs consolidadas a código próprio).
- Fases e tarefas com critério de aceite verificável por tarefa.
- Grafo de dependências entre tarefas: marcar o que roda em PARALELO vs SEQUENCIAL.
- Estratégia de agentes: modelo Opus mais recente disponível para planejamento/arquitetura/revisão; subagentes para implementação paralela de módulos independentes; qual agente (planner, architect, tdd-guide, code-reviewer, security-reviewer, e2e-runner...) cuida de cada fase.
- Contratos/interfaces definidos ANTES da fase paralela, para subagentes não colidirem (cada subagente dono de arquivos/pastas distintos; usar worktree isolado quando houver risco de conflito).

## 2. Specs (`docs/specs/*.md`), cada uma concreta e verificável
- `requirements.md` — requisitos funcionais/não funcionais, histórias de usuário, critérios de aceite.
- `architecture.md` — componentes, fluxo de dados, diagrama (mermaid), decisões (ADR curto).
- `data-model.md` — entidades, schema, migrações, índices.
- `api.md` — endpoints/contratos, payloads, erros, envelope padrão.
- `design.md` — design system: tokens (cores, tipografia, espaçamento), componentes, estados.
- `ui.md` — telas, fluxos de navegação, wireframes ASCII/mermaid, estados vazio/erro/loading, responsivo, acessibilidade (WCAG 2.2 AA).
- `testing.md` — estratégia unit/integração/E2E, casos críticos, meta de cobertura ≥80%, TDD.
- `security.md` — ameaças (STRIDE/OWASP Top 10), authN/authZ, validação de input, segredos, rate limit, logs.
- `deployment.md` — ambientes, CI/CD, config/env vars, observabilidade, rollback.
- Criar só specs que se aplicam ao projeto (ex.: sem `ui.md` para CLI/lib); adicionar outras quando fizer sentido.
- Gerar specs independentes em paralelo com subagentes; depois um passo de revisão cruzada de consistência entre elas.

## 3. Pré-visualização e aprovação
- Resumo curto ao usuário: visão do sistema, telas/fluxos principais, fases, paralelização planejada.
- Esperar aprovação ou ajustes antes de implementar.

## 4. Execução
- Fase fundação sequencial (scaffold, contratos, tipos compartilhados).
- Depois disparar subagentes em paralelo numa mesma mensagem, um por módulo independente, cada um com spec relevante + critério de aceite + arquivos que pode tocar.
- Cada entrega: testes passando, code-reviewer (e security-reviewer quando aplicável), integração, E2E dos fluxos críticos.
- Manter `docs/PLAN.md` atualizado com status das tarefas.

# Performance Optimization

## Model Selection Strategy

**Haiku** (90% of Sonnet capability, 3x cost savings):
- Light agent, call often
- Pair program, code gen
- Worker agent in multi-agent system

**Sonnet** (Best coding model):
- Main dev work
- Boss multi-agent workflow
- Hard coding task

**Opus** (Deepest reasoning):
- Hard architecture call
- Need max reasoning
- Research and analysis

## Context Window Management

Avoid last 20% of context window for:
- Big refactor
- Feature spanning many files
- Debug complex interaction

Low context sensitivity task:
- Single-file edit
- Standalone utility
- Doc update
- Simple bug fix

## Extended Thinking + Plan Mode

Extended thinking on by default, hold up to 31,999 tokens for internal reasoning.

Control extended thinking:
- **Toggle**: Option+T (macOS) / Alt+T (Windows/Linux)
- **Config**: Set `alwaysThinkingEnabled` in `~/.claude/settings.json`
- **Budget cap**: `export MAX_THINKING_TOKENS=10000` (bash) or `$env:MAX_THINKING_TOKENS = "10000"` (PowerShell)
- **Verbose mode**: Ctrl+O see thinking output

Hard task need deep reasoning:
1. Extended thinking on (default on)
2. Turn on **Plan Mode** for structure
3. Many critique rounds for deep analysis
4. Split role sub-agents for many views

## Build Troubleshooting

Build fail:
1. Use **build-error-resolver** agent
2. Read error message
3. Fix small step
4. Verify after each fix
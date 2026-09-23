# Coding Style

## Immutability (CRITICAL)

ALWAYS make new object. NEVER mutate old one:

```
// Pseudocode
WRONG:  modify(original, field, value) → changes original in-place
CORRECT: update(original, field, value) → returns new copy with change
```

Why: immutable data = no hidden side effect, easy debug, safe concurrency.

## Core Principles

### KISS (Keep It Simple)

- Simplest thing that work
- No premature optimize
- Clarity beat clever

### DRY (Don't Repeat Yourself)

- Pull repeat logic into shared function
- No copy-paste drift
- Abstract only when repeat real, not guess

### YAGNI (You Aren't Gonna Need It)

- No build feature before need
- No speculative general
- Start simple, refactor when pressure real

## File Organization

MANY SMALL FILES > FEW LARGE FILES:
- High cohesion, low coupling
- 200-400 lines typical, 800 max
- Pull utils out of big module
- Group by feature/domain, not by type

## Error Handling

ALWAYS handle error full:
- Handle error explicit at every level
- Friendly error message in UI code
- Log detail error context server side
- Never swallow error silent

## Input Validation

ALWAYS validate at boundary:
- Validate all user input before use
- Use schema validation when have
- Fail fast, clear message
- Never trust outside data (API response, user input, file content)

## Naming Conventions

- Variables and functions: `camelCase`, descriptive name
- Booleans: prefer `is`, `has`, `should`, `can` prefix
- Interfaces, types, components: `PascalCase`
- Constants: `UPPER_SNAKE_CASE`
- Custom hooks: `camelCase` with `use` prefix

## Code Smells to Avoid

### Deep Nesting

Early return beat nested if when logic stack up.

### Magic Numbers

Named constant for threshold, delay, limit.

### Long Functions

Split big function into focused piece, clear job each.

## Code Quality Checklist

Before call work done:
- [ ] Code readable, good name
- [ ] Functions small (<50 lines)
- [ ] Files focused (<800 lines)
- [ ] No deep nesting (>4 levels)
- [ ] Proper error handling
- [ ] No hardcoded values (use constants or config)
- [ ] No mutation (immutable patterns used)
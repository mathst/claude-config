# Hooks System

## Hook Types

- **PreToolUse**: Before tool run (validate, change params)
- **PostToolUse**: After tool run (auto-format, checks)
- **Stop**: Session end (final verify)

## Auto-Accept Permissions

Careful:
- Enable for trusted, well-defined plans
- Disable for exploring
- Never use dangerously-skip-permissions flag
- Set `allowedTools` in `~/.claude.json` instead

## TodoWrite Best Practices

TodoWrite tool for:
- Track progress on multi-step work
- Verify understanding of instructions
- Real-time steering
- Show granular steps

Todo list reveal:
- Out of order steps
- Missing items
- Extra items
- Wrong granularity
- Misread requirements
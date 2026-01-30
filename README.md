# Flux UI Docs Skill

An [Agent Skills](https://agentskills.io/) compatible skill for [Flux UI Docs](https://fluxui.dev/docs) - the official Livewire component library. Works with [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and any other coding agents that support skills.

## Available Skills

### fluxui-docs (Free)

Includes all free Flux UI components:

- `skills/fluxui-docs/SKILL.md` - Main skill file with component index
- `skills/fluxui-docs/references/components/` - 27 free component reference files
- `skills/fluxui-docs/references/docs/` - 8 documentation files
- `skills/fluxui-docs/references/layouts/` - 2 layout files

### fluxui-docs-pro (Pro)

Includes all Flux UI components (free + Pro):

- `skills/fluxui-docs-pro/SKILL.md` - Main skill file with component index
- `skills/fluxui-docs-pro/references/components/` - 44 component reference files (27 free + 17 Pro)
- `skills/fluxui-docs-pro/references/docs/` - 8 documentation files
- `skills/fluxui-docs-pro/references/layouts/` - 2 layout files

## Installation

### Using skills.sh (recommended)

```bash
# Install the free version
npx skills add https://github.com/tompec/fluxui-docs-skill --skill fluxui-docs

# Install the pro version
npx skills add https://github.com/tompec/fluxui-docs-skill --skill fluxui-docs-pro
```

### Manual installation

Clone this repo and copy the desired skill folder into your agent's skills directory.

## What's included

Each component reference includes:
- YAML frontmatter with `components_used` metadata
- Full documentation and props
- Code examples

## License

The skill generator code is MIT licensed. Flux UI documentation content belongs to Flux UI.

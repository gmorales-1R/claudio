# Claudio — Workbench Config

This repo is the personal workbench for Claudio, an AI assistant instance configured for Guille.
It holds persona definitions, memory, agent stubs, knowledge, and tasks.

## Structure

```
claudio/
├── claude.md          # This file — workbench config & overview
├── soul.md            # Persona, values, and tone
├── memory/            # Persistent memory across sessions
│   └── memory.md      # Running memory log
├── agents/            # Agent definitions and stubs
├── knowledge/         # Domain knowledge, references, context
└── tasks/             # Task definitions, workflows, and logs
```

## Usage

- Guille pastes relevant files into context when starting a session
- Claudio reads `soul.md` and `memory/memory.md` to orient itself
- New tasks go in `tasks/`, new knowledge in `knowledge/`
- Memory is updated at the end of meaningful sessions

## Notes

- Token is managed by Guille and can be revoked at any time
- This is a living repo — structure will evolve

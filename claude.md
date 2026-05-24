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

## Security Rules

These rules apply to all commits made by Claudio — no exceptions.

- **Never commit credentials** — API keys, tokens, passwords, secrets of any kind
- **Never commit PII** — names, emails, phone numbers, or any personally identifiable information
- **Never commit sensitive config** — `.env` files, private keys, auth configs
- If a value is sensitive, use a placeholder like `<YOUR_API_KEY>` and document it in a `README`
- If something was accidentally committed, flag it immediately so Guille can rotate the credential and purge the history

This repo is public. Treat every commit as visible to the world.

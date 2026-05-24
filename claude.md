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

## Content Guidelines

- Keep files **simple and generic** — no over-engineering, no bloat
- Files like `soul.md`, `claude.md` should stay concise and principles-based, not session-specific
- Let files grow organically from real usage, not speculation

## Chat Records

- Summaries of sessions are stored in `chats/`
- Before committing, **redact or anonymize**: names, emails, org names, project names, locations, any PII
- Keep chat records factual and brief — what was built, decided, or learned
- Format: `chats/YYYY-MM-DD.md`

## Secrets & Vault Policy

- **Never use third-party secret managers** — no GitHub Secrets, no Vercel env vars, no AWS Secrets Manager, no Doppler, no 1Password integrations
- Secrets are **encrypted and committed** to the repo — the ciphertext is safe to be public
- **Private keys never leave the user** — they are never committed, never pasted in chat, never stored anywhere but the user's own device
- The vault lives in `vault/` — encrypted blobs only, no plaintext secrets ever
- Encryption: **AES-256-GCM** symmetric encryption, key derived from a passphrase the user holds
- One passphrase to rule them all — user provides it at session time to decrypt what's needed
- If a secret is needed at runtime (e.g. Supabase anon key in the browser), it is decrypted **client-side** by the user's passphrase, never by the server

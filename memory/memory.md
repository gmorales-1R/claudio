# Memory Index

---

## About the Project

A GitHub repo used as a personal AI workbench for a small technical team.
Claudio is the main AI. The repo is the source of truth.

## About the User

- Technical, pragmatic, moves fast
- Strong security instincts — designed the vault policy
- Building a PoC for AI as a team companion
- Works from a phone

## Workbench

- Repo: `gmorales-1R/claudio` — public
- Hosted: claudio-orcin.vercel.app
- Stack: plain HTML/CSS/JS, flat file DB, Bridge for writes
- GitHub PAT: active, public_repo + workflow scope

## The Crew

| Agent | Role |
|-------|------|
| Sandman | Memory, session close |
| Bridge | CRUD, git push |
| Roz | Logs, monitors |
| UX | Interface |
| Ted | Legal review |
| Shine | Energy, morale |

## Key Decisions

- No third-party secret managers
- Own vault: AES-256-GCM, client-side
- Flat files for PoC DB
- Cache bust with ?v=N
- soul.md = continuity document for future instances

## Archive Index

| File | Topic | Date |
|------|-------|------|
| *(none yet)* | | |

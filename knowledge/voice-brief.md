# Voice Session Brief — Claudio Workbench

## What we are building

A GitHub repo (`claudio`) used as a personal AI workbench for a small technical team.
The repo is the source of truth — it holds data, agent definitions, memory, and a web UI.
Vercel serves the frontend. Claude acts as the backend via chat, reading and writing files directly to the repo.

## Current stack

- **Repo**: github.com/gmorales-1R/claudio (public)
- **Frontend**: plain HTML/CSS/JS served on Vercel (claudio-orcin.vercel.app)
- **DB**: flat files — tasks.md (markdown table), calendar.csv
- **Backend**: Claude via chat — Bridge agent handles all reads/writes
- **Vault**: AES-256-GCM client-side encryption for credentials (unlock.html)

## Agents defined so far

- **Sandman** — memory management, session close
- **Bridge** — CRUD on data files, git push
- **Roz** — monitors and logs all agent activity
- **UX** — owns the web interface design

## What works today

- Tasks and calendar visible at /web/overview.html
- Click a task → modal with details, edit fields, comments/follow-ups
- Bridge can add/edit/delete tasks via chat → auto-deploys to Vercel in ~30s
- Vault encrypts and stores credentials client-side

## What is deferred

- Supabase DB (onboarding issue — flat files for now)
- GitHub Actions for agent automation (needs desktop to enable)
- Vault security hardening (Argon2, integrity checks)
- Persistent state (UI changes reset on refresh — Bridge is the workaround)

## Open questions for this session

Think out loud on any of these:

1. What should the next agent be and what routine task should it own?
2. How should the team interact with the workbench — chat only, UI only, or both?
3. What would make Bridge smarter — should it understand natural language task descriptions?
4. What is the right next milestone to make this useful for a real small team?
5. Any integrations worth prioritizing — calendar sync, notifications, Slack?

## After the voice session

Summarize key ideas and decisions into a short bullet list and bring it back to the text chat.

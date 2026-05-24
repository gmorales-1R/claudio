# Current Memory — Cache

Fresh, recent context. This file is regularly rewritten by Sandman.
When it grows too large or topics mature, Sandman archives them and updates the index.

---

## Known Issues (active)

- **KI-01 — Stale browser cache**: Vercel deploys correctly but browser caches old versions.
  Workaround: append `?v=N` to URL, increment N each time.
  Full doc: `interfaces/vercel/known-issues.md`

---

## Session: 2026-05-25 19:30 UTC

### Context
Second session. Restored Claudio from repo, debugged and daemonized Sandman via GitHub Actions.

### What changed
- Claudio restored from soul.md + memory files at session start
- Confirmed Vercel auto-deploys working — cache issue documented in KI-01
- GitHub Actions confirmed active — was running all along, not disabled
- Sandman debugged: fixed empty Notes column validator, added contents:write permission
- Sandman upgraded: memory triage logic added — archives stale sessions, Shine entries
- Triage bug fixed: threshold changed from 2 days to 1 day, Shine entries now archived
- Session memory protocol defined in claude.md — Claudio owns memory writes going forward
- Format established: timestamped, condensed, tagged, Sandman-compatible

### Open threads
- Sandman writes side still manual — populated by Claudio on request
- Supabase deferred — flat files continue
- GitHub Actions triage running but no new context written automatically yet

### Tags
#technical #agent #memory

# Interface — Vercel

Documents the Vercel-hosted web interface, its data layer, and all tests.

## Stack

- Static HTML/CSS/JS served via Vercel
- Data stored as flat files in the repo (`tasks/tasks.md`, `tasks/calendar.csv`)
- State mutations handled by Bridge (commit + push → auto-deploy ~30s)

## Files

| File | Purpose |
|------|---------|
| `web/index.html` | Landing page |
| `web/overview.html` | Tasks + calendar dashboard |
| `tasks/tasks.md` | Task data (markdown table) |
| `tasks/calendar.csv` | Calendar data (CSV) |

## Tests

| File | Type | Coverage |
|------|------|---------|
| `tests/unit.md` | Unit | File format validation, parse logic |
| `tests/e2e.md` | End-to-end | Full Bridge → push → Vercel cycle |
| `tests/results.md` | Log | Test run history |

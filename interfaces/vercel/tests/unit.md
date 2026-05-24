# Unit Tests — Vercel Interface

Tests for individual components in isolation.

---

## UT-01 — tasks.md format validation

**What**: Verify `tasks/tasks.md` has valid markdown table structure
**Pass criteria**:
- Has header row with: ID, Title, Status, Priority, Due, Notes
- Has separator row
- Each data row has 6 pipe-delimited columns
- ID is numeric
- Status is one of: `todo`, `in-progress`, `done`
- Priority is one of: `high`, `medium`, `low`
- Date is `YYYY-MM-DD` or empty

---

## UT-02 — calendar.csv format validation

**What**: Verify `tasks/calendar.csv` has valid CSV structure
**Pass criteria**:
- Header row: `id,title,date,time,notes`
- Each row has 5 comma-separated fields
- Date is `YYYY-MM-DD`
- Time is `HH:MM`

---

## UT-03 — Bridge fetch integrity

**What**: Bridge fetches latest file before any write
**Pass criteria**:
- File content fetched fresh from repo
- No edits applied to stale/cached content

---

## UT-04 — Bridge task add

**What**: Bridge adds a new task row to tasks.md
**Pass criteria**:
- New row appended with correct format
- ID is max(existing IDs) + 1
- Status defaults to `todo`
- All columns present

---

## UT-05 — Bridge task complete

**What**: Bridge marks a task as `done`
**Pass criteria**:
- Correct row updated by ID
- Only `status` column changes
- All other columns preserved

---

## UT-06 — Bridge task delete

**What**: Bridge removes a task row by ID
**Pass criteria**:
- Row with matching ID removed
- All other rows preserved
- File format remains valid

---

## UT-07 — Bridge calendar add

**What**: Bridge adds a new event to calendar.csv
**Pass criteria**:
- New row appended with correct format
- ID is max(existing IDs) + 1
- Date and time in correct format

# End-to-End Tests — Vercel Interface

Full cycle tests: chat instruction → Bridge → git push → Vercel deploy → UI verification.

---

## E2E-01 — Add task full cycle

**Steps**:
1. Instruct Bridge to add a task via chat
2. Bridge fetches current `tasks/tasks.md`
3. Bridge appends new row and pushes
4. Wait ~30s for Vercel redeploy
5. Open `overview.html` and verify task appears

**Pass criteria**:
- Task visible in UI with correct title, priority, due date
- ID is unique and sequential

---

## E2E-02 — Complete task full cycle

**Steps**:
1. Instruct Bridge to mark task [ID] as done
2. Bridge fetches, updates status, pushes
3. Wait ~30s for Vercel redeploy
4. Open `overview.html` and verify task shows as done

**Pass criteria**:
- Task rendered with strikethrough and reduced opacity
- Status in file is `done`

---

## E2E-03 — Delete task full cycle

**Steps**:
1. Instruct Bridge to delete task [ID]
2. Bridge fetches, removes row, pushes
3. Wait ~30s for Vercel redeploy
4. Open `overview.html` and verify task is gone

**Pass criteria**:
- Task no longer appears in UI
- File format remains valid after deletion

---

## E2E-04 — Add calendar event full cycle

**Steps**:
1. Instruct Bridge to add calendar event via chat
2. Bridge fetches current `calendar.csv`
3. Bridge appends new row and pushes
4. Wait ~30s for Vercel redeploy
5. Open `overview.html` and verify event appears in Upcoming

**Pass criteria**:
- Event visible with correct date, time, title
- Sorted correctly by date

---

## E2E-05 — Roz logs activity

**Steps**:
1. Perform any Bridge operation
2. Check `logs/activity.md`

**Pass criteria**:
- Entry added with correct agent, action, target, result

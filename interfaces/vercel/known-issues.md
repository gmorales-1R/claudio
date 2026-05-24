# Known Issues — Vercel Interface

---

## KI-01 — Stale browser cache masks live deployments

**Status**: Active  
**Severity**: Low — cosmetic, no data loss  
**Discovered**: 2026-05-23  

### Description
Vercel deploys correctly on every push to `main` (confirmed via dashboard).
However, browsers — especially on mobile — aggressively cache static files.
This causes the old version of the page to appear even after a successful deploy,
making it seem like changes aren't working when they actually are.

### Symptoms
- Page looks unchanged after a confirmed Vercel deploy
- No errors visible (because the old page loads fine)
- Dashboard shows deployment as "Ready" but UI doesn't reflect it

### Current Resolution
Append a version query string to the URL to force a fresh load:
```
claudio-orcin.vercel.app/web/overview.html?v=2
```
Increment `v=N` each time you need to bust the cache.

### Limitations
- Manual and easy to forget
- Not reliable for team members who don't know the workaround

### Future Fix
When a proper backend is in place, implement cache-busting via:
- Asset versioning in HTML (`<script src="app.js?v=BUILD_HASH">`)
- Vercel cache headers configuration
- Service worker with explicit cache invalidation

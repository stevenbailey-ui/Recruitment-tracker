# Bring a Friend — Hackney RFC Girls Rugby Tracker

A single-page tool for tracking U11/U12 girls' recruitment prospects, built to satisfy the Bring a Friend tracker requirement in the Development Plan.

## What it is

- One file: `index.html`. No build step, no server, no dependencies.
- Data is stored **only in the browser it's used in** (localStorage) — nothing is sent anywhere.
- Uses **initials only** for both referrer and prospect, with a soft warning if you accidentally type something that looks like a full name.
- Tracks the funnel: Logged → Contacted → Invited → Attended → Joined, shown as live counts at the top.
- CSV export button for sharing a snapshot at committee meetings or with Steve.

## Hosting on GitHub Pages

1. Create a new GitHub repository (can be private or public — private is fine since GitHub Pages works on private repos with a paid plan; on a free personal account it will be public unless you're on GitHub Pro/Team/Enterprise).
2. Upload `index.html` to the root of the repo (or to a folder, e.g. `/tracker`).
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set Source to **Deploy from a branch**, branch `main`, folder `/ (root)` (or `/tracker` if you used a subfolder).
5. Save. GitHub will give you a URL like `https://<your-username>.github.io/<repo-name>/`.
6. Share that link with parents and coaches — it works on phone, tablet, or laptop.

## Important limitation to know about

**Data does not sync between devices or browsers.** Because this stores data in localStorage with no backend, each parent/coach using it on their own phone will see their own separate tracker, not a shared one.

This matches the "low-friction, parent-owned" design intent from the original tracker document, but it means:

- If you want one shared, club-wide view (e.g. for the Team Manager to see everyone's prospects), the **Team Manager should be the single person who enters all data**, using the WhatsApp/in-person updates from parents as the source.
- Alternatively, use the **Export CSV** button regularly and combine exports from multiple devices manually.
- If a genuinely shared, multi-device tracker becomes necessary later, that requires a small backend (e.g. Google Sheets via Apps Script, Firebase, or Supabase) — a meaningfully bigger build than this. Worth revisiting after the September–October trial period if single-owner entry proves too much of a bottleneck.

## Safeguarding note

Per the original tracker document, this tool deliberately:
- Never stores full names, only initials
- Never stores phone numbers, emails, or addresses
- Has no login, no account system, no external data transmission

Still worth a quick sign-off from Mary Impey (Safeguarding Lead) before parents start using it, consistent with the original recommendation.

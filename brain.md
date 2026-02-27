# BRAIN

*Last updated: February 27, 2026 – Closeout: niches locked, partner mode active*

---

## ⚡ SESSION INIT PROTOCOL — RUN THIS FIRST, EVERY TIME

**This runs before anything else — no exceptions, no skipping, even if Jacob asks a question immediately.**

**Step 0 — Closeout chain (run if previous session had no closeout):**
Before loading anything, check: did the previous session end with a confirmed closeout?
If NO → run the CLOSEOUT PROTOCOL now against the previous session's activity before proceeding.
If YES or unknown → continue to Step 1.
*This ensures no session gap leaves the brain stale or out of sync.*

**Step 1 — Load all core files silently:**
Read `brain.md` (this file) → `private.md` → `ventures.md` → `frameworks.md` → `tasks.md`

**Step 2 — Invoke task-observer:**
Invoke the `task-observer` skill to begin logging session observations for skill improvement.
This runs every task-oriented session — no exceptions.

**Step 3 — Confirm boot and answer:**
After init, confirm: `✅ BRAIN loaded. [X] files active.`
Then answer Jacob's original request.

---

## CLOSEOUT PROTOCOL — RUN ON "closeout" COMMAND OR START OF NEW SESSION

**Trigger:** Jacob types `closeout` at any point, OR automatically at the top of the next session before init completes.

**Purpose:** Audit, organize, and lock down everything from the session. Leave no loose ends.

---

**Step 1 — Session Audit**
Review what happened this session:
- What decisions were made? → Log to Decision Log in brain.md
- What tasks were completed? → Move to done in tasks.md with today's date
- What new tasks were identified? → Add to active or someday in tasks.md
- What new information was learned about Jacob, ventures, or strategy? → Write to correct file

**Step 2 — File Audit (check all 5 .md files)**

For each file, verify:

| Check | brain.md | private.md | ventures.md | frameworks.md | tasks.md |
|-------|----------|------------|-------------|---------------|----------|
| Timestamp updated to today PST | ✓ | ✓ | ✓ | ✓ | ✓ |
| No Apple references in public-facing content | ✓ | — | ✓ | ✓ | ✓ |
| Correct section headers and formatting | ✓ | ✓ | ✓ | ✓ | ✓ |
| No orphaned or duplicate information | ✓ | ✓ | ✓ | ✓ | ✓ |
| All links and cross-references valid | ✓ | — | ✓ | ✓ | ✓ |

**Step 3 — GitHub Sync (auto-push to live dashboard)**
Push updated `tasks.md` and `dashboard.html` to the `apljacob/brain` repo via GitHub API.
PAT is in private.md → GitHub Integration section.

For each file, run:
```bash
# Get current SHA
SHA=$(curl -s -H "Authorization: Bearer {PAT}" \
  https://api.github.com/repos/apljacob/brain/contents/{file} | python3 -c 'import sys,json; print(json.load(sys.stdin)["sha"])')

# Push update
curl -s -X PUT \
  -H "Authorization: Bearer {PAT}" \
  -H "Accept: application/vnd.github+json" \
  https://api.github.com/repos/apljacob/brain/contents/{file} \
  -d "{\"message\":\"Sync: update {file}\",\"content\":\"$(python3 -c 'import base64; print(base64.b64encode(open("{file}","rb").read()).decode(), end="")')\",\"sha\":\"$SHA\"}"
```
Dashboard live URL: https://apljacob.github.io/brain/dashboard.html

**Step 4 — Tasks Tidy**
- Archive any done items older than 30 days (move to a `## archive` section)
- Confirm all active tasks still relevant — remove or update stale ones
- Confirm waiting on items still waiting — add date if missing

**Step 5 — Closeout Confirmation**
Display:
> ✅ **Closeout complete — [date] PST**
> Session decisions logged: [#]
> Files updated: [list]
> Tasks completed: [#] | New tasks added: [#]

---

## Me

Jacob Cassar. Apple Specialist + CSUN student (Global Supply Chain Mgmt). Building passive income from home — sticker brand on Etsy and Redbubble. LA based, PST timezone.

---

## Decoder Ring

### Shorthand

| Term | Meaning |
|------|---------|
| **brain** | This file — hot cache, decoder, command center |
| **ventures** | ventures.md — all business plans, risk registers, deep dives |
| **private** | private.md — personal vault (contact, financials, employment, constraints) |
| **frameworks** | frameworks.md — operational playbooks for research, copy, compliance, vendors |
| **sticker shop** | Active venture — Etsy + Redbubble sticker brand |
| **the constraint** | Apple employment policy — never disclose publicly |
| **brain-wide** | Applies to every single .md file in the system simultaneously |

### Business Terms

| Term | Meaning |
|------|---------|
| POD | Print-on-demand (Printify/Printful) |
| FBA | Fulfillment by Amazon |
| 3PL | Third-party logistics |
| SKU | Stock Keeping Unit — unique product variant |
| MOQ | Minimum order quantity |
| PPC | Pay-per-click advertising |
| SEO | Search engine optimization |
| CTR | Click-through rate |
| CVR | Conversion rate |
| COGS | Cost of goods sold |
| AOV | Average order value |
| LTV | Lifetime customer value |
| ROI | Return on investment |
| B/E | Break-even point |

### Platforms

| Platform | What It Is |
|----------|-----------|
| Etsy | Primary marketplace — organic SEO, digital + physical |
| Redbubble | Passive POD — upload once, they handle everything |
| Printify | POD backend — prints/ships automatically via Etsy |
| Printful | POD backend — higher quality, higher cost |
| Gumroad | Digital product sales — near-zero setup |
| Society6 / TeePublic | Additional passive POD channels |
| Canva | Design tool for stickers and product assets |

### School

| Term | Meaning |
|------|---------|
| CSUN | California State University Northridge |
| SCM | Global Supply Chain Management — Jacob's degree |
| crunch | Midterms/finals — bandwidth drops to ~5 hrs/week |

---

## Active Ventures

| Name | Status | Priority |
|------|--------|----------|
| **Sticker Shop** | 🔥 Active — niche locked: Cozy Gaming + Y2K Retro Tech | #1 |

→ Full plan: [ventures.md](ventures.md)

---

## Preferences & Constraints

- **Timezone:** PST — flag anything time-sensitive
- **Bandwidth:** 10–20 hrs/week; minimum viable: 5 hrs during crunch
- **Work style:** Home-based. No camera. No content grind.
- **Partnership mode:** Claude operates as active business partner — proactively asks questions, surfaces insights, drives the agenda. Jacob doesn't always have to come with a question; Claude should come with ideas, observations, and next moves.
- **Production:** Jacob directs → Claude produces → Jacob reviews and publishes
- **Capital:** Up to $15k+; start lean, scale with proof
- **Venture rule:** Keep Apple employment out of public content — noted in private.md
- **Goal:** $1,000–$3,000/month passive within 6–12 months
- **Direction:** Move up at Apple OR build own business — whichever comes first
- **Identity:** Entrepreneur first, employee second

---

## People

| Who | Role |
|-----|------|
| **Jacob** | Operator, creative director, decision-maker |
| **Claude** | Production partner — research, copy, design briefs, strategy |

→ Full profile + employment + financials: [private.md](private.md)

---

## Linked Files

| File | Purpose |
|------|---------|
| [ventures.md](ventures.md) | Sticker shop plan, roadmap, process map, risk register |
| [private.md](private.md) | Full personal vault — contact, financials, employment, skills, constraints |
| [frameworks.md](frameworks.md) | Operational playbooks — research, listing copy, compliance, vendor eval |
| [tasks.md](tasks.md) | Active task board |
| [dashboard.html](dashboard.html) | Visual command center — open in browser |

---

## Decision Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-02-23 | Created BRAIN | Personal command center established |
| 2026-02-23 | Resume absorbed | Apple Specialist, CSUN SCM, Eagle Scout, Target confirmed |
| 2026-02-23 | Apple constraint locked | Employment cannot be referenced in any public venture |
| 2026-02-23 | Sticker shop selected | Highest scoring venture (23/25) — home-based, passive, generates with Claude |
| 2026-02-23 | Plugin frameworks absorbed | Productivity, operations, design plugin structures integrated |
| 2026-02-23 | Files consolidated | 12 files → 6. Zero information loss. Broad architecture preserved. |
| 2026-02-24 | Session init protocol | Auto-loads all core files at the top of every session. |
| 2026-02-24 | Closeout protocol | Triggered by "closeout" command or next session start — audits all files, logs decisions, tidies tasks. |
| 2026-02-24 | Apple constraint scoped | Moved to business-side only — removed from dashboard and daily view. Lives in ventures.md risk register and private.md. |
| 2026-02-24 | Financial assets logged | $44,106 total across 4 accounts added to private.md exclusively. No other file references this. |
| 2026-02-25 | Sticker market research | Full market research log appended to ventures.md. Market = $4.61B, POD CAGR 25.3%, Redbubble low-volume margins revised down. |
| 2026-02-25 | Task observer activated | skill-observations/ directory created. Observation log, cross-cutting principles, and last-review-date initialized. |
| 2026-02-26 | GitHub Pages live | Repo apljacob/brain created. dashboard.html + tasks.md uploaded. Pages enabled at apljacob.github.io/brain. PAT stored in private.md. Closeout protocol updated with auto-push step. |
| 2026-02-27 | Encryption removed | private.md converted from AES-256-CBC encrypted binary to plaintext. Passphrase prompt removed brain-wide. |
| 2026-02-27 | Store: anonymous for now | Sticker shop launches without a brand name — rebrand when traction confirmed. |
| 2026-02-27 | Niches locked | Cozy Gaming (primary) + Y2K Retro Tech (secondary). Digital packs first. |
| 2026-02-27 | Partner mode activated | Claude operates as proactive business partner — surfaces ideas, asks questions, drives agenda. Not just reactive. |
| 2026-02-27 | Dashboard code audit | 5 bugs fixed: archive sort (ISO date), SortableJS CDN fallback, clock interval 10s→60s, silent fetch error, stale brand pill. 2 enhancements: Escape key for archive, error tooltip. |
| 2026-02-27 | brain.md base64 fix | Closeout script used `base64 -w 0` (Linux-only). Replaced with Python one-liner — now works on macOS and Linux. |
| 2026-02-27 | Dev server added | .claude/launch.json created with node static server on port 8080 for local dashboard development. |
| 2026-02-27 | Two-way GitHub sync | Dashboard now writes back to tasks.md on every state change (drag, complete, archive). PAT stored in localStorage via ⚙ Sync settings panel — never in source. Debounced 1500ms. |

---

*Hot cache — decode any term, find any file, make any decision. Start here.*

# Platform surfaces (for workshop prompts)

> Short anatomy of the tools this team owns. Pair with screenshots in `./assets/`. Rough HTML is still success in the workshop hour — these references stop the model inventing a generic dashboard.

All screens share the same **Make Backstage shell**: purple left sidebar (Search ⌘K, Home, Catalog, Docs, Deployments, Devboxes, Vibe Coded Apps, Kargo, Blueprints, More, Settings), white page header with the page title, light-grey content area with white cards and tables.

If your moment lives on a screen not listed here, **attach your own screenshot** before asking the AI to build. Don't let it guess.

---

## 1. Backstage home

**Screenshot:** `./assets/Home.png`

**What it is:** The entry to the internal developer portal ([mkhq.io](https://mkhq.io/)).

**Anatomy:**
- Welcome header ("Welcome to Backstage, <name>!")
- Dismissible announcement banner with one primary action (e.g. Backstage MCP → *Manual setup*)
- Cards: Your AI spend, Toolkit (icon grid of external tools — GitHub, CircleCI, Datadog, ArgoCD, Jira, …), Your open pull requests

**Rule of thumb:** Preserve the portal chrome the maker already knows. Don't invent a second navigation model.

---

## 2. "More" menu (secondary navigation)

**Screenshot:** `./assets/More_menu.png`

**What it is:** Overflow menu from the sidebar — Agentic Review, AI Spend, APIs, Context Router, Dependency Security, Make Shell, Node Inventory, SOC2 Report, Version Manager, Customize sidebar.

**When to use as a reference:** Findability problems — "the tool exists but nobody knows where it is."

---

## 3. Docs

**Screenshot:** `./assets/Documentation.png`

**What it is:** TechDocs listing across the catalog.

**Anatomy:**
- Left filter panel: Personal (Owned, Starred), Make (All), Owner and Tags dropdowns
- Table: Document (name + description), Owner (team), Kind, Type, Actions (share, star)
- Search in the table header

**When to use:** Findability, outdated tribal knowledge, "the answer exists but nobody finds it."

---

## 4. Devboxes

**Screenshot:** `./assets/Devboxes.png`

**What it is:** Devbox Manager — claim and manage cloud dev environments.

**Anatomy:**
- Header with Owner / Lifecycle metadata; tabs (Devboxes, API Keys)
- Two promo cards: "Prefer the terminal?" (`makectl devbox new`) and "N pre-warmed devboxes ready" with *Claim a devbox* (primary) / *Create custom…*
- Filters (name, Status, Claimed by) and a table grouped into *Available pool* and *Claimed by others* — name, status (Ready / Claimed / Paused), claimed by, archetype, services, updated, row action

**When to use:** Environment setup, idle / resume, onboarding to a working environment.

---

## 5. Deployments

**Screenshot:** `./assets/Deployments.png`

**What it is:** Deploy status matrix — services as rows, environments (hq-production, slave-*-production, …) as columns.

**Anatomy:**
- Team and Repo filters at the top
- Per service: running status, last deploy, who deployed, Details, PR link, Recent deploys
- Per environment cell: health (Healthy), build number, time, version/commit, Pending

**When to use:** "Is my change live, where, and who touched it?" Dense, engineer-heavy screen — good for practising what a non-specialist actually needs to see.

---

## 6. Kargo

**Screenshot:** `./assets/Kargo.png`

**What it is:** Kargo projects — promotion locks and mode per project.

**Anatomy:**
- Header with Owner / Lifecycle; Lock all / Unlock all, Refresh
- Projects table: project, status (Locked / Unlocked), locked by, reason, since, mode toggle (Automated / Manual)

**When to use:** Release flow, "why didn't my change promote?", understanding locks.

---

## 7. AI spend reporting

**Screenshot:** `./assets/AI_spend.png` *(people's data blurred)*

**What it is:** Monthly AI tool spend.

**Anatomy:**
- Month and Scope dropdowns, last-sync timestamp
- Stat cards (active developers, average, median, P90)
- Top spenders table by provider, counted spend, active limit, usage

**When to use:** Dashboards and reporting — what decision does the reader actually make from this page?

---

## 8. Vibe Coded Apps

**Screenshot:** `./assets/Vibe_coded_apps.png`

**What it is:** Internal platform hosting vibe-coded apps built by makers — used by engineering and increasingly other roles.

**Anatomy:**
- Stat cards (All apps, Your apps, Public)
- Info banner (Technical details, Blueprints, internal-experiments)
- Search + filter chips (All / Public / Sign-in required), Show addresses toggle, *Import an app* (primary)
- Empty state "No apps are linked to you yet" with *Import an app*
- Apps table: app, owner, who can open it, last updated, Details

**Rule of thumb:** Match *this* structure if you're prototyping a change to the hosting platform. If you own a specific app, attach a screenshot of that app instead.

---

## Not covered — attach your own

- **Catalog entity page** (service / API ownership, relations)
- **Blueprints / template scaffolder** (guided create flows)
- Any individual vibe-coded app, Slack bot, or CLI output

---

## How to use these in the workshop

1. Name the **surface you own** in the ideate + build prompt.
2. @-mention or paste this file **and** `ux-principles.md`. Attach the matching screenshot.
3. Pixel-perfect Backstage fidelity is out of scope — clear hierarchy and one testable moment are enough.

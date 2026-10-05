# Platform context (for workshop prompts)

> Paste or @-mention this file with the discovery, define, and ideate+build prompts. One page. Not a design-system spec.

For universal UI/UX principles see `ux-principles.md`. For screen anatomy and screenshots see `platform-surfaces.md`.

---

## What the platform team builds

Internal tools that help **makers** get their work done at Make — not the Make product itself.

Primary surfaces include:

- **Make Backstage** ([mkhq.io](https://mkhq.io/)) — internal developer portal built on [Backstage](https://backstage.io/). Templates, docs, service catalog, and related workflows. Uses the open-source Backstage / Spotify design system, not Make's product design system.
- **Vibe-coded apps** — lightweight internal apps surfaced through / alongside Backstage. Used by engineering and increasingly by other roles.
- **The wider tooling stack** — anything in the DX / engineering-productivity surface (dev environments, docs discovery, release helpers, ask-channel tooling, future cloud agent environments, etc.).

When building a prototype today, match the *tool the participant actually owns*. Rough HTML that shows one moment is enough. Pixel-perfect Backstage fidelity is out of scope for the workshop hour.

---

## Who the users are

**All makers** — not only engineers.

| Role (examples) | What they often come to the platform to do |
|---|---|
| Software engineer | Find a service, spin up an environment, follow a template, ship a change, answer an #ask ping |
| Engineering manager / tech lead | See ownership, unblock a team, understand friction from DX signal |
| Designer | Try an internal app or template; find docs; sometimes hit walls built for engineer mental models |
| Other makers (PM, research, ops, …) | Same portal and apps, with less tribal knowledge of how engineering tools are supposed to work |

Name a real role and a concrete job: e.g. *"a designer trying to open a vibe-coded app to try a flow"* or *"an engineer joining a new repo who needs a working environment without Slack archaeology."*

---

## Evidence this team already has

| Source | What it's good for |
|---|---|
| **Quarterly DX survey comments** | Verbatim friction in makers' own words. Already collected; often left as comments instead of turned into briefs. |
| **Conversations / Slack pings** | Real moments someone got stuck. Treat as interview notes — who, what they tried, where it broke. |
| **Usage / analytics** | Where people drop off, which templates are unused, idle rates, time-to-first-success. |
| **Engineering strategy metrics** | DXI (48 Oct 2025 → 56 Feb 2026 → 67 Sep 2026; target 69), reliability, idea-to-customer. Use only when the success sentence truly maps — don't force it. |
| **Comparable tools / workarounds** | How people cope today (tribal docs, asking in Slack, copying a teammate's setup, using a different portal). |
| **Confluence / Jira** | Existing write-ups, known issues, requests that already live as tickets — when the tool can reach them. |

---

## What makers are already saying (public Slack, Jul–Oct 2026)

A quick scan of #ask-devprod, #ask-internal-vibe-coding-platform, #make-engineering-all, #ai-tooling-guild and similar channels. People anonymized to roles. Counts are threads seen in ~25 searches — a floor, not a census. **Use as evidence for your hypothesis; don't quote it as if it were research.**

| Surface | Signal | Who | What it sounds like |
|---|---|---|---|
| **Vibe Coded Apps** | ~8 friction threads in 3 months; nearly every one needed a platform engineer to answer by hand | PMs, designers, recruiting, marketing/GTM, Celonis colleagues | No way to discover what apps exist or who owns them (the page is a management view). "Public" vs "no login" confusing. Imports 12–40 min. Env vars wiped with no alert. No honest usage numbers. |
| **Docs / Catalog / templates** | ~5 "can't find / can't access / broken link" threads; 3 people in 2 months asked which template to use for a new service | New-to-repo engineers, designers/PMs, service authors | Sign-in with two accounts hides most of Backstage. Linked guide broken (35-reply thread). Blueprint README points at templates that don't exist. Docs published but not in the nav. |
| **Devbox / makectl / local setup** | ~8 threads; DX survey names dev environment the #1 improvement priority | Backend + frontend engineers, designers, PMs, new joiners | Version mismatches, binary killed on Mac, out-of-memory, missing DB extension. A separate local-setup workshop was run for non-engineers because the setup skill "is not good enough". |
| **Kargo / deployments** | ~6 "is it broken or is it me?" threads in Sep–Oct | Backend engineers, service owners | Stuck refreshing (2 people in 10 days, one spamming refresh). Same service in Kargo *and* Argo Workflows — which is real? Unexpected Manual mode with an old version in prod. |
| **Backstage MCP / AI spend** | Daily re-auth thread got 6 "+1" — the strongest "me too" seen; still reproducing 2 weeks after a fix | Engineers, engineering managers | "Is it just me?" logouts. MCP apps blocked as bot traffic for 2 days. Confusion over a shared AI budget across tools and empty spend rows. |
| **#ask-devprod as an approval queue** | Dozens of "please review my small PR" posts; "no response for over an hour" bot fired in 3+ threads | Nearly every engineering team | People don't know whose approval they need; some PRs never needed DevProd at all. |

**Positive signals:** DXI up 19 points in a year. Ease of release +19 in 3 months (credited to Kargo). Cursor CSAT 92, Claude Code 87. Backstage MCP and the homepage AI spend widget praised. Make Review called "actually useful, not just noise".

**The pattern:** the audience grew from engineers to all makers, and a lot of the friction never reaches a ticket — it lives in Slack threads answered one at a time.

---

## How to think about a platform problem

1. **Name the maker and the job** — who, trying to accomplish what, at which moment.
2. **Name the friction and its cause** — what gets in the way, and why (missing info, wrong mental model, broken step, tribal knowledge, role mismatch).
3. **Stay out of solutions** until those are written.
4. When exploring solutions, vary **when you intervene** (before / during / after the friction) and **who does the work** (the maker vs the system vs a teammate).
5. **One success signal** — *"We'd know this worked if [a maker did this]."* Optionally tie to a DX driver or DXI when it honestly fits.

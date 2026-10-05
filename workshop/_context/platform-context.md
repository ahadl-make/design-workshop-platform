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
| **Engineering strategy metrics** | DXI (target 69), reliability, idea-to-customer. Use only when the success sentence truly maps — don't force it. |
| **Comparable tools / workarounds** | How people cope today (tribal docs, asking in Slack, copying a teammate's setup, using a different portal). |
| **Confluence / Jira** | Existing write-ups, known issues, requests that already live as tickets — when the tool can reach them. |

---

## How to think about a platform problem

1. **Name the maker and the job** — who, trying to accomplish what, at which moment.
2. **Name the friction and its cause** — what gets in the way, and why (missing info, wrong mental model, broken step, tribal knowledge, role mismatch).
3. **Stay out of solutions** until those are written.
4. When exploring solutions, vary **when you intervene** (before / during / after the friction) and **who does the work** (the maker vs the system vs a teammate).
5. **One success signal** — *"We'd know this worked if [a maker did this]."* Optionally tie to a DX driver or DXI when it honestly fits.

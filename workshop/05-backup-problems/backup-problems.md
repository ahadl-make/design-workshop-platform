# Backup problems (anonymized)

> Use if someone arrives without an idea. Names and teams stripped. Drawn from real DX survey themes (Sept 2026) plus one non-engineer case from the platform team's expanding audience.
> **Do not** put the raw DX CSV in the participant pack.

Pick one. Treat it as your starting idea — then run the discovery prompt on it.

---

## 1. Docs are still tribal, even with Backstage

Makers say documentation is scattered across GitHub, Confluence, and people's heads. Backstage helped, but finding how things relate — especially for newer people or AI agents that need context — is still hard. Stale and AI-generated docs that nobody reads make it worse.

**Starter idea (solution-shaped, on purpose):** "We should add better docs pages in Backstage."

---

## 2. First-time environment setup still needs Slack

Getting a local or cloud environment running still depends on tribal knowledge: missing README steps, Docker vs host confusion, env vars, ports. People re-setup machines multiple times. Newer shared tools (e.g. devboxes) help some teams and leave others unsure what the end goal even is.

**Starter idea:** "We should improve the onboarding guide for local setup."

---

## 3. Dev environments go idle or take too long to resume

People who rely on cloud-ish environments lose flow when the environment idles too fast or takes a long time to come back. Resuming breaks concentration more than the original wait.

**Starter idea:** "We should change the idle timeout."

---

## 4. Infra and platform tools are poorly documented

Argo CD, devboxes, and similar infra surfaces are called out as hard to learn. Makers can run day-to-day work but bounce when they need to understand or change the underlying tooling.

**Starter idea:** "We should write an infra wiki."

---

## 5. Non-engineers hit walls in tools built for engineers

Designers (and other non-engineering makers) try to use vibe-coded apps / Backstage surfaces that were promised as more widely usable. They get stuck — mental models, permissions, jargon, or flows that assume an engineer. The portal is expanding beyond engineering; the experience often hasn't.

**Starter idea:** "We should make Backstage friendlier for non-engineers."

---

## How to use these

1. Pick the one closest to something you've seen.
2. Paste the **starter idea** into the discovery prompt (solution-shaped is fine — the prompt will push you back to the person and the job).
3. If you have a DX comment or a real story that matches, add it as evidence in the prompt.

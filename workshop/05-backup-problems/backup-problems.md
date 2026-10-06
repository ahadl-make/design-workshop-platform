# Backup problems (anonymized)

> Use if someone arrives without an idea. Names and teams stripped. 1–5 are drawn from real DX survey themes (Sept 2026); 6–13 from public Slack threads (Jul–Oct 2026) summarised in `_context/platform-context.md` → *What makers are already saying*.
> **Do not** put the raw DX CSV in the participant pack.

Pick one. Treat it as your starting idea — then run the discovery prompt on it.

---

# From the DX survey

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

# From Slack (Jul–Oct 2026)

## 6. Nobody can find what vibe-coded apps exist

PMs, designers, recruiting and marketing hear about an internal app and can't find it. The Vibe Coded Apps page is built for managing your own apps, not for discovering other people's — no way to see what exists or who owns it. Nearly every thread needed a platform engineer to answer by hand.

**Starter idea:** "We should add search to the Vibe Coded Apps page."

---

## 7. Hosting a vibe-coded app is full of silent surprises

Makers who host an app hit things nobody warned them about: imports take 12–40 minutes, environment variables get wiped with no alert, "Public" vs "no login" is confusing, and there are no honest usage numbers. Each surprise turns into a Slack thread a platform engineer answers by hand.

**Starter idea:** "We should send an email when env vars change."

---

## 8. "Which template do I use for a new service?"

Three people in two months asked this in Slack. The Blueprint README points at templates that don't exist, and some docs are published but not in the nav.

**Starter idea:** "We should clean up the Blueprints list."

---

## 9. Signed in with the wrong account, Backstage looks half-empty

Signing in with one of two accounts hides most of Backstage. New-to-repo engineers, designers and PMs conclude a page or guide doesn't exist — or that they lack access — and ask in Slack. One broken-guide thread ran to 35 replies.

**Starter idea:** "We should remove the second sign-in option."

---

## 10. "Is Kargo broken, or is it me?"

Backend engineers and service owners can't tell whether their release is stuck or still working: Kargo sits refreshing (one person kept hitting refresh), the same service shows up in both Kargo and Argo Workflows, and a project can be unexpectedly in Manual mode with an old version in prod. ~6 threads in Sep–Oct.

**Starter idea:** "We should add a status page for Kargo."

---

## 11. Logged out every day, and nobody knows if it's just them

Engineers and engineering managers using Backstage MCP get asked to re-authenticate daily. The thread collected six "+1"s — the strongest "me too" in the scan — and was still reproducing two weeks after a fix. Each person first assumes it's their own setup.

**Starter idea:** "We should make the login session last longer."

---

## 12. #ask-devprod has become an approval queue

Dozens of "please review my small PR" posts; the "no response for over an hour" bot fired in several threads. People don't know whose approval they actually need — and some PRs never needed DevProd at all.

**Starter idea:** "We should add an SLA bot to #ask-devprod."

---

## 13. Nobody understands the shared AI budget

Engineers and engineering managers are confused that one AI budget is shared across several tools, and some rows in AI spend reporting are empty. (The homepage AI spend widget itself is praised.)

**Starter idea:** "We should add a per-tool breakdown to AI spend."

---

## How to use these

1. Pick the one closest to something you've seen.
2. Paste the **starter idea** into the discovery prompt. For 6–13, the matching row in `platform-context.md` is already there as evidence — the AI can draw on it.
   (Solution-shaped is fine — the prompt will push you back to the person and the job.)
3. If you have a DX comment or a real story that matches, add it as evidence in the prompt.

# Define Prompt Template

Copy the prompt below into your AI tool and paste your discovery summary. **Include platform context** using [How to include platform context](#how-to-include-platform-context).

This step turns the evidence into **a defined problem**: ask why until you reach the cause, write the needs hypothesis, then decide what the design must achieve. No layouts, concepts, or code.

---

## The Prompt

```
You are a senior product designer helping a platform engineer at Make. I build internal tools (Backstage, vibe-coded apps, DX tooling) for makers across the company — engineers and other roles.

The platform context is provided alongside this prompt (workshop/_context/platform-context.md). Read it.

Your job is to help me define the problem before we think about solutions. No UI ideas, layouts, or code — that comes in the next exercise.

---

**My starting idea:**
[PASTE]

**What discovery found:**
[PASTE the whole evidence summary from Exercise 1]

---

Work through three steps. Ask one question at a time.

1. **Ask me "why" questions** to get from my idea to the cause behind it. Two or three is enough — stop once we reach something a platform change could actually touch. Ground your questions in the evidence ("Discovery found PMs asking in Slack who owns an app — why do they end up asking?"). Don't just accept my first answer. I'm a backend-minded engineer: if I drift into how the system works internally, pull me back to what the person experiences. If the evidence and my idea point different ways, say so.

2. **Write the needs hypothesis with me:**
   - We think [ROLE] struggles with [PROBLEM] because [ROOT CAUSE].
   - They need [OUTCOME] without [CURRENT FRICTION].
   A specific role, not "users". The root cause can be technical, but the need must be written from the person's moment — what they see, wait for, or can't do — not from the system's point of view. Keep it about what they need, not what we should build.

3. **Land three lines:**
   - **Goal** — what this person gets done when it works, in their words. An outcome, not a feature ("get a working environment without asking in Slack", not "build a setup wizard").
   - **Success** — "We'd know this worked if [a maker did this]." Something you could actually watch someone do — it becomes the task for a pair test later. Not a system metric (latency, uptime) — what the maker does differently.
   - **The moment to prototype** — the single moment in their journey we most need to try out with a real person. One sentence.

If my hypothesis is treating a symptom rather than the cause, say so. If one of my lines sounds like a feature, ask me: "So they can do what?"

Be conversational and keep it short — we have about 15 minutes. Propose drafts, ask me what to tighten, and stop once I confirm. Do not ideate or build.

Start by asking me your first "why" question.
```

---

## How to include platform context

| Tool | What to do |
|------|------------|
| **Cursor** | `@`-mention `workshop/_context/platform-context.md` with the prompt. |
| **Claude Code** | Ask Claude to read `workshop/_context/platform-context.md`, then paste the prompt. |
| **Claude chat (claude.ai)** | Attach [`platform-context.md`](../_context/platform-context.md) to the same message as the prompt. |

Same chat as discovery is fine — then you don't need to re-paste the summary.

---

## How to use this

1. Copy your starting idea and the evidence summary from Exercise 1.
2. Copy the prompt and paste them in.
3. Include `platform-context.md`.
4. Answer the whys honestly. Confirm the hypothesis, then the three lines. Save them to `my-outputs/2-define.md`.
5. If the AI starts proposing screens or features — stop it: *"Stay in define. No solutions yet."*

---

## Expected output

```
We think [ROLE] struggles with [PROBLEM] because [ROOT CAUSE].
They need [OUTCOME] without [CURRENT FRICTION].

Goal: …
Success: We'd know this worked if [a maker did this].
Moment to prototype: …
```

Then move to **Exercise 3: Ideate + Prototype**.

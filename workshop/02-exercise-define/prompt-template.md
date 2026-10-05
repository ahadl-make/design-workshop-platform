# Define Prompt Template

Copy the prompt below into your AI tool and paste your hypothesis. **Include platform context** using [How to include platform context](#how-to-include-platform-context).

This step decides **what the design must achieve**. No layouts, concepts, or code.

---

## The Prompt

```
You are a senior product designer helping a platform engineer at Make. I build internal tools (Backstage, vibe-coded apps, DX tooling) for makers across the company — engineers and other roles.

The platform context is provided alongside this prompt (workshop/_context/platform-context.md). Read it.

Your job is to help me decide what a design must achieve before we think about solutions. No UI ideas, layouts, or code — that comes in the next exercise.

---

**My needs hypothesis (from discovery):**
[PASTE: "We think [ROLE] struggles with [PROBLEM] because [ROOT CAUSE]. They need [OUTCOME] without [CURRENT FRICTION]."]

---

Help me land three lines:

1. **Goal** — what this person gets done when it works, in their words. An outcome, not a feature ("get a working environment without asking in Slack", not "build a setup wizard").

2. **Success** — "We'd know this worked if [a maker did this]." Something you could actually watch someone do — it becomes the task for a pair test later. Not a system metric (latency, uptime) — what the maker does differently.

3. **The moment to prototype** — the single moment in their journey we most need to try out with a real person. One sentence.

If my hypothesis is treating a symptom rather than the cause, say so before we write anything. If one of my lines sounds like a feature, ask me: "So they can do what?"

Be conversational and keep it short — we have about 15 minutes. Propose a first draft of the three lines, ask me what to tighten, and stop once I confirm. Do not ideate or build.
```

---

## How to include platform context

| Tool | What to do |
|------|------------|
| **Cursor** | `@`-mention `workshop/_context/platform-context.md` with the prompt. |
| **Claude Code** | Ask Claude to read `workshop/_context/platform-context.md`, then paste the prompt. |
| **V0 / ChatGPT / other** | Paste the full contents of [`platform-context.md`](../_context/platform-context.md) **above** the prompt. |

---

## How to use this

1. Copy your needs hypothesis from Exercise 1.
2. Copy the prompt and paste the hypothesis in.
3. Include `platform-context.md`.
4. Confirm the three lines before moving on.
5. If the AI starts proposing screens or features — stop it: *"Stay in define. No solutions yet."*

---

## Expected output

```
Goal: …
Success: We'd know this worked if [a maker did this].
Moment to prototype: …
```

Then move to **Exercise 3: Ideate + Prototype**.

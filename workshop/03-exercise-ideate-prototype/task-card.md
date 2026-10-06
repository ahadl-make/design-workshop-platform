# Exercise 3: Ideation + Prototyping
**Time:** 55 minutes  
**Goal:** Explore directions with an AI design buddy — then build one rough moment

---

## What You'll Do

One continuous conversation with an AI acting as your design buddy:

1. **Think together** — explore directions, pick one, agree on a plan. No code yet.
2. **Build together** — once you've approved the plan, the AI builds a rough prototype with you.

**The thinking is the work.** Don't rush to the prototype. Rough HTML is success — Backstage visual fidelity is out of scope.

**Use the design system.** You build with **Backstage UI (BUI)** — real Backstage components in Make purple. The AI starts from `_context/bui-starter.html` and uses only components from `_context/bui.md`. Don't invent, re-use.

**Design the seats, not the engine.** Directions are described as what the maker sees and does — not services, caches, or pipelines. Everything behind the screen is faked: hardcoded data, no real APIs.

---

## Your Input

- Your **needs hypothesis** from Exercise 1
- Your **three define lines** from Exercise 2: goal, success, moment to prototype
- The **tool or surface you own** (e.g. Backstage docs, Devboxes, a vibe-coded app) — attach the matching screenshot from `_context/assets/` or your own

---

## The Phases

### Phase 1: Explore directions (~15 min)
2–3 genuinely different directions — earlier vs. at the moment, tool vs. maker vs. teammate, or a better version of what people do today. A Slack message or CLI output counts as a prototype too. Pick one.

### Phase 2: Build plan (~5 min)
What you'll build, what the maker does, states, what's left out, what's faked. Cut until it fits ~30 minutes.

### Phase 3: Build (~30 min)
Rough, clear, interactive enough to try the one moment. Leave ~5 min to make sure it opens.

---

## How to Use the Prompt

1. Open your AI tool
2. Copy the prompt from `prompt-template.md`
3. Paste your hypothesis + define lines; name your tool
4. Include `platform-context.md`, `ux-principles.md`, `platform-surfaces.md`, `bui.md`, `bui-starter.html` + your screenshot — see `prompt-template.md`
5. Start the conversation

---

## If the AI Jumps to Code Early

> *"Stop — we haven't agreed on a direction yet. Go back to Phase 1. No code until I approve the plan."*

---

## If You're Stuck

**"I don't know which direction to pick"**  
→ Ask: *"Which one best fits what this maker is trying to get done, with the least to learn?"*

**"The plan is too complex"**  
→ *"What's the simplest version that shows the one moment?"*

**"I keep thinking about how to build it"**  
→ *"That's the engine. What does the maker see on screen at this moment?"*

**"I'm running out of time"**  
→ Keep the chosen direction. Walking someone through it still works for pair testing.

---

## Output

- ✅ A chosen direction
- ✅ A rough prototype (or at least the direction in words)

---

## Next Step

Move to **Exercise 4: Pair Testing + Improve**.

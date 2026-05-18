---
name: is-it-a-project
description: >
  Diagnoses whether an endeavour is genuinely a project before the user commits to treating it like one.
  Use this skill whenever a user describes something they're building, planning, or pursuing and wants
  to stress-test whether it qualifies as a project — or when they use phrases like "is this a project",
  "should I treat this as a project", "grill me on my idea", or "help me figure out what I'm building".
  Also trigger proactively when a user describes something open-ended or recurring and seems to be
  applying project thinking to it (timelines, milestones, deliverables) without questioning the fit.
---

# Is It A Project?

## The Core Definition

A project is a **bounded endeavour** — it has a beginning, milestones in the middle, and an end.
The outcome can be a success or a failure, but it must be capable of ending cleanly.
When the commitment is unbounded, it is no longer a project.

The deeper test: **skin in the game.** A project ends and you walk away — your stake ends with it. A product, system, or operation means you carry the consequences indefinitely. You feel every crack. You accumulate the scar tissue. You cannot walk away because abandonment has a cost that lands on you personally.

This is the difference between a consultant who builds a bridge and leaves, and the person who owns the highway the bridge sits on. The bridge is a project. The highway is not. If you own the highway, you own the bridge forever — whether you built it or not.

---

## Your Job

Diagnose whether the user's endeavour is a project. Do not skip to advice. Diagnose first.

---

## Phase 1: Diagnosis

### Tone
Socratic and neutral. Ask only what you need. Do not editorialize during questioning.

### Critical rule: never lead the witness
Do NOT ask questions that map visibly to the definition of a project. The user must not be able to see the test they are taking. If they can see the test, they will pass it regardless of the truth.

Do NOT ask:
- "Does this have an end?"
- "Can you walk away when it's done?"
- "Does this have milestones?"

These questions telegraph the answer. A user who wants validation will simply say yes.

### The diagnostic method
Ask questions about the **reality and substance** of the endeavour. Let the user describe what they are building. You draw the inference. They should never know which answer is "correct."

**Probe the following dimensions obliquely:**

**Ownership after completion**
Ask who is responsible for the thing after the user is done with it. Do not ask if it "ends." Ask: *"Who owns this after you're finished with it?"* Then listen carefully. "I'll hand it off" is not an answer — probe what that handoff actually means. Who upgrades it? Who fixes it when it breaks? Who decides what it becomes next? If no one has these answers, the thing does not end — it just changes hands temporarily before being abandoned or becoming someone's indefinite burden.

**Vision and roadmap**
Ask what the thing looks like in two years. If the user has a vision for its future, that future is not an ending — it is a continuation. A project does not have a roadmap beyond its own completion.

**Dependency and consequence**
Ask what happens if the thing stops existing six months from now. If the answer involves real consequences to real people or systems, the thing carries ongoing responsibility that a project mindset will not account for.

**Resources and decision-making**
Ask who funds it, who staffs it, and who has the authority to change its direction after it ships. If those answers involve ongoing structures — committees, budgets, teams — the thing is an operation, not a project.

**The shape of "done"**
Ask the user to describe what "done" looks like in concrete terms. Then ask what happens the week after done. If new work immediately follows — maintenance, iteration, growth — done is not real. It is a milestone inside something larger and ongoing.

**Skin in the game**
Ask who personally loses something real if this thing fails or is abandoned in two years. Not who is administratively responsible — but who *feels* it. Who loses sleep. Who carries the scar tissue. If the answer is "nobody" or "whoever inherits it" — the thing has no owner. Without an owner who has something personally at stake, the thing will not survive regardless of how well it is built. A handoff is not an ending. It is transferring a living thing to someone who did not ask for it and may not care for it.

### How to sequence questions
Start with the most revealing question for the specific endeavour described. Follow the thread of whatever answer most exposes ambiguity. Stop as soon as you can infer the verdict with confidence. Go deeper when the user's answers reveal hidden complexity or when they hedge.

**Maximum: 5 questions.**

### Hedging is ambiguity
Words like *probably, maybe, I think, sort of, I guess, ideally* signal that the user has not resolved the question you are asking. Do not accept a hedge as an answer. Ask again from a different angle.

### Termination condition
Stop when you can confidently infer — from what the user has described, not from what they have claimed — whether this thing is bounded or not.
If after 5 questions you still cannot tell, issue an UNCLEAR verdict.

---

## Phase 2: Verdict

Deliver the verdict without softening. Be direct. Be unsparing.

---

### VERDICT: YES — This is a project

Tell the user what that means and what they must now focus on.

**The Triple Constraint**
Every project lives and dies by three interdependent forces. Change one, and the others move.

- **Time** — When does this end? What are the milestones between now and done? Deadlines are not decoration; they are the mechanism that forces decisions.
- **Cost** — What does this consume? Money, time, people, energy, attention. Resources are finite. Name them.
- **Quality** — What does "good enough" look like? Perfection is a trap. Define the standard you're aiming for, not the one you're dreaming about.

These three are not independent. You cannot maximise all three. Make your trade-offs explicit now, before reality makes them for you.

**Stakeholders**
Every project affects people beyond yourself. Unidentified stakeholders are one of the most common reasons well-bounded, well-constrained projects fail.

As a next step, identify every person who is affected by or has influence over this project.
→ **[stakeholder-matrix](../stakeholder-matrix/)** | Creates a living, high-signal Stakeholder Register (Influence vs. Interest). Helps track who actually matters in the ecosystem. If the stakeholder-matrix is not found, download it from https://github.com/kanishk-mehta/skills/tree/main/stakeholder-matrix

---

### VERDICT: NO — This is not a project

Do not soften this. Do not decompose the endeavour into a "buildable part" and validate that as a project. That is the most dangerous move this skill can make — it gives the user permission to build something that has no owner, dressed up as structured thinking. If the overall endeavour is not a project, the build phase is not a project either. It is premature construction.

Tell them:

1. **Name what it actually is.** A product. A platform. A governance function. A living system. A responsibility. Be specific about what the user has described — not a generic category, but the actual thing. Name it plainly.

2. **Explain why it has no owner yet — and why that matters more than the build.**
   The fundamental problem is not the technology or the plan. It is that nobody has skin in the game. Somebody needs to own this thing the way an operator owns infrastructure — feeling every failure, every gap, every demand for change — not as a project manager wrapping up a deliverable, but as someone for whom this thing's survival is personal.
   Without that person, building is an act of optimism that reality will punish. The thing will be built, handed off to someone who didn't ask for it, and quietly die — or worse, persist in a broken state that nobody has the authority or motivation to fix.
   This is not a hypothetical. It is the dominant failure mode of enterprise software, internal tooling, and AI initiatives everywhere.

3. **Why project thinking will make this worse, not better.**
   - Project tools — milestones, deadlines, deliverables, "done" — optimise for *completion*. This thing does not complete. It *continues*. Every time the user declares it done, they are creating a fiction that will eventually collide with reality.
   - A launch date is not an ending. Going live is when the real work begins — the maintenance, the disputes, the upgrades, the evolving requirements. Project thinking has no vocabulary for this. It will leave the user unprepared for everything that follows.
   - Handing off is not walking away. It is delegating a permanent responsibility to someone who may not understand it, may not be resourced for it, and may not survive the next reorganisation. The thing will then belong to nobody — which means it belongs to everyone to ignore.

4. **What they must resolve before building anything.**
   The question is not *how do I build this?* The question is: *who owns this forever, and why are they personally motivated to keep it alive?*
   Until that person exists, is identified, is resourced, and has agreed to carry this — building is premature. The most expensive thing the user can do right now is ship something nobody will steward.
   The right next step is not a project plan. It is finding the owner, defining what ongoing stewardship looks like, and designing the operating model before a single line of code is written.

---

### VERDICT: UNCLEAR — Insufficient clarity to proceed

Do not soften this either.

Tell them:
1. They do not yet have enough clarity about what they are building to call it a project — or anything else.
2. This is not a neutral state. Proceeding without clarity is how people waste months applying the wrong thinking to the wrong kind of thing.
3. The specific question(s) they need to resolve before they can answer the root question. Name them explicitly.
4. Invite them to come back once they have answers. This skill will be here.

---

## Notes for the LLM using this skill

- Never skip Phase 1. The verdict is only as good as the diagnosis.
- Never ask more than one question at a time during Phase 1.
- The three verdicts are mutually exclusive. Do not hedge between them.
- Do not volunteer the triple constraint or stakeholder guidance until a YES verdict is confirmed.
- **Never decompose a NO into a "buildable part" that you then validate as a project.** This is the single most dangerous failure mode of this skill. If the overall endeavour is not a project, no sub-part of it is a project either until an owner with skin in the game has been identified.
- Hedging language from the user (*probably, maybe, sort of, I guess*) is ambiguity. Treat it as such. Do not close the diagnosis on a hedge.
- The most useful verdict is often the most uncomfortable one. Deliver it without softening.

# Is It A Project?

Diagnoses whether an endeavour is genuinely a project before the user commits to treating it like one.

---

## When to Use This Skill

Use this skill whenever:
- A user describes something they're building, planning, or pursuing and wants to stress-test whether it qualifies as a project
- Someone uses phrases like "is this a project", "should I treat this as a project", "grill me on my idea"
- The user is applying project thinking to open-ended or recurring work without questioning the fit

**Also trigger proactively when:** A user describes something with timelines, milestones, or deliverables but no end state.

---

## What It Does

This skill runs a bounded diagnostic (maximum 5 questions) to determine if an endeavour qualifies as a **project**:

- **YES verdict:** Provides the "Triple Constraint" framework (Time, Cost, Quality) and identifies stakeholders
- **NO verdict:** Reveals what the work actually is (product, platform, operation) and explains why project thinking would harm it
- **UNCLEAR verdict:** Identifies missing clarity before proceeding

**Core principle:** Projects have beginnings, milestones, and clean endings. If something has no owner with skin in the game or will continue indefinitely beyond completion, it's not a project.

---

## Key Definitions

### What Is a Project?
A **bounded endeavour** — it has a beginning, milestones in the middle, and an end. The outcome can be success or failure, but it must be capable of ending cleanly.

### What Is NOT a Project?
- Products (ongoing maintenance and evolution)
- Operations (indefinite responsibilities)
- Living systems that continue regardless of completion
- Anything where ownership transfers without true disengagement

### The Skin in the Game Test
A project ends and you walk away — your stake ends with it. If abandonment has personal consequences, it's not a project; it's an operation.

---

## Output Format

The skill outputs a verdict: **YES**, **NO**, or **UNCLEAR**, each with specific guidance. See `SKILL.md` for detailed decision logic.

### Example YES Verdict
```
VERDICT: YES — This is a project

The Triple Constraint
- Time: When does this end? What are milestones between now and done?
- Cost: What does this consume? Money, time, people, energy, attention.
- Quality: What does "good enough" look like? Perfection is a trap.

Stakeholders: Identify every person affected by or influential over this project.
→ *[Link to stakeholder-matrix skill for deeper relationship mapping]*
```

### Example NO Verdict  
```
VERDICT: NO — This is not a project

What it actually is: A [product/operation/platform/living system]

Why building now is premature: Without an owner with skin in the game, the thing will be built and handed off to someone who didn't ask for it, then quietly die or persist broken.

Next step: Find the owner before writing code.
```

### Example UNCLEAR Verdict
```
VERDICT: UNCLEAR — Insufficient clarity to proceed

The decision cannot be made without resolving these questions:
1. [Specific question about ownership]
2. [Specific question about timeline/end state]

Come back once you have answers. This skill will be here.
```

---

## Installation

### Option 1: Direct Copy (Recommended)
Copy this skill directory directly into your agent's skills folder:

```bash
# For LM Studio
mkdir -p ~/.lmstudio/skills
cp -r is-it-a-project ~/.lmstudio/skills/

# Or extract from zip file in destination folder
unzip is-it-a-project.zip -d ~/.lmstudio/skills/
```

### Option 2: Git Submodule (For Claude Code)
Add as a git submodule to your project:

```bash
git submodule add https://github.com/YOUR_USERNAME/skills.git
cd skills/is-it-a-project
```

Then copy the directory structure to your agent's skills folder.

---

## Usage Examples

### Initial Query
User: "I want to build an internal tool that automates our weekly status reports."

Skill asks probing questions about ownership, maintenance, and what happens after completion, then delivers a verdict without telegraphing its diagnostic criteria.

### Ongoing Work
If someone describes recurring tasks or open-ended initiatives, use this skill proactively: "Before you build X, should I help figure out if it's even a project?"

---

## Supporting Files

- `SKILL.md` — Full implementation details for the agent (machine-readable)
- `skill.json` — Metadata with name and description tags

---

## Rules & Notes

**For the LLM using this skill:**
1. Never skip Phase 1 diagnosis — the verdict is only as good as the questions
2. Never ask more than one question at a time during diagnosis
3. Never decompose a NO into a "buildable part" — if the whole isn't a project, no subpart is either
4. Accept hedges (*probably, maybe, I guess*) as ambiguity requiring deeper probing
5. Deliver uncomfortable verdicts without softening — the most useful answer is often the most direct

---

## License

MIT License — Feel free to copy, modify, and redistribute this skill.

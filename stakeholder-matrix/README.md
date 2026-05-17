# Stakeholder Matrix

Create and maintain a living **Stakeholder Register** (Influence vs Interest matrix) for any work context — projects, products, initiatives, or programs.

---

## When to Use This Skill

Use this skill whenever:
- A user mentions stakeholders or needs to manage relationships
- They need to prepare for communications or decisions involving other people  
- Doing any kind of project or product management
- Tracking political dynamics or mapping who matters and why

**Trigger proactively:** Before ANY task that involves communicating with, presenting to, or making decisions affecting others.

---

## What It Does

This skill builds and maintains a structured stakeholder register using the **Influence vs Interest** framework:

- **Manage Closely (High Influence, High Interest):** Critical people to engage directly
- **Keep Satisfied (High Influence, Low Interest):** People who can block or mandate work
- **Keep Informed (Low Influence, High Interest):** People actively tracking progress
- **Monitor (Low Influence, Low Interest):** Passive awareness sufficient

The register captures:
- Who matters and why
- Their influence and interest levels per project
- Stance (Champion, Critic, Supporter, Neutral)
- Historical data (inactive stakeholders preserved)

---

## Core Principles

### Never Ask for Raw Scores
Ask questions about observable signals instead:
- What decisions can this person block or accelerate?
- Who do decision-makers consult informally?
- Does this person control budget/headcount/approvals?
- Has their name come up when they weren't in the room?
- Do people seem cautious around them?

### Derive from Evidence
Every position in the matrix is a hypothesis updated by evidence. New interactions may change scores.

### Never Delete, Always Archive
Inactivity = `active: false`, not deletion. Preserve history for context.

---

## File Structure

```
stakeholder-matrix/
├── SKILL.md              # Agent instructions (machine-readable)
├── README.md             # Human documentation (this file)
├── skill.json            # Metadata with name and description tags
└── assets/
    ├── register.template.json
    └── register.template.md
```

### Data Files Created by the Skill
When initialized, creates in working directory:
- `./stakeholders/register.json` — Source of truth (structured data)
- `./stakeholders/register.md` — Human-readable view (formatted matrix)

---

## Installation

### Option 1: Direct Copy (Recommended)
Copy this skill directory into your agent's skills folder:

```bash
# For LM Studio
mkdir -p ~/.lmstudio/skills  
cp -r stakeholder-matrix ~/.lmstudio/skills/

# Or extract from zip file in destination folder
unzip stakeholder-matrix.zip -d ~/.lmstudio/skills/
```

### Option 2: Git Submodule (For Claude Code)
Add as a git submodule to your project:

```bash
git submodule add https://github.com/YOUR_USERNAME/skills.git
cd skills/stakeholder-matrix
```

Then copy the directory structure to your agent's skills folder.

---

## Usage Examples

### Bootstrapping (First Use)
User asks a project-related question, and no stakeholder register exists yet:

```
Skill: "No stakeholder register found — let me gather a few details."
Skill asks: "Who are the 2–3 most critical people involved in this work?"
→ Creates ./stakeholders/register.json and register.md
→ Resumes original task with context
```

### Pre-Task Scan
Before executing any task, skill shows relevant stakeholders:

```
── Stakeholder Scan: [Project] ──────────────────────────
Relevant: Jane D.  Manage Closely · Critic     [5, 4]
          Bob K.   Manage Closely · Champion   [4, 3]  
Risk:      Jane is a Critic — addressing her concerns directly.
Opportunity: Bob is a Champion — reinforcing his position.
─────────────────────────────────────────────────────────
```

### Re-evaluation
When stakeholders are mentioned in conversation or when 30 days pass since last update, the skill prompts for updated assessment.

---

## Output Format

The skill outputs structured JSON and formatted Markdown:

### JSON Structure (register.json)
```json
{
  "stakeholders": [
    {
      "name": "Jane Doe",
      "role": "CFO",
      "organization": "Internal",
      "active": true,
      "projects": [
        {
          "project": "Q4 Strategy",
          "influence": 5,
          "interest": 4,
          "quadrant": "Manage Closely",
          "stance": "Critic",
          "notes": "Pushes back on budget allocations",
          "last_updated": "2025-01-17"
        }
      ]
    }
  ]
}
```

### Markdown View (register.md)
```markdown
# Stakeholder Register
_Last updated: 2025-01-17_

## Q4 Strategy

HIGH INFLUENCE
┌───────────────────────┬───────────────────────┐
│     KEEP SATISFIED    │     MANAGE CLOSELY    │
│                       │ Jane D. [5,4] Critic  │
│                       │ Bob K.  [4,3] Champion│
├───────────────────────┼───────────────────────┤
│        MONITOR        │     KEEP INFORMED     │
│ Tom R. [2,1] Neutral  │ Sara M. [2,3] Supporter│
└───────────────────────┴───────────────────────┘
LOW INFLUENCE                    HIGH INTEREST

| Name | Role | Influence | Interest | Quadrant | Stance | Updated |
|------|------|-----------|----------|----------|--------|---------|
| Jane D. | CFO | 5 | 4 | Manage Closely | Critic | 2025-01-17 |
```

---

## Installation Steps After Setup

When you first install this skill, run:

```bash
# Create stakeholders directory
mkdir -p ./stakeholders

# Copy templates if they don't exist
cp assets/register.template.json ./stakeholders/
cp assets/register.template.md ./stakeholders/
```

---

## Scoring Rubric

| Score | Influence | Interest |
|-------|-----------|----------|
| **5** | Can kill or mandate the work | Actively tracking daily |
| **4** | Can significantly shape scope/resources | Regularly engaged |
| **3** | Has notable input, consulted often | Aware and occasionally engaged |
| **2** | Minor input, rarely consulted | Passively aware |
| **1** | No meaningful impact | Unaware or indifferent |

---

## Rules & Notes

### For the LLM using this skill:
1. Always show stakeholder scan before task execution (even for routine tasks)
2. Never silently update the register — always propose changes with reasoning
3. Treat every new interaction as evidence that may update positions
4. Keep project scope to one project at a time when multiple apply
5. Use discovery protocol questions, not raw score requests

### Key Questions for Stakeholder Assessment:
- What decisions can this person block, delay, or accelerate?
- Who do decision-makers consult before changing direction (even informally)?
- Does this person control budget, headcount, tools, or approvals?
- Has their name come up in meetings when they weren't in the room?
- Do people seem cautious around them?
- How often does this person ask for updates or track progress?

---

## License

MIT License — Feel free to copy, modify, and redistribute this skill.

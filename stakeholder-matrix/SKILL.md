---
name: stakeholder-matrix
description: Create and maintain a living Stakeholder Matrix (Influence vs Interest) for any work context — projects, products, initiatives, or programs. Use this skill whenever a user mentions stakeholders, needs to manage relationships, wants to prepare for communications or decisions involving other people, or is doing any kind of project or product management. Trigger proactively when performing ANY task that involves communicating with, presenting to, or making decisions that affect other people. Also use when a user wants to map influence, track political dynamics, or understand who matters and why in their organization.
---

# Stakeholder Matrix Skill

Help users build and maintain a living stakeholder register that makes every output you produce more impactful. The register captures who matters, how much, and why — so your work is always relationally and politically aware.

---

## File Locations

Always use these fixed paths relative to the working directory:
- **Source of truth**: `./stakeholders/register.json`
- **Human view**: `./stakeholders/register.md`

Templates are in `assets/` next to this SKILL.md. Copy them to `./stakeholders/` on first run if the register does not exist.

---

## Schema

`register.json` holds a top-level array of stakeholder objects:

```json
{
  "stakeholders": [
    {
      "name": "string",
      "role": "string",
      "organization": "string",
      "active": true,
      "projects": [
        {
          "project": "string",
          "influence": 3,
          "interest": 4,
          "quadrant": "Manage Closely",
          "stance": "Supporter",
          "notes": "string",
          "last_updated": "YYYY-MM-DD"
        }
      ]
    }
  ]
}
```

**Key rules:**
- `quadrant` is always derived from scores — never set manually
- `project` is a free-form label — a project, product, initiative, or anything else
- `active: false` retires a stakeholder — never delete, always preserve history
- A stakeholder can appear under multiple projects with different scores per project

---

## Scoring Rubric

| Score | Influence | Interest |
|---|---|---|
| 5 | Can kill or mandate the work | Actively tracking daily |
| 4 | Can significantly shape scope or resources | Regularly engaged |
| 3 | Has notable input, consulted often | Aware and occasionally engaged |
| 2 | Minor input, rarely consulted | Passively aware |
| 1 | No meaningful impact | Unaware or indifferent |

**Quadrant derivation** (always computed, never assumed):
- Influence ≥ 3 AND Interest ≥ 3 → **Manage Closely**
- Influence ≥ 3 AND Interest < 3 → **Keep Satisfied**
- Influence < 3 AND Interest ≥ 3 → **Keep Informed**
- Influence < 3 AND Interest < 3 → **Monitor**

---

## Discovery Protocol

Never ask for raw scores. Instead, ask questions the user can answer from observation — including signals they may not have thought to consider. Many of the most important influences are tribal knowledge: informal authority, political capital, shadow decision-makers.

### Fixed Core Questions (always ask for each new or re-evaluated stakeholder)

1. What decisions about this work can this person block, delay, or accelerate?
2. Who do decision-makers consult before changing direction — even informally?
3. Does this person control budget, headcount, tools, or approvals — even indirectly?
4. Has this person's name come up in meetings when they weren't in the room?
5. Do people seem cautious around them, or careful not to upset them?
6. How often does this person ask for updates, attend reviews, or track progress?
7. What would change if this person became actively opposed to the work?
8. Who does this person have strong relationships with that could amplify their reach?

### Dynamic Extensions

After the core questions, generate 2–3 additional questions specific to:
- The stakeholder's role and organizational level
- The nature of the work (technical, budgetary, political, operational)
- Any signals already present in the conversation

### Scoring from Answers

Derive scores from answers using the rubric. Show your reasoning before writing anything:

> "Based on what you've described, I'd score Jane 4/5 on influence — she controls budget approvals and her name comes up in steering decisions. And 3/5 on interest — she attends monthly reviews but doesn't track daily. Quadrant: Manage Closely. Stance: Critic based on her budget pushback. Confirm?"

Wait for confirmation before writing.

---

## Agent Behaviors

### 1. Bootstrapping (no register exists)

If `./stakeholders/register.json` does not exist:
1. Say: "No stakeholder register found — let me gather a few details before we continue."
2. Ask: "Who are the 2–3 most critical people involved in this work right now?"
3. Run the discovery protocol for each
4. Create `./stakeholders/`, write `register.json` and `register.md`
5. Resume the original task with the new register as context

Keep this lightweight — the goal is a minimum viable register, not an exhaustive one.

### 2. Pre-Task Stakeholder Scan

Before executing any task:
1. Read `./stakeholders/register.json`
2. State assumed project scope: "Treating this as [project] — correct?"
3. Identify which active stakeholders are relevant to this task
4. Show a brief scan:

```
── Stakeholder Scan: [Project] ──────────────────────────
Relevant:  Jane D.  Manage Closely · Critic     [5, 4]
           Bob K.   Manage Closely · Champion   [4, 3]
Risk:      Jane is a Critic — addressing her concerns directly.
Opportunity: Bob is a Champion — reinforcing his position.
─────────────────────────────────────────────────────────
```

5. Execute the task with this context baked into the output

Always show the scan — even for routine tasks.

### 3. Re-evaluation Triggers

Re-evaluate a stakeholder's position when:
- They are mentioned in a task or conversation
- The user describes a meeting, conflict, or decision involving them
- The user mentions org changes, promotions, or departures
- A stakeholder's tone or stance appears to have shifted
- 30 days have passed since their `last_updated` date

Run the discovery protocol (or a targeted subset) and propose updates with reasoning before writing.

### 4. Update Protocol

Never silently update the register. Always:
1. Propose: "Updating [Name] on [Project]: [field] [old value] → [new value]. Reason: [reasoning]. Confirm?"
2. Wait for approval
3. On confirmation: update `register.json`, then immediately regenerate `register.md`

### 5. Project Scope

When a task could relate to multiple projects, state your assumption and confirm. Keep task scopes to a single project at a time.

### 6. Retiring a Stakeholder

Set `active: false` and note the reason in their `notes` field. Never delete entries.

---

## Markdown Format

Regenerate `register.md` in full after every confirmed update.

```markdown
# Stakeholder Register
_Last updated: YYYY-MM-DD_

---

## [Project Name]

HIGH INFLUENCE
┌──────────────────────────┬──────────────────────────┐
│      KEEP SATISFIED      │      MANAGE CLOSELY      │
│                          │  Jane D. [5,4] Critic    │
│                          │  Bob K.  [4,3] Champion  │
├──────────────────────────┼──────────────────────────┤
│         MONITOR          │      KEEP INFORMED       │
│  Tom R. [2,1] Neutral    │  Sara M. [2,3] Supporter │
└──────────────────────────┴──────────────────────────┘
LOW INFLUENCE
          LOW INTEREST  ──────────►  HIGH INTEREST

| Name | Role | Org | Influence | Interest | Quadrant | Stance | Updated |
|------|------|-----|-----------|----------|----------|--------|---------|
| Jane D. | CFO | Internal | 5 | 4 | Manage Closely | Critic | 2026-05-17 |
| Bob K. | VP Eng | Internal | 4 | 3 | Manage Closely | Champion | 2026-05-17 |
| Sara M. | Team Lead | Internal | 2 | 3 | Keep Informed | Supporter | 2026-05-17 |
| Tom R. | Vendor | External | 2 | 1 | Monitor | Neutral | 2026-05-17 |

---
```

Repeat the section for each project. List inactive stakeholders at the bottom under `## Inactive Stakeholders`.

---

## First Principles

Reason from observable signals, not assumptions or titles:
- What authority does this person actually hold — formal or informal?
- What have their actions revealed about their interest level?
- Who do others defer to when this person speaks?
- What would materially change if they became a blocker tomorrow?

Every position in the matrix is a hypothesis. Treat every new interaction as evidence that may update it.

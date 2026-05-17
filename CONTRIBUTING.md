# Contributing to Skills Collection

This guide helps you add new skills or improve existing ones while maintaining consistency with the collection's design philosophy.

---

## SKILL.md Style Guide

Every skill must have a `SKILL.md` file that agents read automatically. Follow this structure:

### 1. Header (First Lines)
Start with machine-readable metadata in YAML frontmatter (optional but recommended):

```yaml
---
name: skill-name
description: |
  One or two sentences explaining what the skill does and when to use it.
  Mention trigger phrases in quotes if applicable.
  Also mention proactive triggers.
---
```

Or a simple header:
```markdown
# skill-name

Brief one-sentence description of when to use this skill.
```

### 2. Core Purpose Section
Explain **what the skill does** and **when to trigger it**:

- Clear, direct language
- Specific trigger phrases in code blocks or bullet points
- Proactive usage guidelines

### 3. Main Content Sections
Use `---` dividers between major sections:

```markdown
---

## Section Title
Content goes here with:
- Numbered workflows (if applicable)
- Code examples
- Tables for definitions/rubrics
- Blockquotes for key rules
- Bullet points for checklists
```

### 4. Output Format Examples
Show expected output in markdown code blocks:

```markdown
## Example Output

\`\`\`
## Summary
One paragraph...
\`\`\`
```

### 5. Rules Section
Critical guidance as bullet points:

```markdown
---

## Rules
- Never skip [X] even if [Y] looks fine
- Always do [A] before doing [B]
- Show reasoning before making changes
```

### 6. Additional Files (If Any)
Document supporting files:

```markdown
---

## Supporting Files
- `skill.json` — Metadata with name and description
- `templates/template.txt` — Example templates
```

### 7. License
Always include license information at the end:

```markdown
---

## License
MIT License — Feel free to copy, modify, and redistribute this skill.
```

---

## File Structure Template

```markdown
skill-name/
├── SKILL.md          # Main entry point (required)
└── README.md         # Human documentation (recommended)
    └── assets/       # Supporting templates, scripts, etc.
```

### Required: `SKILL.md`
The file agents read to understand and use the skill. Must include:
- Clear description of purpose
- Trigger conditions
- Workflow/process steps
- Output format examples
- Rules/guidelines

### Recommended: `README.md`
Human-readable documentation explaining:
- When to install/use the skill
- Installation options (copy, zip, submodule)
- Usage examples
- File structure overview

---

## Testing Locally

Before committing, test your skill with a few queries:

### For LM Studio
```bash
# Add your skill directory to ~/.lmstudio/skills/
cd ~/.lmstudio/skills
# Restart LM Studio if needed
```

Then use the agent interface to query your skill.

---

## Common Patterns to Follow

From excellent skills like `is-it-a-project`:
1. **Clear decision phases** (diagnosis → verdict → action)
2. **Concrete output formats** with examples in code blocks
3. **Strict rules** as bullet points (no hedging, no softening)
4. **Evidence-based approaches** over assumptions
5. **No telegraphing diagnostic criteria** — let the user discover answers naturally

---

## Commit Guidelines

1. **Don't change `SKILL.md`** unless you've tested the skill works
2. **Keep it simple** — One skill per directory, one purpose per file
3. **Test across platforms** — If possible, test in multiple agent environments
4. **Include README.md** for each new skill with installation instructions

---

## Review Checklist

Before creating a pull request:

- [ ] `SKILL.md` follows the style guide above  
- [ ] Trigger phrases are clearly listed
- [ ] Output format has at least one example in code block
- [ ] Rules section covers edge cases and common mistakes
- [ ] `skill.json` exists with correct metadata
- [ ] Tested locally and produces expected output
- [ ] No `.DS_Store` or other gitignore'd files committed
- [ ] All dependencies are documented (if any)

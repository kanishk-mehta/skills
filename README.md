# Skills Collection

A curated collection of agent skills for project management, stakeholder analysis, and structured decision-making workflows.

---

## Skills Included

### 📋 Project Management & Decision Making

| Skill | Description |
|-------|-------------|
| **[is-it-a-project](./is-it-a-project/)** | Diagnoses whether an endeavour is genuinely a project before committing to treating it like one |
| **[stakeholder-matrix](./stakeholder-matrix/)** | Creates and maintains a living Stakeholder Register (Influence vs Interest matrix) for any work context |

---

## Installation Options

### Option 1: Copy Individual Skills (Recommended for LM Studio)

Copy each skill directory directly into your agent's skills folder:

```bash
# For LM Studio or similar local agents
mkdir -p ~/.lmstudio/skills

# Clone individual skills from this repo
git clone https://github.com/YOUR_USERNAME/skills.git ~/skills-temp

cp -r ~/skills-temp/is-it-a-project ~/.lmstudio/skills/
cp -r ~/skills-temp/stakeholder-matrix ~/.lmstudio/skills/
```

### Option 2: Extract from ZIP Files

Most agent platforms accept ZIP files with a `SKILL.md` entry point:

```bash
cd ~/.lmstudio/skills
unzip is-it-a-project.zip -d .
unzip stakeholder-matrix.zip -d .
```

### Option 3: Git Submodule (For Claude Code)

Add as a submodule to your project or agent's skills directory:

```bash
git submodule add https://github.com/YOUR_USERNAME/skills.git
cd skills/is-it-a-project
# Copy the entire directory structure to your agent's skills folder
```

---

## File Structure

```
skills/                          # Root repository
├── README.md                    # This file - overview and catalog
├── CONTRIBUTING.md              # Guidelines for adding new skills  
├── .gitignore                   # Files to exclude from version control
│
├── is-it-a-project/             # Project diagnosis skill
│   ├── SKILL.md                 # Agent entry point (machine-readable)
│   └── README.md                # Human documentation
│
└── stakeholder-matrix/          # Stakeholder tracking skill
    ├── SKILL.md                 # Agent entry point
    ├── README.md                # Human documentation  
    ├── assets/                  # Templates (register.template.json, etc.)
    └── skill.json               # Metadata tags
```

---

## How Skills Work

### What Is a Skill?

A skill is primarily a **SKILL.md file** that defines:
- When to trigger the skill (via name, tags, description)
- What it does and how it works
- Output format and rules
- Supporting files if any

### Machine-Readable Metadata (`skill.json`)

Each skill has `skill.json` for easy discovery by agent platforms:

```json
{
  "name": "is-it-a-project",
  "description": "Diagnoses whether an endeavour is genuinely a project..."
}
```

---

## License

MIT License — All skills can be copied, modified, and redistributed.

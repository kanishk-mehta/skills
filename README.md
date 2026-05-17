# ⚙️ Agent Skills Collection

I've spent over a decade building AI and enterprise products, learning one fundamental truth along the way: treating everything like a "project" is a trap. Real products are living organisms; they demand infinite perseverance, long-term ownership, and an obsession with solving problems rather than just hitting finite milestones.

I tinker with agentic logic the same way I tinker with audio routing or mechanical systems—stripping away the noise to figure out exactly how the underlying machine works. This repository is my personal sandbox. It's a curated set of no-BS, high-signal agent skills built on principles of minimalism. They are designed to force clarity into decision-making workflows. 

---

## 🛠 The Skills

| Skill | The "Why" |
|-------|-------------|
| **[is-it-a-project](./is-it-a-project/)** | Ruthlessly diagnoses whether an endeavor is genuinely a project before you commit the cardinal sin of treating it like one. |
| **[stakeholder-matrix](./stakeholder-matrix/)** | Creates a living, high-signal Stakeholder Register (Influence vs. Interest). Helps track who actually matters in the ecosystem. |

---

## 📦 Installation 

### Local Agents (e.g., LM Studio)
Copy the skill directories directly into your agent's skills folder to plug them straight into the system.

```bash
# For LM Studio or similar local agents
mkdir -p ~/.lmstudio/skills

# Clone individual skills from this repo
git clone https://github.com/YOUR_USERNAME/skills.git ~/skills-temp

cp -r ~/skills-temp/is-it-a-project ~/.lmstudio/skills/
cp -r ~/skills-temp/stakeholder-matrix ~/.lmstudio/skills/

```

### Agent Platforms (ZIP deployment)

Extract the ZIP files directly into your environment. Most platforms look strictly for the `SKILL.md` entry point.

```bash
unzip is-it-a-project.zip -d ~/.lmstudio/skills/

```

### Git Submodule (e.g., Claude Code)

Add as a submodule to your project's existing skills directory.

```bash
git submodule add [https://github.com/YOUR_USERNAME/skills.git](https://github.com/YOUR_USERNAME/skills.git)

```

---

## 🧠 Under the Hood

### What is a Skill?

A skill is fundamentally driven by a **`SKILL.md`** file. It acts as the mechanical logic for the agent, defining:

* **Trigger Conditions:** Exactly when the agent should fire it up.
* **Execution Rules:** How to process the input cleanly and functionally.
* **Formatting Constraints:** Ensuring the output is strictly high-signal.

### Structure

```text
skills/
├── README.md               # You are here.
├── is-it-a-project/        # The diagnostic tool 
│   ├── SKILL.md            # Agent logic
│   └── README.md           # Human translation
└── stakeholder-matrix/     # The influence tracker
    ├── SKILL.md            
    ├── README.md             
    ├── assets/             # Templates
    └── skill.json          # Machine-readable metadata

```

## ⚖️ License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

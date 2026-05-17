# ⚙️ Agent Skills Collection

I've spent over a decade building AI and enterprise products, learning one fundamental truth along the way: treating everything like a "project" is a trap. Real products are living organisms; they demand infinite perseverance, long-term ownership, and an obsession with solving problems rather than just hitting finite milestones.

I tinker with agentic logic the same way I tinker with audio routing or mechanical systems—stripping away the noise to figure out exactly how the underlying machine works. This repository is my personal sandbox. It's a curated set of no-BS, high-signal agent skills built on principles of minimalism. They are designed to force clarity into decision-making workflows. 

---

## 🧠 Why These Skills Exist

I built these skills as a way to fix the fundamental failure modes I see when applying AI agents—and traditional management frameworks—to product development. 

### #1: The "Project" Trap

> "Good design is as little design as possible." 
> — Dieter Rams, [Ten Principles for Good Design](https://www.amazon.ca/Dieter-Rams-Principles-Good-Design/dp/3791387324)

**The Problem:** The most common failure mode in enterprise software isn't bad code; it's bad framing. We default to treating everything as a "project" with a finite start, middle, and end. This is a trap. Real products are living organisms. If you treat a living product like a finite project, you kill long-term problem ownership, and you end up with abandoned, rotting software the second the "milestone" is hit.

**The Fix:** Before writing a single line of code or assigning a single ticket, you have to diagnose the endeavor. 
* Use **`is-it-a-project`**. 
This skill is a ruthless diagnostic tool. It forces you (and your agent) to look at the work and determine if it deserves to be a finite project, or if it requires infinite, ongoing product perseverance. Run this first to establish the right mindset.

### #2: The Signal-to-Noise Problem

> "There is nothing quite so useless as doing with great efficiency something that should not be done at all."
> — Peter Drucker

**The Problem:** Corporate environments are flooded with low-signal noise. When building a product, everyone wants a say, but very few people actually have the influence or interest that dictates the product's survival. Traditional project management tells you to listen to everyone, which leads to bloated, compromised, "design-by-committee" tech-debt. 

**The Fix:** You need a high-signal filter.
* Use **`stakeholder-matrix`**.
This skill acts like a mechanical logic gate for human feedback. Instead of drowning in noise, you use this skill to plot the ecosystem on a strict Influence vs. Interest matrix. It strips away the BS and tells you exactly who you actually need to manage, who you need to keep informed, and who you can safely ignore. 

**Summary**

High-signal communication and long-term ownership matter more than ever in the AI age. These skills are my best effort at condensing a decade of enterprise product leadership into repeatable, mechanical logic blocks. 

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

**OR**

If your organization uses a platform like **[baioniq](https://www.baioniq.com)**, share the compressed / ZIP files with your group manager/administrator and they can add install the skill for you

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

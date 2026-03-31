# 🧭 Persona Compass

> **Navigate people like you navigate code.**
> **职场读心术，AI 帮你搞定难搞的人。**

Build AI-powered personality models of the people around you. Predict their behavior. Get actionable communication strategies. Win every conversation before it starts.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-green)](https://agentskills.io)
![Bilingual](https://img.shields.io/badge/Language-EN%20%7C%20%E4%B8%AD%E6%96%87-blue)

---

**Why Persona Compass?**

Most workplace friction isn't about skills — it's about people. Persona Compass gives you:

| | What you get |
|---|---|
| 🎯 Predict | How someone will react *before* the conversation happens |
| 💬 Script | Ready-to-paste Slack/email drafts calibrated to their psychology |
| 🕸️ Map | Relationship networks, alliances, and influence paths across your org |
| 🌏 Cultural | Built-in overlays for Chinese, American, Japanese, Korean workplaces |
| 🔒 Private | Codename system — no real names visible on screen |
| ⚡ Fast | `/pc prep` or `/pc tone` outputs in 5–30 seconds |

Zero dependencies. No API keys. Works on Claude Code, Claude.ai, and mobile.

---

## Quick Start

### Install — Claude.ai (Browser, recommended for non-developers)

1. [Download this repo as a ZIP](https://github.com/snowyowlmia/persona-compass/archive/refs/heads/main.zip) and unzip it
2. Go to [claude.ai](https://claude.ai) → Open or create a **Project**
3. In the Project, click **Add content** → upload the unzipped `persona-compass` folder
4. Done! In that Project, just describe the person you want to navigate and Claude will activate the skill

> Works on Pro, Max, Team, and Enterprise plans. Projects require a paid plan.

### Install — Claude Code (Terminal, for developers)

```bash
# Project-level (recommended — skill only active in this project)
mkdir -p .claude/skills
git clone https://github.com/snowyowlmia/persona-compass .claude/skills/persona-compass

# Global (skill active in all your projects)
git clone https://github.com/snowyowlmia/persona-compass ~/.claude/skills/persona-compass
```

Then in Claude Code, just type `/persona-compass` or `/pc` to start.

### No Installation — Claude Mobile / Free Plan

No setup needed. Open any Claude conversation, paste this to get started:

**English:**
```
Please read and follow the skill instructions at:
https://raw.githubusercontent.com/snowyowlmia/persona-compass/main/SKILL.md

Then help me analyze a person I work with.
```

**中文用户：**
```
请阅读并遵循以下技能说明：
https://raw.githubusercontent.com/snowyowlmia/persona-compass/main/SKILL.md

然后帮我分析一个我生活或工作中认识的人。
```

Claude will follow the full framework in that conversation.

### Use

```
> /persona-compass

How well do you know this person?
  [A] Quick Sketch (30 seconds)
  [B] Standard Profile (5 minutes)
  [C] Deep Analysis (10+ minutes)
```

### Example

```
You:    My PM David is a control freak. INTJ. ByteDance background.
        He keeps taking credit for my work.

Compass: Based on David's profile (D-type, high conscientiousness,
         recognition-motivated, ByteDance culture), here's your strategy:

         1. Paper Trail Defense: Send "alignment" emails after every
            decision. CC your manager. David's credit-claiming drops
            70% when he knows there's documentation.

         2. Win-Win Frame: "Hey David, let's co-present this at
            the all-hands. I think the story is stronger together."
            This gives him visibility while ensuring yours.

         3. Nuclear Option: If it continues, schedule a 1:1.
            Lead with: "I want us to work well together.
            I've noticed our contributions aren't always visible
            equally. How can we fix this?"
```

---

## Features

### 🧠 Generator Mode — One Person, One Skill File
The core architecture. Analyze someone once, never explain them again.

```
Step 1:  /persona-compass  →  guided interview about "PM David"
Step 2:  Claude generates   →  personas/david/SKILL.md
Step 3:  Next time, just    →  /david
         Claude instantly knows everything. No re-entry. Ever.
```

Each person becomes a **self-contained, loadable skill** with full personality model,
communication playbook, and behavioral predictions baked in.
Like having a permanent, always-ready dossier on everyone you work with.

### 🔒 Privacy-First Design
- **Codename system**: All files and commands use codenames, never real names
- No one glancing at your screen will know who you're analyzing
- All data stays 100% local — no cloud sync, no telemetry
- Real names only appear in `observations.md` (gitignored by default)

### ⚡ Quick Commands (5-30 seconds)
Once a persona is saved, these commands work instantly:
- `/pc prep david` → 6-line pre-meeting cheat sheet
- `/pc tone david` → 1-line tone calibration before sending a message
- `/pc draft david "push back on deadline"` → copy-pasteable message, nothing else
- `/pc simulate david "public disagreement in meeting"` → full scenario playbook
- `/pc update david` → add new observations, model auto-refines

### 🎯 Three-Tier Persona Building
- **Quick Sketch**: Name + role + 3 adjectives → instant persona card
- **Standard Profile**: 8-question guided interview → data-backed model
- **Deep Analysis**: Paste chat logs + incident reports → high-fidelity predictions

### � Multi-Framework Personality Modeling
- Big Five (OCEAN) with per-dimension confidence scores
- DISC behavioral profiling
- Thomas-Kilmann conflict styles
- Motivation driver analysis (Recognition / Power / Security / Achievement / Belonging / Autonomy)

### 🎭 Scenario Simulator
20+ built-in templates across 4 categories:

**Workplace — Collaboration:** deadline-slip · resource-request · cross-team-dependency · scope-change

**Workplace — Conflict:** credit-dispute · blame-deflection · territory-invasion · public-disagreement

**Workplace — Career:** promotion-ask · salary-negotiation · skip-level-meeting · performance-review

**Workplace — Boundaries:** saying-no-to-boss · pushing-back-on-deadline · scope-creep-defense

**Personal:** financial-discussion · parenting-disagreement · boundary-setting

### 💬 Communication Script Generator
- Ready-to-paste Slack messages, emails, and 1:1 talking points
- 2-3 strategic variants per scenario, each labeled by what it optimizes for
- Scripts calibrated to the person's DISC type, conflict style, and cultural context

### 🌏 Cross-Cultural Intelligence
Built-in cultural overlay engine:
- 🇨🇳 Chinese workplace norms (面子, 关系, 酒桌文化)
- 🇺🇸 American tech culture (radical candor, data-driven, visibility)
- 🇯🇵🇰🇷🇮🇳 East Asian + South Asian behavioral overlays
- Cross-cultural friction points and bridge strategies

### 🕸️ Relationship Map (Multi-Persona)
- Build relationship networks across multiple saved personas
- Detect factions, alliances, and rivalry patterns
- Stakeholder sequencing: calculate the optimal order to approach people
- Multi-party strategy: coordinate across your entire org network
- Supports 20-30+ personas with unlimited relationships between them

---

## Scenarios That Work Beautifully

| You say | Persona Compass does |
|---------|---------------------|
| "David 抢了我的功劳怎么办" | Analyzes David's credit-claiming pattern → 3-tier defense strategy |
| "How do I get Sarah to prioritize my request?" | Loads Sarah's motivation profile → crafts the optimal ask |
| "模拟：我跟老板谈加薪" | Runs salary negotiation sim → scripts + timing + backup plan |
| "Compare David and Sarah's styles" | Side-by-side analysis → how to navigate both simultaneously |
| "Draft an email pushing back on the timeline" | Generates persona-calibrated pushback email with 3 variants |

---

## Commands

| Command | Description |
|---------|-------------|
| `/pc` or `/persona-compass` | Start new persona or enter main menu |
| `/pc list` | List all saved personas (codenames only) |
| `/pc [codename]` | Load and query an existing persona |
| `/pc new` | Create a new persona (assigns codename) |
| `/pc update [codename]` | Add new observations |
| `/pc prep [codename]` | 30-second pre-meeting cheat sheet |
| `/pc tone [codename]` | 5-second tone check before messaging |
| `/pc draft [cn] "[context]"` | Copy-pasteable message draft only |
| `/pc radar` | Weekly relationship scan |
| `/pc simulate [cn] [scenario]` | Full scenario simulation |
| `/pc compare [cn1] [cn2]` | Compare two personas |
| `/pc map` | Show relationship network |
| `/pc map analyze` | Full network + strategy analysis |
| `/pc map factions` | Detect alliance/rival groupings |

---

## Project Structure

```
persona-compass/
├── SKILL.md                          # Skill entry point
├── prompts/
│   ├── intake.md                     # Guided interview questions
│   ├── strategy_generator.md         # Strategy generation logic
│   └── correction_handler.md         # Evolution & correction handling
├── references/
│   ├── personality_frameworks.md     # Big Five, DISC, TKI, etc.
│   ├── cultural_contexts.md          # Cross-cultural communication
│   ├── scenario_templates.md         # 20+ scenario templates
│   ├── tag_translation.md            # Personality tag → behavior rules
│   └── relationship_map.md           # Multi-persona network system
├── profiles/
│   └── examples/
│       └── demo_profiles.json        # 3 example personas
├── personas/                         # User-created personas (gitignored)
│   └── _network/                     # Relationship map data
├── README.md
└── LICENSE
```

---

## Ethics & Philosophy

**This is a communication optimization tool, not a manipulation tool.**

- ✅ Understand people to communicate better
- ✅ Reduce friction and find win-win outcomes
- ✅ Prepare for difficult conversations constructively
- ❌ NOT for manipulation, deception, or control
- ❌ NOT a psychological diagnosis
- ❌ NOT a replacement for honest human conversation

All persona data stays local on your machine. No data collection. No telemetry.

---

## Contributing

PRs welcome! Especially:
- New scenario templates for underserved situations
- Cultural context additions for more regions
- Tag translations for new personality archetypes
- Translations (日本語, 한국어, etc.)

---

## Credits

Built with ❤️ by [@snowyowlmia](https://github.com/snowyowlmia)

MIT License © 2026

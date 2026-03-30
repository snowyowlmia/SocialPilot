# 🧭 Persona Compass

> **Navigate people like you navigate code.**
> **职场读心术，AI 帮你搞定难搞的人。**

Build AI-powered personality models of the people around you. Predict their behavior. Get actionable communication strategies. Win every conversation before it starts.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-green)](https://agentskills.io)
[![Bilingual](https://img.shields.io/badge/Language-EN%20%7C%20中文-blue)]()

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

```
Please read and follow the skill instructions at:
https://raw.githubusercontent.com/snowyowlmia/persona-compass/main/SKILL.md

Then help me analyze a person I work with.
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

### 🔒 Privacy-First Design
- **Codename system**: All files and commands use codenames, never real names
- No one glancing at your screen will know who you're analyzing
- Best on mobile or incognito tab — designed for sensitive workplace use
- All data stays local. No telemetry. No cloud sync.

### ⚡ Quick Commands (5-30 seconds)
Daily-use micro-interactions that build habitual usage:
- `/pc prep alpha` → 6-line pre-meeting cheat sheet
- `/pc tone alpha` → 1-line tone reminder before sending a message
- `/pc radar` → weekly relationship scan with suggested actions
- `/pc draft alpha "push back on deadline"` → copy-pasteable message, nothing else

### 🎯 Three-Tier Persona Building
- **Quick Sketch**: Name + role + 3 adjectives → instant persona card
- **Standard Profile**: 8-question guided interview → data-backed model
- **Deep Analysis**: Chat logs + incident reports → high-fidelity predictions

### 🧠 Multi-Framework Personality Modeling
- Big Five (OCEAN) with confidence scores
- DISC behavioral profiling
- Thomas-Kilmann conflict styles
- Motivation driver analysis
- Attachment theory (for close relationships)

### 🎭 Scenario Simulator
20+ built-in templates across 4 categories:

**Workplace — Collaboration:** deadline-slip · resource-request · cross-team-dependency · scope-change

**Workplace — Conflict:** credit-dispute · blame-deflection · territory-invasion · public-disagreement

**Workplace — Career:** promotion-ask · salary-negotiation (+ rejection recovery playbook) · skip-level-meeting · performance-review (+ self-review calibration by boss type)

**Workplace — Boundaries:** saying-no-to-boss · pushing-back-on-deadline · scope-creep-defense · protecting-work-life-balance

**Personal:** financial-discussion · parenting-disagreement · boundary-setting

### 💬 Communication Script Generator
Get ready-to-use messages calibrated to the person's psychology:
- Slack messages, emails, 1:1 talking points
- 2-3 strategic variants per scenario
- Each variant labeled with what it optimizes for

### 🌏 Cross-Cultural Intelligence
Built-in cultural context engine for:
- 🇨🇳 Chinese workplace norms (面子, 关系, 酒桌文化)
- 🇺🇸 American tech culture (radical candor, data-driven, visibility)
- 🇯🇵🇰🇷🇮🇳 East Asian + South Asian overlays
- Cross-cultural friction points and bridge strategies

### 📈 Self-Improving Model
- Track prediction accuracy over time
- Correct and refine with new observations
- Model confidence increases with usage

### 🕸️ Relationship Map (Multi-Persona)
- Build relationship networks between multiple personas
- Detect factions, alliances, and rivalry patterns automatically
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

# 🧭 Persona Compass

> **Navigate people like you navigate code.**
> **职场读心术，AI 帮你搞定难搞的人。**

Build AI-powered personality models of the people around you. Predict their behavior. Get actionable communication strategies. Win every conversation before it starts.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-green)](https://agentskills.io)
[![Bilingual](https://img.shields.io/badge/Language-EN%20%7C%20中文-blue)]()

---

**What makes this different from [colleague-skill](https://github.com/titanwings/colleague-skill)?**

colleague-skill creates a digital clone that **replaces** your colleague.
Persona Compass builds a model that helps you **navigate** them.

| | colleague-skill | Persona Compass |
|---|---|---|
| Goal | Simulate a person | Understand a person |
| Output | AI role-play | Strategy + scripts |
| Use case | "Work as if you're them" | "How do I get them to agree?" |
| Input | Feishu/DingTalk API (heavy) | Text description (zero-dep) |

---

## Quick Start

### Install

```bash
# Claude Code (project-level)
mkdir -p .claude/skills
git clone https://github.com/merrymango/persona-compass .claude/skills/persona-compass

# Claude Code (global)
git clone https://github.com/merrymango/persona-compass ~/.claude/skills/persona-compass
```

Zero dependencies. No API keys. No pip install. Just clone and go.

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
20+ built-in templates across workplace and personal contexts:
- Deadline slip · Credit dispute · Salary negotiation
- Territory defense · Skip-level prep · Team restructure
- Financial discussions · Boundary setting · And more

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
| `/pc list` | List all saved personas |
| `/pc [slug]` | Load and query an existing persona |
| `/pc new` | Create a new persona |
| `/pc update [slug]` | Add new observations |
| `/pc simulate [slug] [scenario]` | Run a scenario simulation |
| `/pc draft [slug] [context]` | Draft a persona-calibrated message |
| `/pc compare [slug1] [slug2]` | Compare two personas |
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

Inspired by [colleague-skill](https://github.com/titanwings/colleague-skill) for the concept of packaging interpersonal knowledge as AI skills.

Built with ❤️ by [MerryMango LLC](https://github.com/merrymango)

MIT License © 2026

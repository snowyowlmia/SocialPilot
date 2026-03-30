---
name: persona-compass
description: >
  Build personality models of colleagues, clients, friends, or family members and get
  AI-powered communication strategies. Use this skill whenever the user wants to:
  understand someone's personality, predict how someone will react, get advice on
  communicating with a difficult person, prepare for a tough conversation, navigate
  office politics, resolve interpersonal conflict, write a strategic message to
  someone specific, or simulate a scenario with a specific person. Also trigger when
  the user mentions: "how do I deal with", "how should I talk to", "what would X do if",
  "help me communicate with", "prepare me for a conversation with", MBTI, DISC,
  personality type, difficult coworker, toxic boss, or relationship dynamics.
  Supports both English and Chinese (中英双语). 职场读心术，AI 帮你搞定难搞的人。
version: 1.0.0
user-invocable: true
allowed-tools: Read, Write, Edit, Bash
---

# Persona Compass 🧭

> Navigate people like you navigate code.
> 职场读心术，AI 帮你搞定难搞的人。

Build a personality model → Predict behavior → Get actionable communication strategies.

**This is a communication optimization tool, not a manipulation tool.**
The goal is mutual understanding, reduced friction, and win-win outcomes.

---

## Trigger Conditions

Activate when the user says any of:

- `/persona-compass` or `/pc`
- "帮我分析一个人" / "帮我搞定某某"
- "How do I deal with [person]"
- "Help me communicate with [person]"
- "What would [person] do if..."
- "Prepare me for a conversation with [person]"
- Any reference to an existing persona profile by name/slug

Enter **query mode** when a persona already exists and user asks:
- A scenario question ("如果我跟他说...他会怎么反应？")
- A strategy request ("帮我写封邮件给他")
- A simulation ("模拟一下我跟他谈加薪")

Enter **evolution mode** when user says:
- "他不会这样" / "That's not right" / "Update [persona]"
- "我有新的信息" / "I observed something new"

---

## Language Detection

Detect the user's language from their first message.
- Chinese input → respond in Chinese throughout
- English input → respond in English throughout
- Mixed → follow the dominant language, keep technical terms in English

---

## Main Flow: Create New Persona

### Step 1: Quick Start (3 tiers)

Offer three input modes based on how much the user knows:

```
How well do you know this person?

  [A] Quick Sketch (30 seconds)
      Name + role + 3 personality adjectives
      → Generates a draft persona from archetypes

  [B] Standard Profile (5 minutes)
      Guided interview: 8 key questions
      → Generates a data-backed persona

  [C] Deep Analysis (10+ minutes)
      Paste chat logs, describe incidents, provide context
      → Generates a high-fidelity persona with prediction confidence scores
```

### Step 2: Information Collection

**For Quick Sketch [A]**, ask only:
1. **Name/alias** (required)
2. **Role & relationship** (e.g., "PM on my team", "my skip-level manager", "my spouse")
3. **Three words** that describe them (e.g., "controlling, data-driven, insecure")

**For Standard Profile [B]**, use the guided interview in `${SKILL_DIR}/prompts/intake.md`.
Core questions cover:
- Communication style (verbose vs terse, direct vs indirect)
- Decision-making pattern (data-driven vs gut-feel vs consensus)
- Conflict behavior (fight vs flight vs freeze vs negotiate)
- Motivation drivers (what do they care about most?)
- Stress response (what happens under pressure?)
- Trust signals (how do they build/lose trust?)
- Power dynamics (how do they relate to authority?)
- Known personality indicators (MBTI, DISC, zodiac — optional but useful as priors)

**For Deep Analysis [C]**, additionally accept:
- Pasted chat logs (Slack, Teams, WeChat, email)
- Described incidents ("Last week when X happened, he did Y")
- Work artifacts (how they write docs, run meetings, give feedback)
- Third-party observations ("Our mutual friend says he's...")

Read the full question sequences from `${SKILL_DIR}/prompts/intake.md`.

### Step 3: Personality Modeling

Load the personality framework reference: `${SKILL_DIR}/references/personality_frameworks.md`

Map collected information to a multi-dimensional model:

**Layer 1 — Core Traits (Big Five / OCEAN)**
Score each dimension 0-100 based on observed evidence.
Flag dimensions with low confidence (insufficient data).

**Layer 2 — Behavioral Patterns (DISC + Custom)**
Classify dominant interaction style: Dominance / Influence / Steadiness / Conscientiousness.
Add custom behavioral tags from the tag translation table in
`${SKILL_DIR}/references/tag_translation.md`.

**Layer 3 — Conflict & Stress Profile**
Thomas-Kilmann conflict mode: Competing / Collaborating / Compromising / Avoiding / Accommodating.
Stress response pattern: fight / flight / freeze / fawn.
Trigger points: what specifically sets them off.

**Layer 4 — Motivation & Values**
Primary drivers: Recognition / Security / Power / Achievement / Belonging / Autonomy.
What they protect: reputation, territory, relationships, process.

**Layer 5 — Cultural & Contextual Layer**
Load cultural context from `${SKILL_DIR}/references/cultural_contexts.md`.
Apply cultural overlays based on:
- National/ethnic background
- Corporate culture (big tech, startup, government, etc.)
- Generation / career stage
- Industry norms

### Step 4: Generate Persona Card

Output a structured persona card containing:

```
# [Name] — Persona Compass Card

## Quick Profile
- Role: [role & relationship to user]
- DISC Type: [type] | Conflict Style: [style]
- Primary Motivator: [motivator]
- Trust Level: [low/medium/high with user]

## Big Five Scores
- Openness: [score]/100 [confidence: high/medium/low]
- Conscientiousness: [score]/100
- Extraversion: [score]/100
- Agreeableness: [score]/100
- Neuroticism: [score]/100

## Behavioral Predictions
### Under Pressure
[specific predicted behaviors]

### When Receiving Bad News
[specific predicted behaviors]

### Trigger Points
[list of specific triggers with predicted reactions]

## Communication Playbook
### DO
[3-5 specific actionable tactics]

### DON'T
[3-5 specific things to avoid]

### Magic Phrases
[3-5 phrases calibrated to this person's psychology]

### Optimal Timing & Channel
[when and how to approach them]

## Confidence Assessment
- Overall model confidence: [percentage]
- Areas needing more data: [list]
```

### Step 5: Save Persona

Write persona files to `./personas/{slug}/`:
- `persona.md` — Full persona card
- `meta.json` — Structured metadata
- `observations.md` — Raw observations log
- `corrections.md` — Correction history

---

## Query Mode: Using an Existing Persona

When a persona exists and user asks a question:

1. Read `personas/{slug}/persona.md`
2. If corrections exist, read `personas/{slug}/corrections.md` and apply overrides
3. Determine query type:

**Scenario Simulation:**
- User describes a situation → Predict the person's reaction
- Load scenario templates from `${SKILL_DIR}/references/scenario_templates.md`
- Output: predicted reaction + recommended strategy + specific scripts

**Strategy Request:**
- User needs to accomplish something involving this person
- Output: step-by-step approach with timing, channel, framing
- Include ready-to-use message drafts (Slack/email/talking points)

**Relationship Dynamics:**
- User asks about multi-person dynamics
- Cross-reference multiple personas if available
- Output: power map + alliance/conflict analysis + optimal positioning

**Message Drafting:**
- User needs to write a specific message to this person
- Generate 2-3 variants with different strategic approaches
- Each variant labeled with what it optimizes for (e.g., "Preserve relationship" vs "Assert boundary")

---

## Evolution Mode: Update Persona

When user provides new information or corrections:

1. Read existing persona
2. Classify the update:
   - **New observation**: Append to observations.md, re-analyze relevant layers
   - **Correction**: "He didn't react like you predicted" → Update prediction model
   - **Context change**: "He got promoted" / "We had a falling out" → Adjust relationship dynamics
3. Track prediction accuracy in meta.json
4. Regenerate persona card with updated model

---

## Built-in Scenario Templates

Load from `${SKILL_DIR}/references/scenario_templates.md`. Categories include:

**Workplace — Collaboration:**
deadline-slip, resource-request, cross-team-dependency, scope-change, delegation

**Workplace — Conflict:**
credit-dispute, blame-deflection, territory-invasion, public-disagreement, passive-aggression

**Workplace — Career:**
promotion-ask, salary-negotiation, skip-level-meeting, performance-review, resignation

**Workplace — Leadership:**
difficult-feedback, team-restructure, underperformer-conversation, new-manager-transition

**Personal — Family:**
financial-discussion, parenting-disagreement, boundary-setting, difficult-news

**Personal — Social:**
favor-request, confrontation, apology, boundary-enforcement

---

## Relationship Map Mode

Build and navigate multi-persona networks for organizational strategy.
Load the full system from `${SKILL_DIR}/references/relationship_map.md`.

### When to Activate
- User mentions 2+ people in the same situation
- User asks about "office politics", "org dynamics", "how to navigate"
- User describes a multi-party conflict or needs multi-stakeholder buy-in
- User says `/pc map`

### Core Capabilities
1. **Network building**: Map relationships, trust levels, and power dynamics between personas
2. **Faction detection**: Identify alliances and rival groups automatically
3. **Stakeholder sequencing**: Calculate the optimal order to approach people for buy-in
4. **Multi-party strategy**: Generate coordinated strategies across relationship networks
5. **Influence path finding**: Find the shortest path to influence a target person

### Data Storage
Network data stored in `personas/_network/map.json`.
Each persona file remains independent; the map is an overlay.

### Capacity
- No hard limit on number of personas
- 20-30 personas is the practical sweet spot for most users
- Single query can cross-reference up to 6-8 personas simultaneously
- Relationship map supports unlimited edges between personas

---

## Management Commands

| Command | Action |
|---------|--------|
| `/pc list` | List all saved personas |
| `/pc [slug]` | Load and query a persona |
| `/pc new` | Create a new persona |
| `/pc update [slug]` | Add information to existing persona |
| `/pc compare [slug1] [slug2]` | Compare two personas side-by-side |
| `/pc simulate [slug] [scenario]` | Run a scenario simulation |
| `/pc draft [slug] [context]` | Draft a message for this person |
| `/pc map` | Show relationship network |
| `/pc map add [s1] [s2] [rel]` | Add a relationship between two personas |
| `/pc map analyze` | Full network analysis with strategy |
| `/pc map path [s1] [s2]` | Find influence path between two people |
| `/pc map factions` | Detect faction groupings |

---

## Ethical Guidelines (Built-in)

This skill operates under these non-negotiable principles:

1. **Optimize for mutual benefit.** Strategies should aim for win-win, not zero-sum.
2. **No manipulation.** Advice focuses on clear communication, not deception.
3. **Respect autonomy.** People are complex; models are approximations.
4. **Flag uncertainty.** When confidence is low, say so explicitly.
5. **Encourage direct communication.** AI-mediated strategy is a complement to,
   not a replacement for, honest human conversation.
6. **Privacy by design.** Persona files stay local. No data leaves the user's machine.

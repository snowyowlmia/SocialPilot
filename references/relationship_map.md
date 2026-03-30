# Relationship Map System

Build and navigate relationship networks between multiple personas.
Upgrade from single-person tactics to organizational strategy.

---

## Data Structure

Store relationship maps in `personas/_network/map.json`:

```json
{
  "nodes": [
    {
      "slug": "david-liu",
      "name": "David Liu",
      "role": "Senior PM",
      "org_level": 6,
      "team": "Platform",
      "influence_score": 7
    },
    {
      "slug": "sarah-kim",
      "name": "Sarah Kim",
      "role": "Engineering Director",
      "org_level": 8,
      "team": "Platform",
      "influence_score": 9
    }
  ],
  "edges": [
    {
      "from": "david-liu",
      "to": "sarah-kim",
      "relationship": "reports_to",
      "trust_level": "high",
      "dynamics": "David manages up aggressively; Sarah values his execution",
      "leverage": "Sarah trusts David's judgment on technical scope"
    },
    {
      "from": "user",
      "to": "david-liu",
      "relationship": "peer",
      "trust_level": "medium",
      "dynamics": "Competitive tension over project ownership",
      "leverage": "You have deeper technical expertise; he has more political capital"
    }
  ],
  "factions": [
    {
      "name": "Platform expansion camp",
      "members": ["david-liu", "sarah-kim"],
      "agenda": "Consolidate more projects under Platform org",
      "threat_to_user": "May absorb your project"
    }
  ],
  "user_position": {
    "allies": ["wei-zhang"],
    "neutral": [],
    "rivals": ["david-liu"],
    "gatekeepers": ["sarah-kim"]
  }
}
```

---

## Relationship Types

| Type | Code | Description |
|------|------|-------------|
| Reports to | `reports_to` | Direct reporting line |
| Peer | `peer` | Same level, same or different team |
| Skip-level | `skip_level` | Manager's manager or beyond |
| Mentor | `mentor` | Informal guidance relationship |
| Rival | `rival` | Competitive relationship |
| Ally | `ally` | Mutual support, shared interests |
| Gatekeeper | `gatekeeper` | Controls access to resources/decisions/people |
| Stakeholder | `stakeholder` | Has interest in your project outcomes |
| Sponsor | `sponsor` | Actively advocates for your career/project |

---

## Building the Map

### Step 1: Identify Key Players

Ask the user:
```
Let's map your professional network around [situation/goal].

Who are the key people involved? For each person, tell me:
1. Name and role
2. Their relationship to you (boss, peer, skip-level, etc.)
3. Their relationship to each other (if known)
4. Are they an ally, neutral, or rival to your goals?

让我们画出和[目标/情况]相关的人际关系网。
涉及到哪些关键人物？每个人告诉我：
1. 名字和角色
2. 和你的关系
3. 他们之间的关系（如果知道的话）
4. 对你的目标来说，他们是盟友、中立还是对手？
```

### Step 2: Map Dynamics

For each pair of people with a relationship, assess:
- **Power direction**: Who has more leverage?
- **Trust level**: How much do they trust each other?
- **Information flow**: Who tells whom what?
- **Alliance strength**: How stable is their relationship?
- **Shared interests**: What do they agree on?
- **Conflict points**: Where do they disagree?

### Step 3: Identify Patterns

Detect these common organizational patterns:

**Triangle dynamics (三角关系)**
- A-B are allies, B-C are allies, but A-C are rivals
- Strategy: Use B as a bridge; never force B to choose sides

**Information bottleneck (信息瓶颈)**
- One person controls information flow between groups
- Strategy: Build alternative information channels; never depend on a single source

**Shadow hierarchy (影子权力结构)**
- Formal hierarchy doesn't match actual influence
- Strategy: Identify who really makes decisions vs who signs off

**Coalition formation (联盟形成)**
- Multiple people aligning against a shared threat
- Strategy: Join early if aligned; build counter-coalition if threatened

**Kingmaker position (造王者位置)**
- One person's support determines outcomes for others
- Strategy: Understand what the kingmaker values; align your pitch accordingly

---

## Multi-Persona Strategy Generation

### Stakeholder Sequencing

When you need buy-in from multiple people, the ORDER matters.

**Algorithm:**
1. Score each stakeholder: `impact × accessibility × influence_on_others`
2. Identify dependencies: "Sarah won't agree unless David agrees first"
3. Find the **pivot person**: the one whose agreement unlocks others
4. Build the sequence: Easy wins first → Pivot person → Remaining holdouts

**Output format:**
```
Stakeholder Sequence for [goal]:

Round 1 (Build momentum):
  → Wei Zhang [ally, easy yes] — Approach via async doc review
  → Purpose: Get technical validation you can reference later

Round 2 (Secure the pivot):
  → Sarah Kim [gatekeeper, neutral] — 1:1 meeting, frame as her initiative
  → Purpose: Her support makes David's opposition untenable

Round 3 (Neutralize opposition):
  → David Liu [rival, likely no] — Group setting with Sarah present
  → Purpose: He won't fight this publicly if Sarah already endorsed
```

### Alliance Building

**Identify potential allies by checking:**
- Shared goals (who benefits if you succeed?)
- Shared enemies (who is also threatened by your rival?)
- Complementary strengths (what do you have that they need, and vice versa?)
- Reciprocity potential (can you trade favors?)

**Alliance activation script:**
```
"I've been thinking about [shared concern]. I think we're both impacted
by [shared threat/opportunity]. Would you be open to [specific collaboration]?
I think together we could [mutual benefit]."
```

### Conflict Resolution (Multi-Party)

When multiple personas are in conflict:

1. **Map each party's ACTUAL interest** (not stated position)
   - What do they really want? (often different from what they say)
   - What are they afraid of losing?
   - What would they trade?

2. **Find the non-zero-sum dimension**
   - Is there something that costs you nothing but matters to them?
   - Can you expand the pie before dividing it?
   - Is there a framing where everyone gets their #1 priority?

3. **Design the negotiation sequence**
   - Bilateral pre-meetings before any group discussion
   - Build agreements incrementally (small yeses before big asks)
   - Use a neutral facilitator if available

---

## Visualization Commands

| Command | Output |
|---------|--------|
| `/pc map` | Show the current relationship network |
| `/pc map add [slug1] [slug2] [relationship]` | Add a relationship |
| `/pc map analyze` | Full network analysis with strategy recommendations |
| `/pc map path [slug1] [slug2]` | Find influence paths between two people |
| `/pc map power` | Rank all personas by influence score |
| `/pc map factions` | Detect and display faction groupings |

---

## Network Analysis Output Format

```markdown
## Relationship Network Analysis

### Power Map
[Ranked list of personas by influence, with key relationships noted]

### Your Position
- Strengths: [what you control — information, expertise, relationships]
- Vulnerabilities: [where you're exposed — dependencies, information gaps]
- Opportunities: [alliances to build, pivots to make]
- Threats: [rival moves to watch for, coalition risks]

### Faction Analysis
- [Faction 1]: [members] — Agenda: [what they want]
  Your relationship to this faction: [aligned / neutral / opposed]
- [Faction 2]: [members] — Agenda: [what they want]

### Recommended Moves
1. [Specific action with specific person] — Timeline: [when]
   Expected outcome: [what this achieves]
2. [Next action]
3. [Next action]

### Scenarios to Prepare For
- If [person] does [action] → Your response: [strategy]
- If [faction] aligns against you → Your response: [strategy]
```

---

## Example: Project Ownership Defense

**User situation:** "David wants to absorb my project into his org. Sarah (his boss, my skip-level) hasn't decided yet. Wei is my tech ally but has no political power."

**Network analysis output:**

```
Power Map:
  Sarah Kim (Dir, influence: 9) — Decision maker
  David Liu (Sr PM, influence: 7) — Actively pursuing takeover
  You (IC/TL, influence: 5) — Project creator, technical owner
  Wei Zhang (Staff Eng, influence: 4) — Technical ally, no org power

Your SWOT:
  S: Deep project knowledge, stakeholder relationships, Wei's backing
  W: Lower org level than David, less political capital with Sarah
  O: Sarah values technical depth; your expertise is your leverage
  T: David is actively lobbying Sarah; time is against you

Recommended Sequence:
  1. TODAY: Brief Wei, ask him to write a technical assessment showing
     project complexity that only you can navigate (creates switching cost)
  2. THIS WEEK: Request 1:1 with Sarah. Frame: "I want to share my
     roadmap vision for [project]" — NOT "David is trying to take my project"
  3. IN THE 1:1: Show Sarah a 6-month roadmap that ties to her org goals.
     Make it clear that your continued ownership = her org's success
  4. ONLY IF NEEDED: Negotiate terms — "If consolidation makes sense,
     I want to retain tech lead role + quarterly VP updates"

Watch for: David scheduling a "reorg proposal" meeting with Sarah
before your 1:1. If you hear about this, accelerate Step 2.
```

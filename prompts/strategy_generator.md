# Strategy Generator

Generate actionable communication strategies based on a persona profile and a specific situation.

## Input Requirements
- Loaded persona profile (from `personas/{slug}/persona.md`)
- User's situation description
- User's goal (what they want to achieve)
- Constraints (relationship importance, time pressure, organizational context)

## Strategy Generation Framework

### Step 1: Situation Analysis
Parse the user's situation for:
- **Stakeholders**: Who is involved? Load all relevant personas.
- **Stakes**: What's at risk? (career, relationship, project, money)
- **Timeline**: How urgent? (immediate / days / weeks)
- **Power dynamics**: Who has leverage?
- **History**: Any relevant past interactions?

### Step 2: Persona-Based Prediction
For each persona involved, predict:
- Their **initial reaction** (first 5 minutes)
- Their **considered response** (within 24-48 hours)
- Their **underlying concern** (what they're really worried about)
- Their **best-case response** (what success looks like)
- Their **worst-case response** (what failure looks like)

### Step 3: Strategy Options
Generate 2-3 distinct strategic approaches. Each must:
- Have a clear **label** (e.g., "Direct approach" / "Indirect approach" / "Coalition building")
- Specify what it **optimizes for** (speed? relationship? outcome? safety?)
- Include **specific steps** with timing
- Include **ready-to-use language** (scripts, email drafts, talking points)
- Identify **risks** and **mitigation**
- Define **success indicators** (how to know it's working)
- Define **abort criteria** (when to switch strategies)

### Step 4: Message Drafting
When generating messages (email, Slack, talking points):

**Calibrate to persona's preferences:**
- D-type: Short, direct, bottom-line first, action-oriented
- I-type: Warm opening, enthusiasm, vision, collaborative language
- S-type: Gentle, reassuring, emphasize stability and support
- C-type: Detailed, precise, data-backed, logical structure

**Calibrate to cultural context:**
- Chinese workplace: More indirect, relationship-acknowledging, face-preserving
- American workplace: More direct, data-driven, action-oriented
- Cross-cultural: Bridge both styles explicitly

**Provide 2-3 variants when stakes are high:**
Variant A: Prioritizes [goal 1] — label clearly
Variant B: Prioritizes [goal 2] — label clearly
Variant C: Middle ground — label clearly

## Output Format

```markdown
## Strategy Analysis: [situation summary]

### What [persona] is likely thinking
[Prediction based on their profile — their perspective, not yours]

### Strategy 1: [Label] — optimizes for [what]
**Approach:** [1-2 sentence summary]
**Steps:**
1. [Specific action] — [timing]
2. [Specific action] — [timing]
3. [Specific action] — [timing]

**Script/Draft:**
[Ready-to-use message or talking points]

**Risks:** [what could go wrong]
**If it works:** [what to do next]
**If it doesn't:** [pivot strategy]

### Strategy 2: [Label] — optimizes for [what]
[Same structure]

### My Recommendation
Based on [persona]'s profile and your stated priorities, I'd recommend
Strategy [N] because [specific reasoning tied to persona traits].

### Watch For
- [Behavioral signal that indicates Strategy is working]
- [Behavioral signal that indicates Strategy is failing]
- [Trigger for switching to Plan B]
```

## Special Modes

### Multi-Persona Scenario
When multiple personas are involved:
1. Analyze each persona's likely position
2. Map alliances and conflicts between them
3. Identify the key person to influence first (sequencing)
4. Generate a stakeholder-by-stakeholder approach

### Win-Win Finder
When user explicitly asks for win-win:
1. Identify what each party truly cares about (not positions, but interests)
2. Find non-overlapping interests (things that cost you little but matter to them)
3. Propose creative trades
4. Frame the outcome so both sides feel they won

### Defensive Strategy
When user needs to protect something (credit, territory, position):
1. Map the threat vector (where is the attack coming from?)
2. Build defenses (documentation, alliances, visibility)
3. Create deterrents (make the cost of attack higher than the benefit)
4. Prepare response playbooks for likely attack scenarios

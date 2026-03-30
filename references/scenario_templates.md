# Scenario Templates

Each template defines: context setup, persona-specific prediction logic, and strategy output format.

---

## Workplace — Collaboration

### deadline-slip
**Setup:** You need to inform [persona] that a deadline will slip by [duration].
**Persona Variables:** conflict_style, stress_response, trust_level, motivation_driver
**Prediction Logic:**
- If D-type + Competing → Immediate blame-seeking, demands alternatives
- If C-type + Avoiding → Silent frustration, passive withdrawal
- If S-type + Accommodating → Accepts but builds resentment
**Output:** Predicted reaction + timing strategy + message draft + follow-up plan

### resource-request
**Setup:** You need [persona] to allocate resources (people/budget/time) to your project.
**Persona Variables:** motivation_driver, decision_style, power_dynamics
**Prediction Logic:**
- If motivated by Recognition → Frame as visibility opportunity
- If motivated by Security → Show low-risk, high-precedent approach
- If motivated by Power → Show how it expands their influence

### cross-team-dependency
**Setup:** Your project depends on [persona]'s team delivering something, and they're not prioritizing it.
**Persona Variables:** conflict_style, motivation_driver, hierarchy_behavior
**Strategy Options:**
1. Direct pressure (works for D-types, backfires for S-types)
2. Create shared accountability (works for C-types)
3. Escalate through mutual management (nuclear option)
4. Make their delivery a visible win for them (works universally)

### scope-change
**Setup:** You need to propose a significant scope change to [persona] who owns the current plan.
**Persona Variables:** openness, conscientiousness, territory_sensitivity
**Prediction Logic:**
- High Openness + Low Territory → Receptive to new ideas
- Low Openness + High Territory → Will resist; needs data and time

---

## Workplace — Conflict

### credit-dispute
**Setup:** [Persona] is claiming credit for work you did (or contributed significantly to).
**Strategy Tiers:**
1. Soft: Create visibility through follow-up documentation
2. Medium: Direct private conversation with specific examples
3. Hard: Escalate to shared management with evidence

### blame-deflection
**Setup:** [Persona] is deflecting blame for a failure onto you or your team.
**Counter-Strategy by Type:**
- Against Blame Shifter: Pre-document the timeline; send "alignment" emails before failures
- Against Political Player: Build alliances before the blame game starts
- Against Micromanager: Over-document your communications and decisions

### territory-invasion
**Setup:** [Persona] is attempting to take over ownership of your project/area.
**Defense Framework:**
1. Stakeholder lock: Ensure key stakeholders identify you as owner
2. Knowledge moat: Be the irreplaceable expert
3. Narrative control: Tell the story of this project to leadership before they do
4. Negotiate terms: If takeover is inevitable, negotiate conditions

### public-disagreement
**Setup:** [Persona] disagrees with you in a group meeting.
**Response by Persona Type:**
- D-type: Don't back down publicly; propose to "take it offline" with data
- I-type: Acknowledge their point, redirect to shared goals
- S-type: Rarely happens; if it does, it's serious — take very seriously
- C-type: Welcome the detail discussion; agree to review data together

---

## Workplace — Career

### promotion-ask
**Setup:** You want [persona] (your manager) to support your promotion.
**Framework:**
1. Build the case before the ask (evidence file)
2. Understand their promotion philosophy (merit vs loyalty vs visibility)
3. Make it easy: provide them the exact talking points they'd use
4. Timing: After a visible win, not during crises

### salary-negotiation
**Setup:** You're negotiating compensation with [persona].
**Persona-Adapted Approach:**
- Data-driven persona: Bring market data, comp surveys, competing offers
- Relationship persona: Frame as long-term partnership investment
- Power persona: Create perceived BATNA (best alternative)

### skip-level-meeting
**Setup:** You have a meeting with [persona], who is your manager's manager.
**Preparation by Persona Type:**
- D-type skip: Be concise, lead with impact, have specific asks ready
- I-type skip: Be personable, share enthusiasm, connect your work to vision
- C-type skip: Be precise, bring data, show thoroughness

### performance-review
**Setup:** You're giving or receiving a performance review with [persona].
**Giving to High-D:** Be direct, specific, future-focused. Don't soften too much.
**Giving to High-S:** Be gentle, acknowledge effort, give time to process.
**Receiving from anyone:** Listen fully before responding; ask for specific examples.

---

## Personal — Family

### financial-discussion
**Setup:** You need to discuss a significant financial decision with [persona] (partner/family).
**Framework:**
- Frame as shared goal, not unilateral decision
- Use concrete scenarios, not abstract principles
- Start small (pilot approach) to reduce resistance
- Respect their risk tolerance as valid, not wrong

### parenting-disagreement
**Setup:** You and [persona] disagree on a parenting approach.
**Framework:**
- Focus on the child's outcome, not who's "right"
- Acknowledge what the other approach gets right
- Propose a trial period rather than permanent change
- United front: "Let's decide together, then present together"

### boundary-setting
**Setup:** You need to set a boundary with [persona] (parent/sibling/friend).
**Framework by Attachment Style:**
- Secure: Direct statement, they'll respect it
- Anxious: Reassure the relationship isn't threatened, then state boundary
- Avoidant: Be clear and brief; don't over-explain (they'll withdraw)

---

## Output Format for All Scenarios

```markdown
## Scenario Analysis: [scenario_name]

### Predicted Reaction
Based on [persona]'s profile ([key traits]), they will most likely:
- Immediate reaction: [prediction]
- Within 24 hours: [prediction]
- Long-term pattern: [prediction]
- Confidence: [high/medium/low]

### Recommended Strategy
**Approach: [strategy_label]**
- Timing: [when to act]
- Channel: [how — email, Slack, 1:1, group]
- Framing: [how to position your message]
- Key phrases to use: [specific language]
- Things to avoid: [specific pitfalls]

### Ready-to-Use Script
[Draft message / talking points / email template]

### If It Doesn't Go As Predicted
- Plan B: [alternative approach]
- Escalation path: [when and how to escalate]
- Warning signs: [behaviors that indicate strategy isn't working]
```

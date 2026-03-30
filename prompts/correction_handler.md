# Correction & Evolution Handler

## Trigger Detection

Activate when user says:
- "他不会这样" / "That's not right" / "He wouldn't do that"
- "实际上他..." / "Actually, he..."
- "你预测错了" / "Your prediction was wrong"
- "我有新的观察" / "I observed something new"
- "他最近变了" / "He's changed recently"

## Correction Types

### Type 1: Prediction Miss
User reports that a predicted behavior didn't match reality.

**Process:**
1. Ask: "What did you expect based on my prediction, and what actually happened?"
2. Identify which persona dimension was wrong
3. Adjust the relevant score/tag
4. Log: `{date, scenario, predicted, actual, dimension_adjusted, new_value}`
5. Recalculate confidence scores for affected predictions

### Type 2: New Observation
User provides new behavioral data.

**Process:**
1. Classify: Does this confirm, refine, or contradict existing model?
2. If confirms: Increase confidence on relevant dimensions
3. If refines: Add nuance (e.g., "He's direct, but only with peers, not with superiors")
4. If contradicts: Flag for review, ask clarifying questions
5. Append to observations.md with timestamp

### Type 3: Context Change
Relationship or situation has changed fundamentally.

**Process:**
1. Identify what changed (promotion, new team, personal event, conflict)
2. Reassess power dynamics and trust levels
3. Re-run relevant prediction models
4. Update persona card with change noted
5. Alert user to predictions that may now be invalid

## Accuracy Tracking

In meta.json, track:
```json
{
  "predictions_made": 15,
  "predictions_verified": 8,
  "predictions_correct": 6,
  "accuracy_rate": 0.75,
  "corrections_applied": 3,
  "last_updated": "2026-03-30T10:00:00Z",
  "confidence_trend": "improving"
}
```

## Evolution Rules

1. Never delete original observations — append corrections
2. Weight recent observations more heavily than older ones
3. After 3+ corrections on the same dimension, significantly revise the score
4. If accuracy drops below 50%, suggest a persona rebuild
5. Track which scenarios produce the most prediction misses

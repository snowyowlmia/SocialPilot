# Persona Intake Interview

## Quick Sketch Mode (Tier A)

Ask these 3 questions only:

```
1. What's their name or alias? (I'll use this as an identifier)
   他/她叫什么？（可以用代号）

2. What's their role and how do they relate to you?
   Examples: "Senior PM, same team", "My manager's manager", "My spouse"
   他/她是什么角色？和你什么关系？

3. Give me 3 words or phrases that capture who they are.
   Examples: "controlling, data-obsessed, secretly insecure"
   用3个词描述这个人的核心特质。
```

After collecting, confirm: "Based on this, here's my initial read: [summary]. Sound right?"

---

## Standard Profile Mode (Tier B)

Ask these 8 questions in conversational order. Skip any the user can't answer.
Adapt language to match the user's (Chinese or English).

### Q1: Communication Style
```
How does this person typically communicate?
- Are they verbose or terse? (长篇大论 vs 惜字如金)
- Direct or indirect? (直来直去 vs 暗示绕弯)
- Written or verbal preference? (偏好文字沟通还是当面说)
- How fast do they typically respond? (回复速度)
```

### Q2: Decision Making
```
How do they make decisions?
- Data-driven: needs numbers and evidence (数据驱动)
- Gut-feel: trusts instinct (凭感觉)
- Consensus: needs everyone to agree (追求共识)
- Authority: defers to hierarchy (看上面的意思)
- Speed: makes fast calls, sometimes wrong (快刀斩乱麻)
```

### Q3: Conflict Behavior
```
When there's a disagreement, what do they typically do?
- Fight: push back hard, escalate (硬刚)
- Flight: avoid the topic, go silent (回避)
- Freeze: shut down, stop responding (僵住)
- Fawn: agree on surface, resist passively (表面同意暗中抵抗)
- Negotiate: try to find middle ground (寻求妥协)

Can you describe a specific conflict you witnessed or experienced with them?
能描述一个你亲历或目睹的具体冲突吗？
```

### Q4: Motivation Drivers
```
What does this person care about most? (Pick top 2)
- Recognition: being seen as competent/important (被认可)
- Security: stability, predictability, not being blindsided (安全感)
- Power: influence, control, territory (权力/控制)
- Achievement: results, impact, shipping things (成就感)
- Belonging: being liked, team harmony (归属感)
- Autonomy: independence, not being micromanaged (自主权)
```

### Q5: Stress Response
```
What happens when they're under pressure? (deadline, crisis, high stakes)
- Do they become more controlling or more hands-off?
- Do they communicate more or less?
- Do they blame others, blame themselves, or focus on solutions?
- Any specific behaviors you've noticed? (加班到深夜? 开始甩锅? 变得暴躁?)
```

### Q6: Trust Dynamics
```
How does this person build trust?
- Through competence: they trust people who deliver (能力型信任)
- Through loyalty: they trust people who are "on their team" (忠诚型信任)
- Through transparency: they trust people who share information (透明型信任)
- Through time: slow to trust, but loyal once earned (慢热型信任)

What makes them lose trust?
- Being surprised / out of the loop (被蒙在鼓里)
- Incompetence / missed deadlines (能力不行)
- Disloyalty / going around them (背后搞小动作)
- Dishonesty / inconsistency (不诚实/前后不一)
```

### Q7: Power & Hierarchy
```
How do they relate to authority?
- With superiors: deferential / equal / challenging?
  (对上级: 顺从/平等/敢于挑战)
- With peers: collaborative / competitive / territorial?
  (对同级: 合作/竞争/守地盘)
- With subordinates: empowering / controlling / dismissive?
  (对下级: 赋权/控制/忽视)
```

### Q8: Known Indicators (Optional)
```
Do you know any of the following? (All optional, skip freely)
- MBTI type? (e.g., INTJ, ENFP)
- DISC profile? (D, I, S, C)
- Zodiac / 星座?
- Enneagram type?
- Any self-described personality traits?
  (他们怎么描述自己？)
```

---

## Deep Analysis Mode (Tier C)

In addition to the Standard Profile questions, prompt for:

### Raw Data Sources
```
I can analyze any of the following to build a deeper model:

1. Chat logs — paste Slack/Teams/WeChat/email conversations
   (粘贴聊天记录，我会分析用词习惯、语气变化、回复模式)

2. Key incidents — describe 2-3 specific situations and how they reacted
   (描述2-3个关键事件及他们的反应)

3. Third-party views — what do others say about this person?
   (别人怎么评价这个人？)

4. Work artifacts — how do they write documents? run meetings?
   (他们写文档/开会的风格是什么？)

5. Observed patterns — any recurring behaviors you've noticed?
   (你注意到的反复出现的行为模式？)
```

### Chat Log Analysis Dimensions
When analyzing pasted chat logs, extract:
- **Response latency patterns**: fast on some topics, slow on others?
- **Vocabulary and tone shifts**: formal vs casual, when does it change?
- **Initiative patterns**: do they start conversations or only respond?
- **Emoji/reaction usage**: expressive or reserved?
- **Group vs 1:1 behavior**: different persona in different contexts?
- **Topic avoidance**: what topics do they redirect or ignore?
- **Power language**: "I decided" vs "we could" vs "they said"
- **Hedging frequency**: "maybe", "I think", "probably" vs definitive statements

---

## Post-Intake Processing

After collecting information:

1. Summarize key findings back to user for confirmation
2. Flag any contradictions in the data ("You said they're direct, but the chat logs show a lot of hedging — which is more typical?")
3. Identify gaps: "I'm least confident about their [dimension]. If you observe [specific behavior], that would help refine the model."
4. Ask: "Ready to generate the persona card? Or want to add anything?"

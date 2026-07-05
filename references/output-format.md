# Output Format

Deliver in this order. **The Prompt comes first** — that's what the user copies. Design notes come after, for users who want to understand the reasoning.

## Template

### [Point Title] | [Visual Type]

#### 📋 The Prompt

> Target model: [GPT Image 2 / Nano Banana / MJ v7] | Quality: [low/medium/high]

```text
[Complete 5-block prompt, copy-paste ready. No markdown formatting inside.
 User should be able to select this block and paste directly into the image generator.]
```

---

#### Design notes

- **推荐理由**: [1-2 sentences on why this type/module combo fits this topic]
- **知识点拆解**:
  - 学习目标: ①[drawable goal] ②[drawable goal] ③[drawable goal]
  - 模块选择: [module1] → [module2] → ... (5-8 modules)
- **图文文案** (on-image copy budget):
  - 主标题：[≤ 12 chars]
  - 副标题：[≤ 24 chars]
  - 重点项：[point 1] / [point 2] / ... (each ≤ 8 chars)
  - 金句：[≤ 16 chars]
- **变体** (variants):
  - (1) [Text-reduced version — focus on visual metaphor]
  - (2) [Pure background — no text, for manual editing]
  - (3) [Alternative layout — different type or arrangement]

## Formatting rules

1. **The Prompt is always in a code block** — triple backticks, no language tag (so it copies clean).
2. **The Prompt must be pure** — no inline labels, no commentary. Just the prompt text.
3. **Design notes are separated by `---`** — so the user knows where the copyable part ends.
4. **Model hint** goes above the code block, in a blockquote.
5. **Bilingual title** when possible — Chinese title + English gloss helps GPT Image 2 treat the topic seriously.
6. **Card number** for series — if part of a multi-card set, prefix the title with `卡片 N/M`.

# Visual Type Guide & Module Pool

Two approaches to choosing what goes on the image: **preset types** (fast, for common patterns) and **module assembly** (flexible, for unique content).

## Approach 1: Preset Types (Fast Path)

Choose one type automatically unless the user names a type. Good for standard educational patterns.

| Type | Chinese | Use When | Typical Modules |
|------|---------|----------|-----------------|
| `graphic-card` | 图文卡片 | One concept, definition, or quick memory point | 定义 + 3要点 + 金句 |
| `knowledge-map` | 知识地图 | System, roadmap, capability map, classification | 中心 + 4-6分支 |
| `three-column` | 三栏结构 | 3 dimensions, methods, modules, or categories | 标题 + 3并列卡片 |
| `scene-story` | 场景故事 | Teacher/student/parent/workplace scenario | 角色 + 任务 + AI帮助 + 人的判断 |
| `analogy` | 生活类比 | Abstract concept or technical term | 概念 + 类比 + 映射 + 提醒 |
| `process-flow` | 流程图 | Steps, method, workflow, input-to-output | 起点 + 4-8步 + 终点 |
| `right-wrong` | 正误对比 | Misconception, bad vs good | 错误 ← → 正确 + 结论 |
| `intent-explainer` | 意图解释 | Boundary, value, "what it is / is not" | 是什么 + 不是什么 + 为什么重要 + 何时用 |

### Selection hints (keyword → type)

- "什么是 X" → `graphic-card`; if abstract, use `analogy`
- "X 的体系 / 路线 / 能力" → `knowledge-map`
- "三种 / 三类 / 三步" → `three-column`
- "如何做 / 步骤 / 流程" → `process-flow`
- "误区 / 错误 / 不要这样" → `right-wrong`
- "老师 / 学生 / 家长怎么用" → `scene-story`
- "边界 / 为什么重要 / 什么时候用" → `intent-explainer`

## Approach 2: Module Assembly (Flexible Path)

For content that doesn't fit neatly into a preset type, assemble from the **module pool**. Pick 5-8 modules that best serve the learning goals.

### Module Pool

| Module | Chinese | What it does | Example content |
|--------|---------|--------------|-----------------|
| `definition` | 定义 | One-sentence core definition | "Token = AI 处理文字的最小单位" |
| `example` | 例子 | Concrete real-world instance | "Apple → Ap-ple → 2 tokens" |
| `steps` | 步骤 | Sequential process | "1.输入 2.拆分 3.计算 4.输出" |
| `comparison` | 对比 | X vs Y side by side | "Token vs Word" |
| `pitfall` | 误区 | Common misunderstanding | "Token ≠ Word（不是按词拆的）" |
| `analogy` | 类比 | Life metaphor for abstract concept | "像搭积木一样理解" |
| `gold-sentence` | 金句 | Memorable takeaway | "先查后答" |
| `rating` | 评分 | Quick assessment or metric | "难度 ★★☆ / 实用 ★★★" |
| `flow-arrow` | 流程箭头 | Directional connection between modules | A → B → C |
| `zoom-detail` | 局部放大 | Zoomed-in detail of a key element | Leaf cross-section labeled |
| `warning` | 警告 | Risk or caution note | "⚠ 注意上下文窗口限制" |
| `mnemonic` | 记忆口诀 | Rhyme or keyword summary | "查-增-生，三步走" |

### Assembly guidelines

1. **Always start with `definition` or `analogy`** — anchor the concept first.
2. **End with `gold-sentence` or `mnemonic`** — give the viewer a takeaway.
3. **Cap at 5-8 modules** — beyond 8, the model starts dropping labels.
4. **Use `pitfall` or `warning` for at least one module** — this is what makes the image feel authored, not generated.
5. **Connect modules with `flow-arrow`** when there's a sequence; leave as independent cards when there isn't.

### Assembly example

**Topic**: "Prompt Engineering 入门"

```
Selected modules (6):
  definition  → "Prompt = 给 AI 的指令"
  analogy     → "像给实习生写需求文档"
  steps       → "1.角色 2.上下文 3.任务 4.格式"
  pitfall     → "误区：越长越好（错，清晰比长度重要）"
  example     → "好：'你是一位老师，请用3句话解释X'"
  gold-sentence → "清晰 > 长度"
```

This produces a richer card than forcing it into a single preset type.

## Type → Layout Pattern Mapping

Each type has a natural spatial layout. Specify this in the CONTENT BLOCKS section of the 5-block prompt:

| Type | Spatial layout |
|------|---------------|
| `graphic-card` | Central metaphor + 3 surrounding point cards |
| `knowledge-map` | Center node + 4-6 branches radiating outward |
| `three-column` | Top title + 3 equal vertical columns |
| `scene-story` | Horizontal scene, AI as floating panel/card |
| `analogy` | Left: life scene, Right: tech mapping, arrows between |
| `process-flow` | Horizontal or vertical chain of 4-8 step cards |
| `right-wrong` | Left-right split, conclusion strip at bottom |
| `intent-explainer` | 2×2 quadrant (是什么/不是什么/为什么/何时用) |

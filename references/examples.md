# Example Outputs

Three full examples showing the complete workflow. Each follows the output format: **prompt first, design notes after**.

---

## Example 1: Analogy — "什么是 Token"

**User input**: 把 Token 讲给家长听，用生活类比

### Token：AI 的积木 | Analogy

#### 📋 The Prompt

> Target model: GPT Image 2 | Quality: high

```text
Create a horizontal 1536×1024 educational knowledge card.

CANVAS: clean pearl-white background (#F8F9FA), soft pastel blue primary (#7DB3D9), warm coral secondary accent. Generous whitespace, soft clay-texture feel.

HEADER: THE TEXT READS: "Token：AI 的积木" — main title 42pt bold, centered top. Subtitle directly below: THE TEXT READS: "理解 AI 如何阅读文字" — 22pt, muted gray.

CONTENT BLOCKS (5 rounded cards, soft clay style, numbered badges, connected by thin arrows):
1) 类比: THE TEXT READS: "一句话 = 一堆积木" — shows a sentence breaking into colorful translucent Lego-like bricks, each labeled with a short syllable.
2) 定义: THE TEXT READS: "Token = 最小文字单位" — a single brick enlarged with a label.
3) 例子: THE TEXT READS: "Apple = Ap + ple" — two bricks side by side.
4) 误区: THE TEXT READS: "Token ≠ 按词拆分" — crossed-out word icon.
5) 金句: THE TEXT READS: "像搭积木一样理解 AI" — centered at bottom, 20pt, accent color.

VISUAL: soft claymorphism illustration, rounded edges, macaron color palette, friendly flat icons. Thin charcoal-grey connector arrows (1pt, single-headed). Style like a modern education-technology infographic, warm but not childish.

CONSTRAINTS: every visible text string is rendered verbatim — THE TEXT READS exactly as specified above. No garbled text, no misspelled characters, no Lorem ipsum, no placeholder text. No dense small text, no complex backgrounds, no cyberpunk, no neon glow. No watermarks, no platform logos. The image looks like a published educational handout, not a marketing poster. High-fidelity Chinese typography, crisp text rendering.
```

---

#### Design notes

- **推荐理由**: 抽象概念用触觉类比最直观——家长能秒懂"拆字"过程。
- **知识点拆解**:
  - 学习目标: ①文字被拆成积木块 ②每块有编号 ③积木数量有限
  - 模块选择: `analogy` → `definition` → `example` → `pitfall` → `gold-sentence`
- **变体**: (1) 去文字纯积木图 (2) 纯白背景版 (3) 等距3D版

---

## Example 2: Process Flow — "Vibe Coding 流程"

**User input**: 做一张 Vibe Coding 从想法到交付的流程图

### Vibe Coding 流程 | Process Flow

#### 📋 The Prompt

> Target model: GPT Image 2 | Quality: medium | thinking: medium

```text
Create a horizontal 1536×1024 educational process-flow diagram.

CANVAS: clean white background (#FFFFFF), tech-blue primary (#2563EB), soft green secondary accent (#10B981). Modern glassmorphism feel with subtle transparency.

HEADER: THE TEXT READS: "Vibe Coding 流程" — 44pt bold, top-left. Subtitle: THE TEXT READS: "从想法到交付的极简路径" — 22pt, gray.

CONTENT BLOCKS (7 rounded step cards in a horizontal left-to-right flow, connected by directional arrows):
1) THE TEXT READS: "明确目标" — target icon.
2) THE TEXT READS: "补充上下文" — document icon.
3) THE TEXT READS: "输出 Plan" — checklist icon.
4) THE TEXT READS: "生成初版" — code icon.
5) THE TEXT READS: "人工 Review" — magnifying-glass icon.
6) THE TEXT READS: "交付成果" — package icon.
7) THE TEXT READS: "沉淀 Skill" — bookmark icon.
Bottom strip: THE TEXT READS: "把想法变成交付" — centered, 24pt, accent blue.

VISUAL: isometric 3D step cards, glassmorphism panels, thin teal connector arrows with directional indicators. Each card has a numbered circle badge and a simple flat icon. Style like a clean architecture diagram, not a children's illustration.

CONSTRAINTS: every visible text string is rendered verbatim — THE TEXT READS exactly as specified. No garbled text, no misspelled characters, no Lorem ipsum. No dense small text, no complex backgrounds, no cyberpunk. No watermarks. High-fidelity Chinese typography.
```

---

#### Design notes

- **推荐理由**: 工作流需要清晰步骤序列，箭头连接让人秒懂顺序。
- **知识点拆解**:
  - 学习目标: ①从模糊想法开始 ②经过 Plan/生成/Review ③最终交付
  - 模块选择: `steps`(7步) → `flow-arrow` → `gold-sentence`
- **变体**: (1) 压缩为 4 步简化版 (2) 竖版流程 (3) 圆形循环版

---

## Example 3: Knowledge Map — "AI Agent 的构成"

**User input**: AI Agent 是由什么组成的？做一张知识地图

### Agent：全能助手 | Knowledge Map

#### 📋 The Prompt

> Target model: GPT Image 2 | Quality: high

```text
Create a horizontal 1536×1024 educational knowledge map.

CANVAS: clean light gray background (#F8F9FA), navy primary (#1E3A5F), with individual module accent colors (blue, green, orange, purple, teal, gold).

HEADER: THE TEXT READS: "Agent 不只是模型" — 40pt bold, top-center. Subtitle: THE TEXT READS: "大脑加规划加工具加记忆" — 22pt, gray.

CONTENT BLOCKS (center node with 6 surrounding branch cards connected by thin lines):
Center: THE TEXT READS: "Agent" — large, 36pt, in a circular node.
Branch 1 (top): THE TEXT READS: "LLM 大脑" — brain icon.
Branch 2 (top-right): THE TEXT READS: "规划流程" — flowchart icon.
Branch 3 (bottom-right): THE TEXT READS: "工具箱" — toolbox icon.
Branch 4 (bottom): THE TEXT READS: "上下文记忆" — memory-chip icon.
Branch 5 (bottom-left): THE TEXT READS: "沙盒环境" — sandbox icon.
Branch 6 (top-left): THE TEXT READS: "反馈循环" — circular-arrow icon.
Bottom strip: THE TEXT READS: "从想到做的跨越" — centered, 20pt.

VISUAL: flat UI knowledge map, thin connector lines (1pt navy), each branch is a rounded card with a flat icon and short label. Center node is larger and darker. No tangled lines, clean radial layout. Style like a professional architecture diagram.

CONSTRAINTS: every visible text rendered verbatim — THE TEXT READS exactly as specified. No garbled text, no misspelled characters, no Lorem ipsum. No messy lines, no sci-fi aesthetic, no cyberpunk. No watermarks. High-fidelity Chinese typography, crisp text rendering.
```

---

#### Design notes

- **推荐理由**: 复杂系统用整体地图最直观——一眼看到所有组件及关系。
- **知识点拆解**:
  - 学习目标: ①Agent 有多个组成部分 ②每个部分有不同职责 ③协同工作
  - 模块选择: center `definition` + 6 × `example` branches + `gold-sentence`
- **变体**: (1) 减少到 4 分支简化版 (2) 放射状 3D 版 (3) 左右树状结构版

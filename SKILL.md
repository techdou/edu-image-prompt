---
name: edu-image-prompt
description: Generate student-friendly educational image prompts from knowledge points for AI literacy lessons, PPT slides, public-account posts, handouts, livestream decks, and classroom knowledge cards. Use when the user asks to turn a concept, lesson point, outline, or teaching topic into a clean visual prompt, 图文卡片, 知识地图, 流程图, 课堂配图, 课程素材, 生图 Prompt, or 知识卡片. Outputs a structured 5-block prompt optimized for GPT Image 2, Nano Banana, and Midjourney with reliable Chinese text rendering.
---

# edu-image-prompt

Turn any educational knowledge point into a professional, structured image-generation prompt. The output is a **copy-paste-ready prompt** that produces clean, readable educational visuals — not decorative posters.

## Use This Skill For

- **Teaching Materials**: PPT slides, knowledge cards, process flows, lecture handouts.
- **Concept Visualization**: Explaining abstract theories, technical terms, or complex systems.
- **Social Media Education**: Xiaohongshu cards, public-account posts, livestream decks.

## Interactive Workflow (MANDATORY)

When the user triggers this skill, you MUST NOT generate the final prompt immediately. Execute this 4-step SOP:

### Step 1: The Inquiry (问询式交互)

Present a multiple-choice menu. Use `ask_user` tool if available, or print the markdown menu and wait.

Ask the user to select:

1. **领域美学 (Domain Style)**: [A] 科技/AI (玻璃态) | [B] 商学/管理 (黑金商务) | [C] 人文/历史 (复古杂志) | [D] 少儿/心理 (亲和黏土)
2. **质感渲染 (Rendering Medium)**: [A] 等距 3D (Isometric) | [B] 扁平 UI (Flat UI) | [C] 场景实拍+AR面板 (Editorial Photo)
3. **展示平台 (Platform Layout)**: [A] PPT/直播 (16:9) | [B] 朋友圈/小红书 (3:4) | [C] 通用讲义 (16:9)
4. **目标模型 (Target Model)**: [A] GPT Image 2 (默认，中文渲染最佳) | [B] Nano Banana (快速批量) | [C] Midjourney v7 (艺术插画) | [D] 不指定

### Step 2: Knowledge Decomposition (知识点拆解) — THE CRITICAL STEP

Before writing any prompt, decompose the knowledge point into **3-4 drawable visual elements** (学习目标). This is the step most people skip, and the #1 reason AI educational images fail.

Ask yourself: *What 3-4 things should a student be able to point to after seeing this image for 30 seconds?*

```
示例 — "什么是 Token"
✅ 好的学习目标（可绘制）：
  1. 一句话被拆成多块积木（Token 化过程）
  2. 每块积木有编号/标签（Token = 最小单位）
  3. 积木数量有上限（上下文窗口限制）

❌ 坏的学习目标（不可绘制）：
  "学生理解 Token 的概念"
```

Then select **5-8 content modules** from the module pool in `type-guide.md`:
`定义 → 例子 → 步骤 → 对比 → 误区 → 类比 → 金句 → 评分`

### Step 3: Prompt Generation (生成)

Apply the user's style choices + the decomposed modules to the **5-block structured prompt template** (see `prompt-rules.md`):

```
[1] CANVAS — 尺寸、背景、主色调
[2] HEADER — 精确标题文本 + 定位句（引号包裹）
[3] CONTENT BLOCKS — 5-8 个命名模块
[4] VISUAL — 线条/图标/箭头/配色风格
[5] CONSTRAINTS — "THE TEXT READS:..." + 禁止项
```

Apply model-specific techniques from `model-guide.md` (e.g., GPT Image 2 的 thinking 模式、Midjourney 的 --ar 参数).

### Step 4: Quality Check (质量验证) → Output

Before outputting, run the validation checklist in `validation.md`. Then deliver following the format in `output-format.md`.

## The Golden Rules

- **Analogy First**: For abstract concepts, always anchor to a tactile life analogy before the technical framing.
- **Text Must Render**: Every Chinese string on the image must be wrapped in `THE TEXT READS: "..."` — this is the #1 accuracy lever for CJK text rendering.
- **Structure Before Style**: Describe canvas/layout/blocks BEFORE visual style. Starting with "beautiful, vibrant..." makes the AI fill gaps randomly.
- **5-8 Modules Max**: Below 5 looks empty; above 8 starts losing labels even on GPT Image 2.
- **Pure Output**: The final prompt must be copy-pasteable without extra formatting labels.

## References (Read When Needed)

- **5-block prompt template & text rendering**: [prompt-rules.md](references/prompt-rules.md)
- **Model-specific guide (GPT Image 2 / Nano Banana / MJ)**: [model-guide.md](references/model-guide.md)
- **Visual types & module pool**: [type-guide.md](references/type-guide.md)
- **Style parameters**: [style-config.md](references/style-config.md)
- **Example outputs**: [examples.md](references/examples.md)
- **Output format**: [output-format.md](references/output-format.md)
- **Validation checklist**: [validation.md](references/validation.md)
- **Troubleshooting (pitfalls & fixes)**: [troubleshooting.md](references/troubleshooting.md)

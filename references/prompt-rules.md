# 5-Block Prompt Template & Text Rendering Rules

This is the core engine of the skill. Every prompt must follow the 5-block structure, in this exact order.

## The 5-Block Template

```
[1] CANVAS — orientation, background, dominant accent color.
[2] HEADER — exact title text (quoted) + one-line positioning sentence.
[3] CONTENT BLOCKS — 5-8 named modules, each with a label and short content.
[4] VISUAL — line weight, icon style, arrow style, palette accents.
[5] CONSTRAINTS — "THE TEXT READS: ..." for every label + negative rules.
```

### Why this order matters

- **Canvas first**: The model commits to layout before content. If you describe the topic before the canvas, you get random aspect ratios.
- **Header before sections**: The H1 anchors hierarchy. Without it, all modules render at the same visual weight and the image reads flat.
- **5-8 modules is the sweet spot**: Below 5 looks empty; above 8 starts losing labels even on GPT Image 2.
- **Visual block before constraints**: Style descriptions placed early get over-applied; placed late they act as a finishing pass.
- **Constraints at the bottom, in imperative voice**: The model treats them as guardrails rather than suggestions.

## Text Rendering — THE #1 Accuracy Lever

The single most important technique for Chinese text accuracy: **wrap every on-image string in `THE TEXT READS: "..."`**. This comes from the OpenAI cookbook and has been validated across 300+ generations.

### Text rendering checklist

| Technique | Example | Why |
|-----------|---------|-----|
| **Quote literal text** | `THE TEXT READS: "Token：AI 的积木"` | Forces exact spelling, prevents mojibake |
| **Specify font hierarchy** | `Main title 48pt bold, subtitle 24pt, body 18pt` | Prevents all text rendering at same weight |
| **ALL CAPS for English** | `THE TEXT READS: "RAG = RETRIEVAL + GENERATION"` | English renders more reliably in caps |
| **Spell out brand/uncommon words** | `THE TEXT READS: "G-P-T" (spelled G-P-T)` | Letter-by-letter improves accuracy |
| **State exact position** | `Title at top-center, subtitle directly below` | Prevents text piling in one corner |
| **One language per label** | `标题用中文 "知识卡片", 不要中英混排` | Mixed scripts increase garbling risk |

## Copy Limits (Character Budget)

Chinese text rendering on images degrades rapidly with length. Enforce strict limits:

| Element | Max Characters | Notes |
|---------|---------------|-------|
| 主标题 (Main title) | ≤ 12 Chinese chars | Shorter is always better |
| 副标题 (Subtitle) | ≤ 24 Chinese chars | One line max |
| 重点项 (Key point) | ≤ 8 Chinese chars each | Fragments, not sentences |
| 金句 (Gold sentence) | ≤ 16 Chinese chars | Memorable takeaway |
| **Total on-image text** | ≤ 60 Chinese chars | Hard ceiling for readability |

If the knowledge point requires more text, split into a **2-3 card series** instead of cramming one image.

## Mandatory Keywords & Negatives

Every prompt must include these:

**Mandatory positives**:
- The exact use-case mode: `educational infographic`, `knowledge card`, `study handout`, or `classroom diagram`
- Layout direction: `clean layout`, `high whitespace`, `clear hierarchy`
- Text legibility: `crisp typography`, `readable labels`

**Mandatory negatives** (append at end of CONSTRAINTS block):
- `No garbled text, no misspelled characters, no Lorem ipsum, no placeholder text`
- `No dense small text, no text walls`
- `No complex backgrounds, no cyberpunk, no neon glow`
- `No commercial advertisement aesthetic, no marketing poster vibe`
- `No watermarks, no platform logos`

## Example: Assembling a 5-Block Prompt

**Input**: "把 RAG 讲给家长听，用生活类比"

**Step 2 output (decomposed modules)**: 类比(图书馆查资料) → 定义(RAG三步) → 流程(检索→增强→生成) → 金句

**Assembled prompt**:

```
Create a horizontal 1536×1024 educational knowledge card.

CANVAS: clean pearl-white background (#F8F9FA), soft blue primary accent (#4A90D9), warm orange secondary accent. Generous whitespace, paper-texture feel.

HEADER: THE TEXT READS: "RAG：给 AI 配一个图书管理员" — main title 42pt bold, centered top. Subtitle directly below: THE TEXT READS: "像查图书馆一样理解 AI 怎么找答案" — 22pt, muted gray.

CONTENT BLOCKS (5 rounded cards, numbered, connected by thin arrows):
1) 生活类比: THE TEXT READS: "就像你去图书馆" — shows a person at a library desk finding a book, simple flat icon style.
2) 第一步 检索: THE TEXT READS: "先去书架找相关书" — icon of searching bookshelves.
3) 第二步 增强: THE TEXT READS: "把找到的内容做笔记" — icon of writing notes.
4) 第三步 生成: THE TEXT READS: "基于笔记回答问题" — icon of AI answering.
5) 金句: THE TEXT READS: "RAG = 先查后答" — centered at bottom, 20pt, accent color.

VISUAL: flat vector illustration, friendly rounded icons, thin charcoal-grey connector arrows (1pt, single-headed), numbered circle badges on each card. Style like a modern education-technology infographic, not a children's book.

CONSTRAINTS: every visible text string is rendered verbatim — THE TEXT READS exactly as specified above. No garbled text, no misspelled characters, no Lorem ipsum, no placeholder text. No dense small text, no complex backgrounds. No watermarks, no platform logos. The image looks like a published educational handout, not a marketing poster. High-fidelity Chinese typography, crisp text rendering.
```

## Style Consistency for Series

When generating a multi-card series (e.g., a course module), lock the style parameters:

1. Keep the same CANVAS block (same background, accent colors, aspect ratio)
2. Keep the same VISUAL block (same icon style, arrow style, line weight)
3. Only swap the HEADER and CONTENT BLOCKS
4. Add a card number label: `THE TEXT READS: "卡片 1/3"` at top corner

This produces a visually coherent set rather than random images.

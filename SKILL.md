---
name: edu-image-prompt
description: >-
  Generates structured 5-block image-generation prompts for educational visuals
  from any knowledge point. Produces copy-paste-ready prompts optimized for
  GPT Image 2, Nano Banana, and Midjourney with reliable Chinese text
  rendering. Use when the user wants to turn a concept, lesson, or topic into
  a knowledge card (图文卡片), infographic (知识地图), process diagram (流程图),
  classroom illustration (课堂配图), or social-media study card (知识卡片), or
  asks for a 生图 Prompt / AI 配图 / 教学素材.
---

# edu-image-prompt

Turns any educational knowledge point into a **copy-paste-ready image-generation prompt** that produces clean, readable educational visuals — not decorative posters.

## When to use

- Turning a concept / lesson point / outline into a visual prompt
- Creating PPT slides, knowledge cards, process diagrams, lecture handouts
- Concept visualization for abstract theories or technical terms
- Social-media education cards (Xiaohongshu, public-account posts)

## When NOT to use

- User wants the image itself generated directly (not a prompt)
- User wants a photo edit or image retouching
- User wants a logo, brand asset, or marketing creative

## Workflow (3 steps)

### Step 1 — Style setup

If the user already specified a style ("用黏土风", "做小红书卡片"), skip to Step 2.

Otherwise, use **sensible defaults** and proceed — do NOT block on a menu:

| Parameter | Default | Full menu (only if user asks "有哪些选项") |
|-----------|---------|---------------------------------------------|
| 领域美学 | 科技/AI 玻璃态 | A)科技 B)商学黑金 C)人文复古 D)少儿黏土 |
| 质感渲染 | 扁平 UI | A)等距3D B)扁平UI C)场景实拍+AR |
| 展示平台 | 通用讲义 16:9 | A)PPT/直播 B)小红书3:4 C)通用16:9 |
| 目标模型 | GPT Image 2 | A)GPT Image 2 B)Nano Banana C)Midjourney D)不指定 |

> Rationale: most users just want a good card fast. Give them the default, let them override.

### Step 2 — Knowledge decomposition (CRITICAL)

Fill this template. Do NOT skip — this is the step that separates a useful educational image from a pretty-but-empty poster.

**Decomposition table** (copy and fill):

| # | Visual goal (must be drawable) | Module | On-image text (≤8 chars) |
|---|-------------------------------|--------|--------------------------|
| 1 | [具体可绘制元素, e.g. "一句话被拆成积木块"] | analogy / definition / ... | "≤8字" |
| 2 | ... | ... | ... |
| 3 | ... | ... | ... |
| 4 | (optional) ... | ... | ... |

**Module pool** (pick 5-8, see `type-guide.md` for details):
`definition` · `example` · `steps` · `comparison` · `pitfall` · `analogy` · `gold-sentence` · `rating` · `flow-arrow` · `zoom-detail` · `warning` · `mnemonic`

**Validation checkpoint** — before proceeding, verify:
- [ ] Every goal is drawable (if any reads like "understand X", rewrite it more specifically)
- [ ] 5-8 modules selected (fewer = empty, more = labels get dropped)
- [ ] At least one `pitfall` or `warning` module (makes the image feel authored)
- [ ] If the topic is abstract, an `analogy` module is included

### Step 3 — Generate, validate, and deliver

1. **Assemble** the 5-block prompt using the template in `prompt-rules.md`, applying the style from Step 1 and modules from Step 2.
2. **Apply model-specific techniques** from `model-guide.md` (e.g., GPT Image 2 thinking mode, MJ `--ar` parameter).
3. **Quick-check** against the validation rules below.
4. **Deliver** following the output format (prompt first, design notes after).

## The 5-block prompt structure

Every prompt must follow this order (see `prompt-rules.md` for full template):

```
[1] CANVAS       — dimensions, background, dominant accent color
[2] HEADER       — exact title text wrapped in THE TEXT READS: "..."
[3] CONTENT BLOCKS — 5-8 named modules with labels
[4] VISUAL       — line weight, icon style, arrow style, palette
[5] CONSTRAINTS  — text accuracy rules + negative keywords
```

**The #1 text-rendering rule**: wrap every Chinese string in `THE TEXT READS: "..."`. This is the biggest accuracy lever for CJK text (source: OpenAI cookbook, validated across 300+ generations).

## Output format

Deliver in this order (prompt first — that's what the user copies):

1. **📋 The Prompt** — the complete 5-block prompt in a code block, copy-paste ready
2. **Design notes** (brief) — recommended type, decomposition summary, model hint, variants

See `output-format.md` for the exact template.

## Quick validation rules

Before delivering, verify:
- Prompt follows 5-block order (CANVAS first)
- Every CJK label wrapped in `THE TEXT READS: "..."`
- Total on-image Chinese text ≤ 60 characters
- Font hierarchy specified (≥ 3 tiers)
- Negative constraints included (no garbled text, no Lorem ipsum, no watermarks)
- If target is Midjourney: no Chinese text on image

Full checklist: `validation.md`. Pitfall fixes: `troubleshooting.md`.

## References (one level deep — read when needed)

- [prompt-rules.md](references/prompt-rules.md) — 5-block template + text rendering rules
- [model-guide.md](references/model-guide.md) — GPT Image 2 / Nano Banana / MJ v7 adaptation
- [type-guide.md](references/type-guide.md) — 8 preset types + 12-module pool
- [style-config.md](references/style-config.md) — domain aesthetics + color palettes
- [examples.md](references/examples.md) — 3 complete worked examples
- [output-format.md](references/output-format.md) — output structure template
- [validation.md](references/validation.md) — full quality checklist
- [troubleshooting.md](references/troubleshooting.md) — 6 common pitfalls and fixes

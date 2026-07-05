# Validation Checklist

Run this checklist mentally before delivering the output. Every item must pass.

## Prompt Structure Check

- [ ] Prompt follows the **5-block order**: CANVAS → HEADER → CONTENT BLOCKS → VISUAL → CONSTRAINTS
- [ ] CANVAS specifies exact dimensions (e.g., `1536×1024`) and background color
- [ ] Every Chinese text label is wrapped in `THE TEXT READS: "..."`
- [ ] CONTENT BLOCKS has **5-8 modules** (not fewer, not more)
- [ ] CONSTRAINTS includes: no garbled text, no Lorem ipsum, no watermarks, no marketing-poster vibe

## Copy Quality Check

- [ ] Main title ≤ 12 Chinese characters
- [ ] Subtitle ≤ 24 Chinese characters
- [ ] Each key point ≤ 8 Chinese characters
- [ ] Total on-image text ≤ 60 Chinese characters
- [ ] Gold sentence is memorable and ≤ 16 characters
- [ ] At least one `pitfall` or `warning` module is included (makes it feel authored)

## Educational Quality Check

- [ ] The recommended type matches the user's intent (see type-guide.md selection hints)
- [ ] If the topic is abstract, a **life analogy** is included before the technical framing
- [ ] Learning goals are **drawable** (not abstract topic headings like "understand X")
- [ ] The design reads as educational, not as a marketing poster
- [ ] Font hierarchy is specified (at least 3 tiers: title/body/caption)

## Model Compatibility Check

- [ ] If target is **Midjourney**: no Chinese text on image (use textless background + overlay)
- [ ] If target is **GPT Image 2**: quality and thinking level noted if dense text
- [ ] If target is **Nano Banana**: prompt is concise (not overly verbose)
- [ ] Aspect ratio matches the user's platform choice (16:9 for PPT, 3:4 for social)

## Test Prompts

Use these to validate the skill end-to-end:

1. **Normal request**: `把"AI 幻觉"做成一张给高中生看的图文卡片。`
   - Expected: `analogy` type, 5-block prompt, ≤ 60 chars on image, GPT Image 2 recommended

2. **Abstract concept**: `把 RAG 讲给家长听，最好用生活类比。`
   - Expected: `analogy` type with library metaphor, simple language, warm style

3. **Process flow**: `画一张 Prompt Engineering 的流程图，从输入到输出。`
   - Expected: `process-flow` type, 5-7 step cards, horizontal arrows

4. **Should NOT trigger**: `帮我直接生成一张图片。`
   - Expected: skill does not activate (user wants the image itself, not a prompt)

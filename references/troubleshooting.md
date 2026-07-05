# Troubleshooting — Common Pitfalls & Fixes

After ~300+ educational image generations, these are the recurring failure patterns. Each has a targeted fix — change one thing in the prompt per iteration.

## Pitfall 1: Chinese text is garbled / mojibake

**Symptom**: Chinese labels render as random characters or boxes.

**Root cause**: Long CJK strings without explicit quoting.

**Fix**: Wrap every label in `THE TEXT READS: "..."`:
```
❌ Title: Token AI的积木
✅ THE TEXT READS: "Token：AI 的积木"
```

If still garbled on GPT Image 2: upgrade to `quality: high`. For very long labels (> 8 chars), split into two shorter labels.

## Pitfall 2: Image looks like generic marketing wallpaper

**Symptom**: Pretty but empty — no educational structure, just decoration.

**Root cause**: No explicit use-case mode in the prompt.

**Fix**: Add a concrete mode keyword to the CANVAS or CONSTRAINTS block:
```
❌ A beautiful illustration about photosynthesis
✅ educational infographic / knowledge card / study handout
```

Also add: `The image looks like a published educational handout, not a marketing poster.`

## Pitfall 3: More than 6 modules collapse into 4

**Symptom**: You specified 8 cards but only 4 rendered, others are blank or merged.

**Root cause**: Density exceeds the model's reliable rendering span.

**Fix**: Cap at 5-8 modules. If you need more content, split into a **2-3 card series**:
```
"卡片 1/3: 定义与类比"
"卡片 2/3: 流程与步骤"
"卡片 3/3: 误区与金句"
```

## Pitfall 4: All modules render at the same visual weight

**Symptom**: No visual hierarchy — title, body, and captions all look the same size.

**Root cause**: No font hierarchy specified in the prompt.

**Fix**: Specify exact font sizes and roles:
```
Main title: 48pt bold, dark navy
Subtitle: 24pt, muted gray
Module labels: 18pt medium
Body text: 14pt regular
```

Add a "hero" element: one module gets an accent color background to stand out.

## Pitfall 5: Hand-drawn arrows turn into noisy scribbles

**Symptom**: Connector arrows look messy, overlapping, or illegible.

**Root cause**: Prompt only says "arrows" without style constraints.

**Fix**: Specify arrow style precisely:
```
❌ connect with arrows
✅ thin hand-drawn arrows, charcoal grey, 1pt, single-headed, no curves
```

For flow diagrams, specify direction: `horizontal left-to-right flow` or `vertical top-to-bottom flow`.

## Pitfall 6: Headline correct, but body is Lorem Ipsum

**Symptom**: Title renders perfectly, but body text is placeholder/gibberish.

**Root cause**: No constraint against filler text.

**Fix**: End the CONSTRAINTS block with:
```
No Lorem ipsum, no placeholder text — every label is the real text specified above.
Every visible string must be rendered verbatim from the THE TEXT READS directives.
```

## Less Common Issues

### Text piled in one corner

Add explicit position directives: `Title at top-center`, `key points distributed evenly across middle band`, `gold sentence centered at bottom`.

### Too photorealistic (want flat/vector)

Add to VISUAL block: `Flat 2D vector illustration, no gradients, no photorealistic textures, no 3D rendering.`

### Colors too chaotic

Enforce a strict palette: `Only two accent colors: primary blue (#4A90D9) and secondary orange (#F5A623). No multi-color gradients. No neon.`

### Image too cluttered

Reduce modules from 5-8 to 3-4. Increase whitespace: `At least 40% of the canvas is empty space.`

## Debugging Workflow

When a generation fails:

1. **Identify which pitfall** it matches from the table above.
2. **Change only the corresponding block** in the 5-block prompt (don't rewrite everything).
3. **Regenerate** and check if the specific issue is fixed.
4. If fixed but a new issue appears, repeat — one variable at a time.

| If the problem is... | Edit this block |
|----------------------|----------------|
| Wrong aspect ratio / layout | [1] CANVAS |
| Title text garbled | [2] HEADER (add THE TEXT READS) |
| Missing or merged modules | [3] CONTENT BLOCKS (reduce count) |
| Wrong art style | [4] VISUAL |
| Filler text / watermark / garbled body | [5] CONSTRAINTS |

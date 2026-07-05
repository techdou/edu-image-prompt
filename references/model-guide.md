# Model Adaptation Guide — GPT Image 2 / Nano Banana / Midjourney v7

Different models need different prompt strategies. Choose the target model in Step 1 of the SOP, then apply the techniques below.

## Quick Comparison

| Feature | GPT Image 2 | Nano Banana | Midjourney v7 |
|---------|-------------|-------------|---------------|
| Chinese text rendering | ✅ Best (multilingual) | ✅ Good | ⚠️ Poor (avoid CJK on image) |
| Layout planning | ✅ Thinking mode | ⚠️ Basic | ❌ No |
| Resolution | Any (up to 3840px) | Fixed sizes | --ar parameter |
| Style consistency | ✅ Up to 10 images/request | ✅ Fast batch | ✅ --sref reference image |
| Best for | Educational cards, infographics | Quick batch cards | Artistic illustrations |
| Speed | Medium | Fast | Medium |
| Text-heavy images | ✅ Use quality: high | ⚠️ Medium | ❌ Avoid |

## GPT Image 2 (Recommended Default)

Best overall for educational content with Chinese text. Use as the default when the user doesn't specify a model.

### Key techniques

**1. Thinking mode**: For complex layouts (knowledge maps, process flows), the model can plan before rendering. This dramatically improves layout accuracy:
```
quality: medium, thinking: medium  ← practical default for diagrams
quality: high, thinking: high      ← for dense text / final delivery
quality: low                       ← for fast iteration / layout testing
```

**2. Flexible resolution**: Any size where both edges are multiples of 16, max edge < 3840px, ratio ≤ 3:1:
```text
PPT/直播:     1536×1024  (16:9 horizontal)
小红书:       1080×1440  (3:4 vertical)
知识卡:       1024×1536  (2:3 vertical, exam-handout aesthetic)
超宽信息图:   2560×1024  (5:2 ultra-wide)
```

**3. THE TEXT READS quoting**: This is the single biggest accuracy lever. Wrap every Chinese label:
```
THE TEXT READS: "Token：AI 的积木"    ← model renders exact characters
Token AI的积木                       ← model may garble or paraphrase
```

**4. Quality tiers**:
- `quality: low` — fast iteration, test layout composition. Costs ~25% of high.
- `quality: medium` — sweet spot for most production work. Clean textures, readable text.
- `quality: high` — for small text, dense panels, print-ready output. 4× cost of medium.

**5. Local edit fidelity**: After generating one card, you can ask for targeted edits ("keep layout, swap content block 3") with high fidelity. This makes batch production viable.

### GPT Image 2 prompt suffix

Append to the end of the 5-block prompt:
```
Render in high-fidelity Chinese typography. Crisp text rendering. No artifacts.
```

## Nano Banana (Fast Batch)

Best when you need many cards quickly (e.g., a full course module series). Good text rendering, fast generation.

### Key techniques

**1. Lock the style for series**: Generate one reference card, then reuse the exact same CANVAS + VISUAL blocks. Only swap HEADER and CONTENT BLOCKS.

**2. Simpler prompts work better**: Nano Banana prefers concise prompts over verbose ones. Compress the 5-block template:
```
Vertical knowledge card, 3:4. Title "RAG：给 AI 配图书管理员".
5 numbered cards: 类比→检索→增强→生成→金句.
Flat vector, blue/orange accents, white background, rounded icons.
Text must render exactly as written. No garbled text, no watermarks.
```

**3. Test with medium quality first**: Iterate at medium, switch to high for final delivery.

## Midjourney v7 (Artistic Illustration)

Best for cover art, metaphors, and scene illustrations. **Avoid for Chinese text on images** — use it for textless visual metaphors, then overlay text in Canva/Figma.

### Key techniques

**1. Use --ar for aspect ratio**:
```
--ar 16:9    PPT/livestream
--ar 3:4     Xiaohongshu/social
--ar 21:9    ultra-wide banner
```

**2. Use --sref for style consistency**:
```
gentle watercolor illustration of [concept], soft earth tones, warm diffused light, minimal background, educational and calming, no text --ar 16:9 --sref [reference_image_url]
```

**3. Template pattern for series**:
Save the first successful prompt as a template with a `[SUBJECT]` placeholder. Drop in new subjects for each card:
```
a gentle flat-vector illustration of [SUBJECT], soft blue and orange palette, white background, rounded icons, educational infographic style, no text --ar 3:4
```

**4. No Chinese text**: If the card needs Chinese text, generate a textless background with MJ, then add text in Canva/PowerPoint/Figma.

### MJ prompt pattern

```
[style] illustration of [subject], [color palette], [mood], [composition], no text --ar [ratio]
```

## Model Selection Decision Tree

```
Is there Chinese text on the image?
├── Yes → GPT Image 2 (best) or Nano Banana (fast batch)
│   └── Dense text / small labels? → GPT Image 2 quality: high
└── No (textless metaphor or English only)
    ├── Artistic / painterly style? → Midjourney v7
    └── Clean infographic? → GPT Image 2 or Nano Banana
```

## Cross-Model Text Accuracy Tips

Regardless of model, these improve text rendering:

1. **Shorter is better**: ≤ 60 total Chinese characters on one image.
2. **One font size per role**: Don't mix 5 different sizes. Use 3 tiers max (title/body/caption).
3. **High contrast**: Dark text on light background, or vice versa. Avoid mid-gray on light-gray.
4. **Avoid special characters**: Parentheses, brackets, and symbols increase garbling. Use simple punctuation.
5. **Spell out acronyms**: Instead of `RAG`, write `THE TEXT READS: "R-A-G"` if the model struggles.

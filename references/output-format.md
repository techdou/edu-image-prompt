# Output Format

For each knowledge point, output the following structure after completing the 4-step SOP.

## Standard Output Structure

### [Point Title] | [Visual Type]

- **推荐理由**: Why this visual type / module combination works for this specific point.

- **知识点拆解** (Step 2 output):
  - 学习目标: ①[drawable goal 1] ②[drawable goal 2] ③[drawable goal 3]
  - 模块选择: [module1] → [module2] → ... (5-8 modules)

- **图文文案** (On-Image Copy):
  - 主标题：[Main Title, ≤ 12 Chinese chars]
  - 副标题：[Short Explanation, ≤ 24 Chinese chars]
  - 重点项：[Point 1] / [Point 2] / ... (each ≤ 8 chars)
  - 金句：[Memory Line, ≤ 16 chars]

- **The Prompt**: The complete 5-block structured prompt, copy-paste ready. Must include:
  - [1] CANVAS with exact dimensions and colors
  - [2] HEADER with `THE TEXT READS: "..."` for every label
  - [3] CONTENT BLOCKS (5-8 named modules)
  - [4] VISUAL style specification
  - [5] CONSTRAINTS with text accuracy and negative rules

- **变体** (Variants):
  - (1) Text-reduced version (focus on visual metaphor, minimal labels)
  - (2) Pure background version (no text, for manual editing in Canva/Figma)
  - (3) Alternative layout version (different type or module arrangement)

## Formatting Rules

1. **The Prompt section must be pure** — no markdown formatting inside, no extra labels. The user should be able to select and copy-paste it directly into the image generator.
2. **Use a code block** (```) for The Prompt to make copying easy.
3. **Bilingual title** when possible: Chinese title + English gloss helps GPT Image 2 treat the topic as serious/educational.
4. **Model hint**: If the user selected a target model in Step 1, note it above The Prompt:
   ```
   > Target model: GPT Image 2 | Recommended quality: high | thinking: medium
   ```
5. **Card number** for series: If this is part of a multi-card set, add `卡片 N/M` at the top.

---
name: edu-image-prompt
description: Generate student-friendly educational image prompts from knowledge points for AI literacy lessons, PPT slides, public-account posts, handouts, livestream decks, and classroom knowledge cards. Use when the user asks to turn a concept, lesson point, outline, or teaching topic into a clean visual prompt, 图文卡片, 知识地图, 流程图, 课堂配图, 课程素材, or 生图 Prompt.
---

# edu-image-prompt

Turn any educational knowledge point into a professional, structured image-generation prompt. Focus on transforming abstract concepts into highly readable, visually clean educational materials.

## Use This Skill For

- **Teaching Materials**: Creating PPT slides, knowledge cards, process flows, and lecture handouts.
- **Concept Visualization**: Explaining abstract theories, technical terms, or complex systems across any subject (Tech, History, Science, Business).
- **Personal IP/Branding**: Designing educational posters and digital name cards for educators and creators.

## Visual Standards (The "Golden Rules")

- **Layout**: Clear hierarchy with a "Title + Subtitle + Key Points + Gold Sentence" structure.
- **Text Rendering**: Explicitly define the Chinese text to be rendered on the image (optimized for models like DALL-E 3).
- **Negative Constraints**: Strictly exclude garbled text, dense small text, complex backgrounds, cyberpunk, neon glow, and commercial advertisement aesthetic.

## Interactive Workflow (MANDATORY)

When the user triggers this skill, you MUST NOT generate the final prompt immediately. Instead, act as a Visual Director and execute this Standard Operating Procedure (SOP):

### Step 1: The Inquiry (问询式交互)
Present the user with a multiple-choice menu to define the visual style. Use `ask_user` tool if available, or simply print the markdown menu and wait for the user's reply.

**Ask the user to select:**
1. **领域美学 (Domain Style)**: [A] 科技/AI (现代玻璃态) | [B] 商学/管理 (极简黑金商务) | [C] 人文/历史 (复古杂志风) | [D] 少儿/心理 (亲和黏土风)
2. **质感渲染 (Rendering Medium)**: [A] 等距 3D (Isometric) | [B] 扁平 UI 界面 (Flat UI) | [C] 场景实拍+AR面板 (Editorial Photo)
3. **展示平台 (Platform Layout)**: [A] PPT/直播 (16:9, 右侧留白防讲师遮挡) | [B] 朋友圈/小红书 (3:4, 中心大字报防裁切) | [C] 通用讲义 (16:9, 居中平衡)
4. *(Optional)* Any specific color palette preferences?

### Step 2: Generation (生成)
Once the user replies with their choices (e.g., "1B, 2C, 3A"), apply the specific style configurations from `style-config.md` to the generation process.

### Step 3: Output (交付)
Generate the final response following the structure in `output-format.md`. Ensure the chosen Domain, Medium, and Layout parameters are explicitly written into the final english image-generation prompt.

## Output Format

For each knowledge point, output:

### [Point Title] | [Visual Type]
- **Recommended Reason**: Why this visual type works for this point.
- **On-Image Copy**:
  - 主标题：[Large Title]
  - 副标题：[Brief Explanation]
  - 重点项：[Point 1] / [Point 2] / ...
  - 金句：[Memory Line]
- **The Prompt**: [A pure, complete, and ready-to-use image-generation prompt, integrating the user's style choices]
- **Variants**: (1) Text-reduced version; (2) Pure background version; (3) Icon-centric version.

## Core Quality Rules

- **Analogy First**: For abstract concepts, always use a simple life analogy.
- **Direct & Clean**: Avoid decorative clutter. Every visual element must serve the educational goal.
- **Pure Output**: Ensure the "The Prompt" section is copy-pasteable without extra formatting labels.

## References

- Interactive Style Parameters: [style-config.md](references/style-config.md)
- Visual type selection: [type-guide.md](references/type-guide.md)
- Prompt and copy rules: [prompt-rules.md](references/prompt-rules.md)
- Example outputs: [examples.md](references/examples.md)


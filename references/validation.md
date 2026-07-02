# Validation

## Quality Checklist

Before responding, check:

- The output includes a complete image-generation prompt.
- The recommended type matches the user's intent.
- Chinese text is short enough for image rendering.
- The prompt states exact text, layout, style, and negative constraints.
- The design is educational and readable, not a marketing poster.
- If the topic is abstract, the answer includes a life analogy before the formal framing.

## Test Prompts

Use these to validate the skill:

1. Normal request: `把“AI 幻觉”做成一张给高中生看的图文卡片。`
2. Edge request: `把 RAG 讲给家长听，最好用生活类比。`
3. Should not trigger: `帮我直接生成一张图片。`

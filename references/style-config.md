# Advanced Style Configuration

This document defines the advanced visual parameters that can be applied to `edu-image-prompt` generations.

## 1. Dynamic Domain Aesthetics (领域美学)
Adapt the underlying mood based on the subject matter:
- **Tech / AI Literacy (科技/AI)**: Glassmorphism, 3D elements, clean digital vibe, neon blue/green accents (used sparingly).
- **Business / Management (企业管理/商学)**: Corporate Minimalist. Dark mode options, high contrast, sharp geometric cuts, gold/navy blue accents.
- **Humanities / History (人文/历史)**: Museum Editorial. Beige paper texture backgrounds, serif typography metaphors, retro/muted color tones.
- **Kids / Psychology (少儿/心理学)**: Playful Claymorphism or Soft Pastel Vector. Rounded edges, macaron colors, high-affinity scenes.

## 2. Palette Engineering (精准调色板)
Enforce strict color palettes to prevent chaotic colors:
- **Default EdTech**: "Background: #F8F9FA (Pearl White), Primary: Low-saturation theme color, Secondary: Complementary warm tone. Strictly no high-saturation multi-color gradients."
- **Corporate Dark**: "Background: #121212 (Deep Navy/Black), Primary: Champagne Gold, Secondary: Silver gray."

## 3. Rendering Mediums (质感渲染)
Control the artistic 3D/2D style:
- **Isometric 3D (等距视角)**: Best for process flows and knowledge maps. Looks like structural building blocks from a god's-eye view.
- **Flat UI/UX Design (扁平界面风)**: Best for cards and comparisons. Looks like a clean iOS interface screenshot.
- **Editorial Photography (杂志摄影风)**: Best for covers and quotes. Blends real-world scenes (e.g., a real desk) with floating AR data panels.

## 4. Platform-Aware Layouts (多平台构图)
Control composition based on where the image will be shown:
- **PPT / Livestream (16:9)**: Enforce "Right/Left area reserved for speaker video overlay" (大量留白防讲师人像遮挡).
- **Social Media / Xiaohongshu (3:4)**: "Magazine cover layout, text centered, high visual impact, crop-safe margins."
- **Standard Handout (16:9 or 4:3)**: Centered or balanced, max readability.

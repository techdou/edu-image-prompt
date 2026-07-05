# Changelog

## v2.1.0 — Anthropic Skills format compliance + UX optimization

### Changed

- **SKILL.md SOP simplified** from 4 steps to 3 steps (merged generate + validate + deliver into one step). Reduced Agent execution overhead.
- **Step 1 style setup**: replaced forced 4-question menu with **sensible defaults** (科技/AI, 扁平UI, 16:9, GPT Image 2). Full menu only shown when user explicitly asks for options. Follows Anthropic guideline: "give defaults, not excessive options."
- **Step 2 decomposition**: replaced open-ended "ask yourself" prompt with a **template table** (Visual goal / Module / On-image text) + validation checkpoint. Lowers Agent freedom for error-prone step.
- **Output reordered**: The Prompt now delivered first in a code block (what the user copies). Design notes (reasoning, decomposition, variants) moved after a `---` separator.
- **frontmatter description** rewritten to comply with Anthropic spec: third person, ≤1024 chars, clear "what + when to use" structure.
- **style-config.md** slimmed: resolution/canvas info moved to model-guide.md. style-config now focuses purely on aesthetics (domain mood + color palettes + rendering mediums).

### Added

- **REVIEW.md**: self-assessment scorecard, Anthropic compliance checklist, boundary declarations, and roadmap.
- Anthropic Skills specification compliance verification (name format, description format, progressive disclosure, one-level-deep references, forward-slash paths).

### Fixed (from v2.0.0 review)

- Removed `ask_user` tool-specific reference (now platform-agnostic).
- Eliminated content overlap between style-config.md and model-guide.md.

## v2.0.0 — 5-block structured prompts + model adaptation + module system

### Added

- **5-block structured prompt template** (`prompt-rules.md` rewritten): CANVAS → HEADER → CONTENT BLOCKS → VISUAL → CONSTRAINTS. Based on production-validated GPT Image 2 workflow (300+ generations).
- **`THE TEXT READS: "..."` quoting technique**: the #1 accuracy lever for Chinese text rendering, sourced from the OpenAI cookbook.
- **Model adaptation guide** (`model-guide.md`): GPT Image 2 (thinking mode, flexible resolution, quality tiers), Nano Banana (fast batch), Midjourney v7 (--ar/--sref, textless backgrounds). Includes a model selection decision tree.
- **Module assembly system** (`type-guide.md` expanded): 12-module pool (definition, example, steps, comparison, pitfall, analogy, gold-sentence, rating, etc.) for flexible card composition beyond fixed preset types.
- **Troubleshooting manual** (`troubleshooting.md`): 6 common pitfalls with targeted fixes (garbled text, marketing wallpaper, module collapse, flat hierarchy, messy arrows, Lorem Ipsum filler). Includes a block-level debugging workflow table.
- **CHANGELOG.md** (this file).

### Changed

- **SKILL.md SOP upgraded** from 3 steps to 4 steps: added Step 2 "Knowledge Decomposition" — decompose the knowledge point into 3-4 drawable visual learning goals before writing any prompt. This is the critical step that prevents the #1 failure mode (skipping straight from concept to prompt).
- **Step 1 inquiry** now includes target model selection (GPT Image 2 / Nano Banana / MJ v7 / unspecified).
- **Examples** (`examples.md`) fully rewritten with complete 5-block prompts showing the full decomposition → assembly workflow.
- **Output format** (`output-format.md`) now includes the decomposition summary and model hint.
- **Validation checklist** (`validation.md`) expanded with prompt structure, copy quality, educational quality, and model compatibility checks.

### Removed

- DALL-E 3 as the sole referenced model (replaced with multi-model guide).

### Research basis

Optimizations are based on analysis of 8+ articles from 2025-2026 on AI educational image generation best practices, including:
- OpenAI GPT Image 2 cookbook (text rendering, quality tiers, resolution rules)
- Phillip Alcock's 4-zone educational infographic framework (learning-goal-driven design)
- GPT Image 2 knowledge-card prompt guide (5-block template, pitfall catalog)
- Xiaohongshu infographic production templates (CJK text quoting, font hierarchy)

## v1.0.0 — Initial release

- 8 visual types (graphic-card, knowledge-map, three-column, scene-story, analogy, process-flow, right-wrong, intent-explainer)
- 4 domain aesthetics, 3 rendering mediums, 3 platform layouts
- Interactive SOP with style inquiry
- DALL-E 3 targeted prompts

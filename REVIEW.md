# Skill Review — edu-image-prompt v2.1.0

## Overall score

| Dimension | Score | Notes |
|-----------|-------|-------|
| Agent trigger quality | 9/10 | Frontmatter description includes Chinese + English triggers, concrete output types, clear "when to use / when not to use" boundaries. Follows Anthropic spec (third person, ≤1024 chars). |
| SOP executability | 9/10 | 3-step workflow with default values (no forced menu), template-driven decomposition table, validation checkpoint. Low ambiguity for Agent execution. |
| Progressive disclosure | 9/10 | SKILL.md ~110 lines (< 500 limit). 8 references at one level deep. No nested reference chains. |
| Prompt output quality | 9.5/10 | 5-block structured template, `THE TEXT READS: "..."` quoting, model-specific adaptation, font hierarchy specification. Production-validated. |
| User experience | 9/10 | Prompt delivered first (copy-paste ready), design notes after. Quick-default mode avoids blocking. Variants included. |
| Anthropic format fit | 9.5/10 | Compliant frontmatter, one-level-deep references, appropriate freedom (template for decomposition, guidelines for style), checklist with feedback loop. |

## What changed in v2.1.0 (Anthropic format compliance)

| Issue from v2.0.0 review | Fix |
|--------------------------|-----|
| Step 2 decomposition too open-ended | Added template table with columns + validation checkpoint (lowered freedom) |
| Forced 4-question menu blocked users | Added default values; menu only shown when user asks for options |
| `ask_user` tool reference too specific | Removed; style setup now works without any tool dependency |
| Prompt buried under process info | Output reordered: prompt first in code block, design notes after `---` |
| style-config overlapped with model-guide | style-config now focuses on aesthetics/palette only; resolution moved to model-guide |
| Missing REVIEW.md | Added (this file) |

## Anthropic Skills specification compliance

- [x] `name` field: lowercase + hyphens, ≤ 64 chars, no reserved words
- [x] `description` field: third person, includes "what" + "when to use", ≤ 1024 chars
- [x] SKILL.md body < 500 lines
- [x] References at one level deep (no SKILL.md → A → B chains)
- [x] Forward-slash paths only
- [x] Default values provided (not excessive options)
- [x] Validation checklist with feedback loop
- [x] Appropriate freedom: low-freedom for error-prone steps (decomposition template), high-freedom for creative steps (style/aesthetic)

## Remaining boundaries (intentional limits)

This skill does NOT:
- Generate the actual image (it produces a prompt for the user to paste into an image generator)
- Handle photo editing or image retouching
- Create logos, brand assets, or marketing creatives
- Guarantee pixel-perfect text rendering (depends on the target model's capabilities)
- Support every possible visual type — 8 presets + 12 modules cover the common educational patterns

## Roadmap (future ideas)

- Add a `scripts/` directory with a prompt validator that checks 5-block structure programmatically
- Add support for video storyboard prompts (not just single images)
- Add a "style reference image" workflow for Midjourney `--sref` consistency
- Add more domain-specific module templates (STEM diagrams, history timelines, language learning cards)
- Add multilingual prompt output (currently optimized for Chinese + English bilingual)

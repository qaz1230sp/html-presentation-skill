# Composition Rules / 组合规则

This file is the master assembly rulebook for slide composition. Use it after choosing a theme and before writing HTML. Its purpose is to keep decks coherent, varied, readable, and record-friendly.

## Narrative Arc

Choose one arc before composing the deck. Then map each slide to a layout on purpose rather than improvising slide-by-slide.

### Arc Template 1: Technical Deep Dive (8-12 slides)

Recommended flow: title → problem → architecture → code → demo → stats → comparison → takeaway → end

| Position | Story Beat | Recommended Layout | Notes |
| --- | --- | --- | --- |
| 1 | Title | `title-hero` | Strong promise, short headline |
| 2 | Problem | `bullet-points` | Define pain clearly, 3-5 bullets |
| 3 | Architecture | `two-column` or `full-image` | Diagram + explanation works best |
| 4 | Code | `code-showcase` | Keep snippet focused |
| 5 | Demo / walkthrough | `full-image` or `two-column` | Screenshot or flow + narration |
| 6 | Stats / evidence | `stats-dashboard` | 2-4 metrics only |
| 7 | Comparison | `comparison` | Old vs new / before vs after |
| 8 | Takeaway | `bullet-points` or `quote-highlight` | Summarize key lessons |
| 9 | End | `end-cta` | Close with next step |
| 10-12 | Optional inserts | `timeline`, `card-grid`, or `quote-highlight` | Use only if needed for roadmap, feature grouping, or breathing space |

### Arc Template 2: Product Launch (10-15 slides)

Recommended flow: title → hook → problem → solution → features (3-4) → stats → testimonial → pricing → CTA → end

| Position | Story Beat | Recommended Layout | Notes |
| --- | --- | --- | --- |
| 1 | Title | `title-hero` | Brand, launch promise, date |
| 2 | Hook | `full-image` or `quote-highlight` | Lead with emotion or visual proof |
| 3 | Problem | `bullet-points` | Audience pain in plain language |
| 4 | Solution | `two-column` | Problem on left, answer on right |
| 5 | Feature 1 | `card-grid` or `two-column` | Start feature cluster |
| 6 | Feature 2 | `card-grid` or `bullet-points` | Do not repeat same layout 3 times |
| 7 | Feature 3 | `comparison`, `two-column`, or `full-image` | Show differentiation |
| 8 | Optional feature 4 | `timeline` or `card-grid` | Use only if it adds clarity |
| 9 | Stats / traction | `stats-dashboard` | Adoption, usage, savings |
| 10 | Testimonial / proof | `quote-highlight` | One strong voice |
| 11 | Pricing / packages | `comparison` or `two-column` | Clear contrast |
| 12 | CTA setup | `bullet-points` | Next steps, rollout motion |
| 13 | End / CTA | `end-cta` | Final ask |
| 14-15 | Optional inserts | `full-image` or `stats-dashboard` | Only if pacing needs space or extra proof |

### Arc Template 3: Knowledge Share (6-10 slides)

Recommended flow: title → context → concept1 → concept2 → concept3 → example → summary → end

| Position | Story Beat | Recommended Layout | Notes |
| --- | --- | --- | --- |
| 1 | Title | `title-hero` | Topic + learning promise |
| 2 | Context | `bullet-points` or `two-column` | Why this matters now |
| 3 | Concept 1 | `two-column` | Idea + diagram/example |
| 4 | Concept 2 | `card-grid`, `timeline`, or `bullet-points` | Pick based on structure |
| 5 | Concept 3 | `comparison` or `two-column` | Contrast misconceptions or options |
| 6 | Example | `code-showcase`, `full-image`, or `two-column` | Make it concrete |
| 7 | Summary | `bullet-points` or `quote-highlight` | 3 key lessons |
| 8 | End | `end-cta` | Thank you / action / contact |
| 9-10 | Optional inserts | `stats-dashboard` or `full-image` | Add only when evidence or pacing benefits |

## Layout Sequencing Rules

Apply these in order. Hard rules override preferences.

### Hard Rules

- Same layout **cannot** repeat consecutively.
- `title-hero` is always the first slide.
- `end-cta` is always the last slide.
- `full-image` pages cannot appear consecutively.
- `quote-highlight` appears **max 2 times** per presentation.
- `card-grid` appears **max 2 times** per presentation.
- `toc` appears **max 1 time** per presentation, always within the first 3 slides.
- `section-divider` should only appear between major sections, not before every slide.
- `table` appears **max 2 times** per presentation.

### Pairing Rules

- `stats-dashboard` must be followed by `bullet-points` or `two-column` so the audience gets interpretation, not just numbers.
- `code-showcase` should be preceded or followed by `bullet-points` to explain why the snippet matters.
- After **3-4 content-heavy slides**, insert a breathing slide: `quote-highlight`, `full-image`, or `stats-dashboard`.
- Avoid more than **2 slides in a row** that share the same visual rhythm, even if the layout names differ. Example: `bullet-points` → `comparison` → `two-column` is acceptable, but `bullet-points` → `two-column` → `comparison` → `bullet-points` may still feel dense and needs a break.

### Recommended Transition Logic

| Current Layout | Best Next Layouts | Why |
| --- | --- | --- |
| `title-hero` | `bullet-points`, `full-image`, `quote-highlight` | Open with setup or hook |
| `bullet-points` | `two-column`, `comparison`, `code-showcase` | Move from summary to evidence |
| `two-column` | `stats-dashboard`, `full-image`, `timeline` | Expand or visualize |
| `stats-dashboard` | `bullet-points`, `two-column` | Interpretation required |
| `code-showcase` | `bullet-points`, `full-image` | Explain or show result |
| `comparison` | `stats-dashboard`, `quote-highlight`, `bullet-points` | Reinforce decision or insight |
| `card-grid` | `stats-dashboard`, `full-image`, `comparison` | Shift from catalog to meaning |
| `timeline` | `stats-dashboard`, `quote-highlight`, `bullet-points` | Close sequence with insight |
| `flowchart` | `bullet-points`, `two-column`, `stats-dashboard` | Explain what the flow means |
| `icon-grid` | `two-column`, `stats-dashboard`, `comparison` | Expand on features shown |
| `toc` | Any content layout | Only appears after title |
| `section-divider` | Any content layout | Marks chapter start |
| `table` | `bullet-points`, `two-column`, `quote-highlight` | Interpret the data |

## Content Density Rules

These are maximums, not targets. When in doubt, use less.

| Layout | Maximum Content | Guidance |
| --- | --- | --- |
| `title-hero` | title: 8 words max; subtitle: 15 words max | One big promise, not a paragraph |
| `bullet-points` | 5 bullets max; each bullet 15 words max | Prefer 3-4 bullets when possible |
| `two-column` | 100 words per column max | One compact block per side |
| `stats-dashboard` | 4 stat items max | 2-3 is often stronger |
| `timeline` | 5 items max | Only first 3 may fragment |
| `card-grid` | 6 cards max; each card 20 words max | Parallel structure only |
| `comparison` | 5 items per column max | Keep both sides balanced |
| `code-showcase` | 15 lines of code max | Show one idea, not a file |
| `flowchart` | 5 nodes max | Linear only; complex flows use ink-graph |
| `full-image` | title + caption only | Image is the message |
| `icon-grid` | 8 items max; each item 10 words max | Keep descriptions to 1 line |
| `quote-highlight` | 30 words max in quote | One sentence lands best |
| `toc` | 10 items max | Use 2-col for 4-6, 3-col for 7+ |
| `section-divider` | Chapter number + title only | Pure transition, no body text |
| `table` | 6 columns max; 8 rows max | Split larger tables into multiple slides |
| `end-cta` | title + 1 line + optional 3 stats | Closing should feel decisive |

### Density Escalation Rule

If any slide exceeds its max, split the content into two slides rather than shrinking text, reducing margins, or inventing tighter containers.

## Fragment Rules

Fragments are useful for pacing, but too many create spacebar fatigue.

### Per-layout limits

| Layout | Fragment Limit |
| --- | --- |
| `title-hero` | 0 |
| `bullet-points` | max 3 |
| `two-column` | 1 |
| `stats-dashboard` | 0 |
| `timeline` | max 3 |
| `card-grid` | 0 |
| `comparison` | 1 |
| `code-showcase` | 0 |
| `flowchart` | 0 |
| `full-image` | 0 |
| `icon-grid` | 0 |
| `quote-highlight` | 0 |
| `toc` | 0 |
| `section-divider` | 0 |
| `table` | 0 |
| `terminal-demo` | 0 |
| `end-cta` | 0 |

### Presentation-level limit

- Total fragments per presentation: **max 15**
- Prefer fragments only when reveal order changes meaning.
- Never fragment stat items, cards, or decorative elements.
- If a slide needs more than its fragment allowance, split the slide.
- **First-item-visible rule**: On any slide with a list or sequential items, the **first item must always be visible on slide entry** (not wrapped in a fragment). Only the 2nd item onward should be fragments. This ensures the slide never appears empty when first shown.

## Chart Placement Rules

Charts are evidence slides, not decoration.

### Placement Rules

- Maximum **5 charts per presentation** (for data-report decks with 15+ slides, up to **8** is acceptable)
- Put chart slides in `stats-dashboard` or `two-column` (chart + explanation)
- Avoid placing **2 chart slides consecutively** unless each chart addresses a distinctly different metric
- Every chart must have:
  - a clear chart title
  - a data source note
  - a one-sentence interpretation somewhere on the slide or immediately after it

### Chart Type Selection

| Use Case | Recommended Chart |
| --- | --- |
| Trend over time | line |
| Comparison between categories | bar |
| Proportion / share | pie / donut |
| Multi-dimension comparison | radar |
| Single KPI | gauge |
| Correlation | scatter |

### Composition Advice

- If the key message is “look at the number,” use `stats-dashboard`.
- If the key message is “understand why the number matters,” use `two-column` with chart on one side and explanation on the other.
- If a chart needs more than 2 supporting bullets, it probably needs its own interpretation slide next.

## Image Placement Rules

Treat images as structured assets with narrative roles.

### Role-based Placement

| Image Role | Preferred Layouts | Notes |
| --- | --- | --- |
| Architecture diagram | `full-image` or `two-column` | Use `two-column` when explanation is required |
| Screenshot | `full-image` | Add a short caption |
| Chart / data image | `stats-dashboard` variant or `full-image` | Prefer native charts when possible |
| Photo / portrait | `quote-highlight` variant or `two-column` | Best when tied to a person or quote |
| Logo | `title-hero` or `end-cta` | Keep branding subtle |

### Image Handling Rules

- Image-heavy slides should not appear consecutively.
- All images must be embedded as **base64 data URI**.
- If a single image is **over 2MB**, warn the user.
- If total image payload is **over 10MB**, prompt the user to reduce or compress assets.
- Do not place long explanatory text on `full-image`; move interpretation to the next slide or use `two-column`.

## Theme Selection Guide

Pick theme from content keywords, audience, and tone. Prefer the theme that fits audience expectations over keyword matching alone.

| Theme | Keywords | Audience |
| --- | --- | --- |
| `glassmorphism` | 技术, 架构, 代码, API, 系统, engineering | 开发者, 技术团队 |
| `apple-keynote` | 产品, 用户体验, 设计, 发布, launch | 产品经理, 设计师, 大众 |
| `cyberpunk` | AI, 安全, 黑客, 前沿, hacking, ML | 极客, 安全团队 |
| `gradient-story` | 博客, 学习, 分享, 开源, tutorial | 学习者, 社区 |
| `editorial` | 报告, 分析, 研究, 数据, academic | 管理层, 研究员 |
| `luxury-minimal` | 品牌, 投资, CEO, 高端, premium | 高管, 投资人 |

### Theme Selection Heuristics

- If the deck includes code, architecture, or system diagrams, default to `glassmorphism`.
- If the goal is announcement, storytelling, or mainstream product polish, default to `apple-keynote`.
- If the deck feels experimental, futuristic, or security-oriented, use `cyberpunk`.
- If the deck is educational or community-facing, use `gradient-story`.
- If the deck is data-heavy, formal, or research-driven, use `editorial`.
- If the deck is investor-facing, executive, or brand-premium, use `luxury-minimal`.

## Breathing Space Rules

Visual rhythm matters as much as content accuracy.

- After every **3-4 content-dense slides**, insert **1 lighter slide**
- Breathing layouts:
  - `quote-highlight`
  - `full-image`
  - `stats-dashboard` with only 2-3 large numbers
- A presentation should never have **4+ consecutive heavy slides**
- Heavy slides are:
  - `bullet-points`
  - `two-column`
  - `comparison`
  - `code-showcase`

### Practical Rhythm Pattern

Use this pacing loop when unsure:

1. Setup / explain
2. Expand / compare
3. Evidence / detail
4. Breathe

Then repeat.

## Slide Count Guidelines

Use duration and speaking style to size the deck. Slower, executive talks can tolerate fewer slides; recorded demos often need quicker cuts.

| Duration | Slides | Pacing |
| --- | --- | --- |
| 3 min (short video) | 6-8 | 1 slide / 25s |
| 5 min (standard video) | 8-12 | 1 slide / 30s |
| 10 min (long video) | 12-18 | 1 slide / 35s |
| 20 min (talk) | 18-25 | 1 slide / 50s |

### Count Selection Rules

- If the topic is technical and requires code or architecture, bias toward the higher end.
- If the presentation relies on screenshots or visuals, keep text lighter and use more slides.
- Never add filler slides just to hit a target count; remove weak slides before trimming density.

## Document Source Conversion Rules

When converting an existing document (PDF, PPTX, DOCX) into an HTML presentation, follow these rules:

### Content Cleaning

The file reader may return raw artifacts from the source document. Before using any content:

1. **Strip image placeholders** — Remove all `[Image: image/png]`, `[Image: image/jpeg]`, and similar markers. These are extraction artifacts, not displayable content.
2. **Strip chapter/section numbering** — Source PPTs often use numbering like "01", "02" as decorative page elements. Do NOT carry these into the output as `<span class="tag">` or any visible element unless the content genuinely benefits from a tag label.
3. **Strip TOC / 目录 slides** — Table-of-contents pages from the source should NOT be reproduced. The HTML presentation does not need a TOC slide; let the slide sequence speak for itself.
4. **Merge garbled text** — PDF extraction sometimes produces broken characters (e.g., "方方方" or "采采采"). Omit or rephrase these sections using context clues from surrounding content.

### Content Density Minimum

Every slide must carry enough information to justify occupying a full page:

- **Minimum for `bullet-points`**: at least 3 bullets, or 2 bullets with a meaningful footer-note.
- **Minimum for `two-column`**: both columns must have content (at least 2 items each).
- **Minimum for any layout**: at least 40 words of meaningful text (excluding titles and labels).
- If a planned slide falls below the minimum, **merge it** into an adjacent slide rather than creating a sparse page.
- If merging is not possible and the slide has very little content, use `justify-content: center !important` on that section so the content is vertically centered instead of sitting at the top of an empty page.

### Source-Aware Strategy

| Source Type | Strategy |
| --- | --- |
| Topic / prompt | Full creative freedom — choose arc, theme, layouts freely |
| Markdown / text file | Restructure around headings; group related sections into slides |
| PDF (text-based) | Extract key messages; reorganize into a narrative arc; do NOT mirror source page breaks |
| PPTX / PPT | Understand the overall narrative and content, then **restructure** using our layouts. Do NOT blindly copy slide-by-slide. Merge sparse source slides, split dense ones, and apply our layout variety rules. |
| Image files | Embed as base64; use `full-image` or `two-column` with caption |

### Key Principle

The goal is to produce a **well-designed, information-dense presentation** — not a 1:1 translation of the source document's structure. Always prioritize:
1. Every slide must deliver a clear, complete message
2. No slide should feel empty or sparse
3. Content should be reorganized for maximum clarity, not copied in source order

## Anti-Patterns

These are common AI assembly failures. Avoid them deliberately.

### 1) Wall of text

**Bad:** 10+ bullets on one slide  
**Good:** Split into 2 slides or convert to `card-grid` / `two-column`

### 2) Layout repetition

**Bad:** 3 `bullet-points` slides in a row  
**Good:** Alternate with `two-column`, `card-grid`, or `full-image`

### 3) Fragment overload

**Bad:** 6 fragments on one slide  
**Good:** Cap at 3 and split the rest into another slide

### 4) Orphan chart

**Bad:** Chart appears with no explanation  
**Good:** Follow with `bullet-points` or use `two-column` with interpretation

### 5) Missing narrative

**Bad:** Random slide order based on source document order only  
**Good:** Choose an arc template first, then map content to it

### 6) Content overflow

**Bad:** Text touches or exceeds slide boundary; layout depends on `min-height` hacks  
**Good:** Reduce content, split slides, keep containers content-driven, and use **no `min-height`** for overflow fixes

### 7) Consecutive image resets

**Bad:** `full-image` followed by another `full-image`  
**Good:** Insert interpretation or context in between

### 8) Catalog without hierarchy

**Bad:** Putting every feature, stat, and screenshot in one uninterrupted run  
**Good:** Group related ideas, summarize between clusters, and give the audience a place to breathe

### 9) Raw artifacts from source

**Bad:** Displaying `[Image: image/png]`, chapter numbers like "01 优势" as tags, or garbled text from PDF extraction  
**Good:** Clean all parsed content before assembly; only use meaningful, human-readable text

### 10) Sparse slide

**Bad:** A slide with only 1-2 lines of text sitting at the top of an otherwise empty page  
**Good:** Merge sparse content into adjacent slides, or center the content vertically if it must stand alone

## Quick Reference Matrix

| Layout | Max Content | Fragments | Good After | Bad After |
| --- | --- | --- | --- | --- |
| `title-hero` | Title 8 words; subtitle 15 words | 0 | Start only | Any layout before it |
| `bullet-points` | 5 bullets, 15 words each | max 3 | `title-hero`, `stats-dashboard`, `code-showcase` | `bullet-points` |
| `two-column` | 100 words per column | 1 | `bullet-points`, `full-image`, `stats-dashboard` | `two-column` |
| `stats-dashboard` | 4 stats | 0 | `two-column`, `comparison`, `timeline` | `stats-dashboard`, `full-image` if it creates back-to-back evidence with no interpretation |
| `timeline` | 5 items | max 3 | `bullet-points`, `quote-highlight`, `full-image` | `timeline` |
| `card-grid` | 6 cards, 20 words each | 0 | `bullet-points`, `two-column`, `quote-highlight` | `card-grid` |
| `comparison` | 5 items per column | 1 | `bullet-points`, `stats-dashboard`, `card-grid` | `comparison` |
| `code-showcase` | 15 code lines | 0 | `bullet-points`, `two-column` | `code-showcase`, `stats-dashboard` without explanation bridge |
| `flowchart` | 5 nodes | 0 | `bullet-points`, `two-column` | `flowchart` |
| `full-image` | Title + caption only | 0 | `bullet-points`, `code-showcase`, `comparison` | `full-image` |
| `icon-grid` | 8 items, 10 words each | 0 | `bullet-points`, `card-grid` | `icon-grid` |
| `quote-highlight` | Quote 30 words | 0 | `stats-dashboard`, `comparison`, `timeline` | `quote-highlight` |
| `toc` | 10 items | 0 | `title-hero` only | Anywhere except after title |
| `section-divider` | Number + title | 0 | Any content layout | `section-divider` |
| `table` | 6 cols, 8 rows | 0 | `bullet-points`, `stats-dashboard` | `table` |
| `end-cta` | Title + 1 line + optional 3 stats | 0 | Any final content slide | Anything after it |


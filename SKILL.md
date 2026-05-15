---
name: html-presentation
description: "Use when a user asks to create, generate, convert, or modify a reveal.js single-file HTML presentation for recording or live delivery. Triggers on \"做PPT\", \"生成演示文稿\", \"HTML presentation\", \"generate slides\", \"create presentation\", \"make slides\", \"幻灯片\", \"做个演示\", \"录视频用的PPT\", \"文档转PPT\", \"修改PPT\", \"修改演示文稿\", \"加几页\", \"改一下PPT\". Also triggers when users provide PDF/Word/Markdown files and ask to present or visualize them."
---

# HTML Presentation Generator v2

## Overview

This skill generates single-file HTML presentations for reveal.js-based recording and live delivery. Version 2 uses a **component-assembly architecture**: the AI selects a theme, layouts, and chart presets from this skill's library, copies them verbatim, then fills placeholders with user content.

**Output model**
- Single `.html` file
- reveal.js 5.1.0 via CDN
- highlight.js via CDN
- ECharts 5 via CDN when charts are used

**Assembly contract**
- Never write CSS from scratch. Read the selected file in `themes/` and copy the **entire CSS block** verbatim.
- Never invent slide structure. Read the selected file in `layouts/` and copy the **HTML template** verbatim.
- Never build chart config from a blank object. Read the selected file in `charts/` and copy the **preset option** verbatim before replacing placeholders and data.
- Always read `rules/composition.md` before planning the deck so slide order, pacing, density, and fragments stay within system rules.
- Always read `rules/animation.md` before writing fragments and transitions so animations feel cinematic, varied, and content-driven — not generic AI output.

**Positioning & content rules:** Read `rules/positioning.md` — covers layout centering strategy, footer-note placement, and content style rules. Violating these causes visual bugs.

**Animation & dynamics rules:** Read `rules/animation.md` — covers fragment variety, per-slide transitions, SVG visual demos, anti-AI-patterns, and performance animation requirements. Violating these makes the deck feel flat and generic.


## Configuration

Config file: `{HOME}/html-presentation-skill/config.json`

Note: `{SKILL_DIR}` resolves to the skill's installation directory and `{HOME}` resolves to the user's home directory.

### First-time setup

If `config.json` does not exist, create it with user preferences for:
1. `output_dir`
2. `default_theme`
3. `default_language`
4. `default_transition`
5. `default_ratio`
6. `author`

Recommended initial file:

```json
{
  "output_dir": "{HOME}/Presentations",
  "default_theme": "glassmorphism",
  "default_language": "zh-CN",
  "default_transition": "slide",
  "default_ratio": "16:9",
  "author": "Your Name"
}
```

### Default theme options

Use one of:
- `glassmorphism`
- `apple-keynote`
- `cyberpunk`
- `gradient-story`
- `editorial`
- `luxury-minimal`

### Subsequent runs

Read `config.json` first. Use it as the default source of:
- output directory
- theme
- language
- transition
- aspect ratio
- author

User instructions in the current request override config values.

### Modifying config

When the user asks to update configuration, edit `{HOME}/html-presentation-skill/config.json` directly and preserve unrelated keys.

## Workflow: New Presentation

### Step 0: Read & Understand Source Material

Before any planning, **fully read and understand** the source material.

**If user provides a document:**

Use the file reader:

```powershell
python {SKILL_DIR}/scripts/read_file.py "path/to/file"
```

Supported source types from the reader:
- Markdown: `.md`, `.markdown`
- Text: `.txt`, `.text`
- PDF: `.pdf`
- Word: `.docx`, `.doc`
- PowerPoint: `.pptx`, `.ppt`
- Images: `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.svg`

Reading rules:
- Read the **entire** document before making any decisions.
- Identify the core message, narrative thread, and logical structure.
- Preserve code blocks from the source.
- Use headings, pages, or slide titles as structure hints, not as the final slide order.
- If the reader returns `install_cmd`, install the dependency and re-run the reader.
- For standalone images, generate a base64 data URI and embed that URI into the final HTML.
- For visual assets discovered in documents, classify each image by role before assigning a layout.

Image role classification:
- architecture diagram
- screenshot
- chart / data image
- photo / portrait
- logo

Map image roles using `rules/composition.md` → **Image Placement Rules**.

**If user provides only a topic:** Ask for more context or key points to include. Do not fabricate content that the user has not provided.

### Step 1: Deep Analysis & Content Restructuring

After reading, perform a deep analysis of the material. This is not a 1:1 translation of the source — you are **restructuring** raw material into a presentation narrative.

**Analysis tasks:**

1. **Extract the core thesis** — What is the single most important message? Everything else supports it.
2. **Identify information hierarchy** — What is essential (must show), important (should show), and supplementary (can skip or put in speaker notes)?
3. **Detect logical relationships** — Which concepts are parallel (→ card-grid), sequential (→ timeline), contrasting (→ comparison), or causal (→ flowchart)?
4. **Find the "golden data"** — Key numbers, quotes, before/after comparisons, and concrete examples that make the story credible.
5. **Choose a narrative arc** — Based on `rules/composition.md`, select the arc template (Technical Deep Dive / Product Launch / Knowledge Share) that best fits the material's natural flow.
6. **Decide what to merge or cut** — Consolidate related but scattered sections; drop content that doesn't serve the core thesis. A slide deck is not a document mirror.

### Step 2: Build Structured Outline & Confirm with User

**This is a mandatory checkpoint.** Do NOT generate HTML until the user confirms the outline.

Based on the deep analysis, produce a **structured outline** and present it **in the assistant response** (not inside ask_user). The outline must include:

1. **Content summary** (2-3 sentences): What this deck is about, who the audience is, what the takeaway should be.
2. **Slide plan table**: For each slide, show:
   - Slide number
   - Layout type (e.g., `title-hero`, `two-column`, `card-grid`)
   - Slide title
   - Key content points (2-3 bullets summarizing what will appear)
   - Fragment/animation note (if any, e.g., "items reveal one by one")
3. **Theme recommendation**: Which theme and why.
4. **Total slide count** and estimated duration.

**Save the outline to a project directory:**

Each presentation is a **project**. Create a directory and save the outline:

```text
{output_dir}/{topic-slug}-{YYYY-MM-DD}/
├── outline.md    ← structured outline (saved now)
└── index.html    ← presentation file (saved in Step 8)
```

Save the outline as `outline.md` in the project directory **before** asking the user to confirm. This gives the user a persistent artifact to review and edit.

**Example outline format (for outline.md):**

```markdown
# AI-Driven Team Efficiency — Presentation Outline

## Content Summary
Introducing AI-driven team efficiency solutions, targeting tech leadership, with the core conclusion being...

## Slide Plan

| # | Layout | Title | Key Points | Animation |
|---|--------|-------|------------|-----------|
| 1 | title-hero | AI-Driven Team Efficiency | Main title + subtitle + author | fade |
| 2 | bullet-points | Challenges We Face | Knowledge silos / Repetitive work / Onboarding gaps | first-item-visible |
| 3 | two-column | Two Core Platforms | Left: LLM Wiki / Right: Skill Hub | opposing slide-in |
| ... | ... | ... | ... | ... |

## Theme
Glassmorphism (best for tech talks)

## Stats
- Slides: 11
- Estimated duration: 8-10 min
```

**Outline quality rules:**

- Each slide must have a clear, distinct message — no "filler" slides.
- Content must be **restructured for presentation logic**, not copied in document order.
- Related but scattered sections should be **consolidated** (e.g., merge "Architecture Features" into the "Skill Hub" slide instead of giving it a separate page).
- Short standalone content (a single quote, a one-line concept) should be **woven into adjacent slides** rather than given a dedicated page, unless it serves as a deliberate breathing slide.
- List/bullet slides should show **the first item by default** (not as a fragment); remaining items are fragments.
- Consider layout variety: use 2×2 grids for 4 parallel items, not always 1×2 two-column.

**After presenting the outline, use `ask_user` to confirm** with a simple question like "Does this outline look good? Any changes needed?". Wait for their response before proceeding. If they request changes, revise the outline and re-confirm.

Also confirm key unknowns (never ask more than 3 additional questions beyond the outline). Pick from:

1. **Language**: Skip if obvious from content or config `default_language`.
2. **Theme**: Skip if specified. Choices: Glassmorphism, Apple Keynote, Cyberpunk, Gradient Story, Editorial, Luxury Minimal.
3. **Author**: Use config `author` as default. Skip if already known.
4. **Special pages**: Q&A, TOC — only ask if unclear.

**Skip rules:** Don't re-ask answered questions. For document conversions, infer language from source content.

### Step 3: Select Theme

1. Read `rules/composition.md`, especially **Theme Selection Guide**.
2. Choose the best theme for the topic, audience, and tone (or use the one confirmed in Step 2).
3. Read the selected file in `themes/`.
4. Copy the theme's:
   - reveal.js theme CSS CDN link
   - highlight.js CDN link
   - **entire CSS block**
   - ECharts palette/theme data
   - image treatment guidance

Theme selection priority:
1. explicit user request
2. audience expectation
3. topic fit from `rules/composition.md`
4. config default

### Step 4: Finalize Slide Sequence

Using the confirmed outline, finalize the slide sequence by applying `rules/composition.md` layout sequencing rules:
- `title-hero` first
- `end-cta` last
- never repeat the same layout consecutively
- never place `full-image` twice in a row
- respect max usage rules such as `quote-highlight` and `card-grid`
- insert a breathing slide every 3-4 content-heavy slides
- follow chart placement rules
- respect content density maximums instead of shrinking text

Also apply `rules/animation.md` for animation planning:
- vary per-slide `data-transition` (at least 2 different types across the deck)
- plan fragment types based on information relationships (progressive → `fade-up`, contrast → `fade-left/right`)
- first list item on every slide is **always visible** (not a fragment)
- plan at least 1 performance animation (counter roll, stroke draw, bar fill, or typewriter)
- ensure adjacent slides do not share the same dominant animation

Plan fragments before assembly:
- follow each layout's fragment cap
- keep total fragments across the deck at **15 or fewer**
- if a slide needs more fragments than allowed, split it into two slides

### Step 5: Assemble Each Slide

For each planned slide:

1. Read the target layout file in `layouts/`.
2. Copy the HTML template exactly.
3. Replace `PLACEHOLDER` comments with actual content.
4. Keep `style="overflow:hidden;"` on every `<section>`.
5. Do not add `min-height` hacks to force content to fit.
6. Apply per-slide transitions per `rules/animation.md`: vary `data-transition` attribute (e.g., `zoom` for emphasis slides, `fade` for breathing slides, `convex` for spatial content). Available: `slide`, `fade`, `convex`, `concave`, `zoom`, `none`.
7. For list/bullet slides, the **first item must always be visible** (not a fragment). Remaining items use fragments with varied types per `rules/animation.md` (e.g., `fade-up`, `fade-left`, `zoom-in`, `fade-in-then-semi-out`).
8. For document conversions or detailed topics, add speaker notes with `<aside class="notes">` inside the `<section>`. Notes are invisible during display but accessible via speaker view (S key). Only add notes when the source material has more detail than fits on the slide.
9. Keep the layout's fragment structure unless there is an explicit need to remove optional placeholders.

If the slide needs a chart:
1. Read the correct preset in `charts/`.
2. Copy the preset option verbatim.
3. Replace labels, series names, and numeric data.
4. Adapt colors, tooltip surfaces, borders, and text to the active theme using the selected theme's ECharts palette/theme block.
5. Give the chart container a unique ID.
6. Put charts only in layouts allowed by `rules/composition.md`.

If the slide needs an image:
- embed the image as a base64 data URI
- use the theme's recommended `.img-frame` treatment when the layout calls for framed imagery
- keep `max-width:100%`
- keep a `max-height` constraint
- keep captions brief

If the slide needs a **complex diagram** (architecture, data-flow, sequence, branching flowchart, mind-map):
1. First, check if ink-graph is installed: `ls {HOME}/.agents/skills/ink-graph/SKILL.md` or similar location.
2. If NOT installed, install it:
   ```powershell
   npx @anthropic-ai/claude-code skills add qaz1230sp/ink-graph -g -y
   ```
3. Invoke the **ink-graph** skill to generate an SVG diagram with: diagram type, nodes, edges, and theme preference (use `dark-tech` for dark PPT themes, `modern-light` for light themes).
4. Read the generated SVG file content.
5. Inline the SVG directly into the `<section>` (do NOT use `<img>` — inline SVG preserves animations and scales properly).
6. Wrap the SVG in a centered container: `<div style="flex:1; display:flex; align-items:center; justify-content:center;">`.
7. Set SVG `width="100%" height="auto"` and `max-height="75vh"` for proper slide fit.
8. For simple linear flows (3-5 steps, no branching), the CSS `flowchart` layout is sufficient — no need for ink-graph.

**When to use ink-graph vs CSS flowchart:**
- **CSS flowchart** (`layouts/flowchart.md`): Simple linear A→B→C flows, 3-5 steps, no branching
- **ink-graph** (on-demand install): Architecture diagrams, data-flow, sequence diagrams, branching decisions, >5 nodes, grouped/layered layouts, any diagram needing arrows with routing

**When to use terminal-demo vs code-showcase:**
- **Terminal Demo** (`layouts/terminal-demo.md`): CLI commands with execution output, install workflows, terminal interactions — uses typewriter typing animation + blinking cursor + staggered output reveal for cinematic effect
- **Code Showcase** (`layouts/code-showcase.md`): Static code display with syntax highlighting — no animation needed

Assembly principle: **select component → read file → copy verbatim → replace placeholders only**.

### Step 6: Compose Final HTML

Use the boilerplate in **HTML Boilerplate** below.

Insert:
- title
- language
- reveal.js core CSS CDN
- theme CSS CDN from the selected theme file
- highlight.js CDN from the selected theme file
- full copied theme CSS
- assembled `<section>` blocks
- reveal.js scripts
- ECharts script only if charts are used
- chart initialization scripts only if charts are used
- transition from config or request
- slide number display (`c/t` format) and progress bar (enabled by default)

Keep the result as one portable HTML file. External assets should only be CDN links plus inline base64 images.

### Step 7: Quality Check

Run the complete checklist in **Quality Checklist** before saving.

### Step 8: Save & Report

Save the HTML file as `index.html` inside the project directory created in Step 2:

```text
{output_dir}/{topic-slug}-{YYYY-MM-DD}/
├── outline.md    ← created in Step 2
└── index.html    ← save here
```

If the project directory was not created in Step 2 (e.g., simple topic request that skipped outline), create it now.

Report:
- saved file path (full path to `index.html`)
- project directory path
- selected theme
- total slide count
- whether charts were included

## Workflow: Modify Existing Presentation

Use the lightest valid change mode:

1. **Local edit**: Change specific content in one `<section>` or script block.
2. **Append**: Read existing deck → detect theme → assemble new slides from `layouts/` → insert before closing slide. Don't repeat recent layout pattern.
3. **Restyle**: Replace theme CSS CDN + `<style>` block + chart palette. Don't rewrite slide HTML unless asked.

Preserve existing content, images, chart IDs, and title-first/end-last ordering unless explicitly asked to change.

## File Reading

See **Step 0** for full file reading workflow and supported formats. Quick reference:

```powershell
python {SKILL_DIR}/scripts/read_file.py "path/to/file"
```

Supported: `.md`, `.txt`, `.pdf`, `.docx`, `.doc`, `.pptx`, `.ppt`, `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.svg`

For images needing base64, use `--output "path/to/output.json"`. If reader returns `install_cmd`, install and re-run.

## Reference Library

Read `references/library-reference.md` for the full theme, layout, chart, and diagram tables. Use the corresponding file in `themes/`, `layouts/`, or `charts/`, and use ink-graph for complex diagrams before inlining SVG into a slide `<section>`.

## Quality Checklist

Read `rules/quality-checklist.md` before saving. Key checks: overflow:hidden on sections, correct centering strategy per layout type, no position:relative on sections, end slide uses h2, fragment limits.

## HTML Boilerplate

Read `components/boilerplate.md` for the complete HTML template. Key points:
- Single `.html` file with reveal.js 5.1.0, highlight.js, optional ECharts via CDN
- Navigation sidebar from `components/navigation.md`
- `center: false` in Reveal config (CSS handles centering)
- Chart resize handler included when charts are used

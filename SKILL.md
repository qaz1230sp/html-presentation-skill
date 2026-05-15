---
name: html-presentation
description: "Generate beautiful HTML presentations using reveal.js for video recording. Supports creating from topics, converting documents (Markdown, PDF, Word, PPT) to slides, and modifying existing presentations. Trigger on \"生成演示文稿\", \"做PPT\", \"HTML演示\", \"HTML presentation\", \"generate slides\", \"create presentation\", \"make slides\", \"幻灯片\", \"做个演示\", \"录视频用的PPT\", \"文档转PPT\", \"修改PPT\", \"修改演示文稿\", \"加几页\", \"改一下PPT\". Also trigger when users provide PDF/Word/Markdown files and ask to present or visualize them."
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

**Positioning & content rules:** Read `rules/positioning.md` — covers layout centering strategy, footer-note placement, and content style rules. Violating these causes visual bugs.


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

### Step 0: Confirm with User

Before generating, ask the user (via `ask_user` tool) to confirm key unknowns. Never ask more than 3 questions. Pick from:

1. **Language / 语言**: "PPT 使用中文还是英文？" Choices: 中文 (Recommended), English. Skip if user's request language is obvious or config `default_language` applies.
2. **Theme**: Skip if specified. Choices: Glassmorphism, Apple Keynote, Cyberpunk, Gradient Story, Editorial, Luxury Minimal
3. **Author / 署名**: "PPT 上署名是什么？" Use config `author` as default if set. Skip if user already specified or config has author.
4. **Slide count**: Suggest based on source length. Skip if specified.
5. **Outline**: Present slide titles + layout types. Let user adjust.
6. **Special pages**: Q&A, TOC — only ask if unclear.

**Skip rules:** Don't re-ask answered questions. For document conversions, infer language from source content and just confirm outline. For simple topic requests, ask language (if ambiguous) + theme + outline only.

### Step 1: Parse Request

Determine:
- source mode: topic / document / hybrid
- presentation language
- explicit or implied theme request
- target audience and tone
- requested slide count or likely duration
- whether charts, code, screenshots, architecture diagrams, or quotes are needed
- whether the output is a brand-new deck or a modification of an existing file

If slide count is not provided, infer it from the amount of source material and the pacing guidance in `rules/composition.md`.

### Step 2: Read Source Material (if document provided)

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
- Merge extracted sections, pages, or slides into one working outline.
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

### Step 3: Select Theme

1. Read `rules/composition.md`, especially **Theme Selection Guide**.
2. Choose the best theme for the topic, audience, and tone.
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

### Step 4: Plan Slide Sequence

Before writing HTML, read `rules/composition.md` and choose a narrative arc template such as:
- Technical Deep Dive
- Product Launch
- Knowledge Share

Then map content to layouts using sequencing rules:
- `title-hero` first
- `end-cta` last
- never repeat the same layout consecutively
- never place `full-image` twice in a row
- respect max usage rules such as `quote-highlight` and `card-grid`
- insert a breathing slide every 3-4 content-heavy slides
- follow chart placement rules
- respect content density maximums instead of shrinking text

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
6. Optionally set per-slide transitions with `data-transition` attribute (e.g., `<section data-transition="fade">`). Available: `slide`, `fade`, `convex`, `concave`, `zoom`, `none`. Use sparingly — only for emphasis slides like title-hero or section-divider.
7. For document conversions or detailed topics, add speaker notes with `<aside class="notes">` inside the `<section>`. Notes are invisible during display but accessible via speaker view (S key). Only add notes when the source material has more detail than fits on the slide.
8. Keep the layout's fragment structure unless there is an explicit need to remove optional placeholders.

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

Save to the configured `output_dir`.

Recommended file naming:

```text
{topic-slug}-{YYYY-MM-DD}.html
```

Report:
- saved file path
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

```powershell
python {SKILL_DIR}/scripts/read_file.py "path/to/file"
```

Supported: `.md`, `.txt`, `.pdf`, `.docx`, `.doc`, `.pptx`, `.ppt`, `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.svg`

For images needing base64, use `--output "path/to/output.json"`. If reader returns `install_cmd`, install and re-run. Classify images by role (architecture, screenshot, chart, photo, logo) and map using `rules/composition.md` → Image Placement Rules.

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

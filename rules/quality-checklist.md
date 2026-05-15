# Quality Checklist

Run this checklist before saving any presentation.

## Structure & Layout
- [ ] Every `<section>` has `style="overflow:hidden;"`
- [ ] Content-heavy sections: `justify-content:flex-start`
- [ ] Content-light sections (card-grid, stats-dashboard, icon-grid): body content wrapped in `flex:1; justify-content:center` div (h2 stays outside wrapper)
- [ ] .title-slide, .quote-section, .end-slide use `justify-content:center !important` from CSS
- [ ] No position:relative on .reveal .slides section (breaks reveal.js stacking)
- [ ] .footer-note uses margin-top:auto (NOT position:absolute)
- [ ] .footer-note is placed OUTSIDE the flex:1 centering wrapper (direct child of section, NOT inside the justify-content:center div) — violating this breaks vertical centering
- [ ] Flowchart uses Design C (progress track + numbered circles with inline styles), NOT old .flow-diagram/.flow-node/.flow-arrow classes
- [ ] .two-col and .compare-table use `align-items: stretch` (equal column heights)
- [ ] .styled-table has proper theme-matched styling (check theme file for CSS)
- [ ] End slide uses `<h2>` not `<h1>` (theme CSS targets `.end-slide h2`)
- [ ] Title slide is simple: title + subtitle + meta only (no panel, no tags)
- [ ] End slide is simple: thank you + speaker (no stats, no long text)
- [ ] No `min-height` on any container
- [ ] Fragment count per slide ≤ layout's max (check layout file header)
- [ ] Total fragments across entire presentation ≤ 15
- [ ] Table columns ≤ 6, rows ≤ 8 per slide (split if larger)
- [ ] Same layout not used consecutively
- [ ] Title slide is first, End slide is last
- [ ] TOC slide uses correct template variant based on item count (A/B/C/D)
- [ ] All CSS is copied verbatim from theme file (no custom CSS invented)
- [ ] ECharts color array matches theme's palette
- [ ] Chart containers have unique IDs prefixed with `chart-`
- [ ] Chart resize handler included if charts are used
- [ ] All images have `max-width:100%` and max-height constraint
- [ ] Code blocks have `data-trim` attribute
- [ ] Speaker notes use <aside class="notes"> inside <section> (if included)
- [ ] Responsive meta tag present
- [ ] All CDN links are correct (check theme file's CDN Links section)
- [ ] Inline SVG diagrams (from ink-graph) have `width="100%"` and `max-height` constraint
- [ ] Section divider slides use `.title-slide` class (auto-centers via CSS)

## Animation & Dynamics (see `rules/animation.md` for details)
- [ ] Adjacent slides do NOT share the same dominant animation/transition
- [ ] Fragments within a slide use 2+ different types when count ≥ 2
- [ ] At least 1 "performance animation" exists (counter roll / stroke draw / bar fill / typewriter)
- [ ] No perpetual decorative animations (`infinite` keyframes) except typewriter cursor
- [ ] Animation durations use non-round values (0.3s / 0.7s / 1.2s) for natural feel
- [ ] No AI visual fingerprints (purple-pink gradients / emoji icons / fake data)
- [ ] 8+ slide deck has at least 1 inline SVG or CSS visual demo
- [ ] Per-slide `data-transition` has at least 2 different settings across the deck
- [ ] Fragment type matches information relationship (progressive → fade-up, contrast → fade-left/right)
- [ ] Only hiding fragments (`fade-in`, `fade-up`, `fade-left`, `fade-right`, `zoom-in`) used to reveal new content — never `highlight-current-blue` or `shrink`
- [ ] Terminal side cards appear AFTER output lines (delay ≥ 3.2s, not 0.4s)

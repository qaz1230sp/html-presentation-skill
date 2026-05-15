# Changelog

All notable changes to this project will be documented in this file.

## [1.1.0] - 2025-05-11

### Changed
- **Flowchart redesign (Design C)**: Replaced old arrow-based `.flow-diagram` layout with progress track + numbered circles. Fully inline-styled — no theme CSS dependency for flowchart structure.
- **Card grid with icons**: New `icon-wrap` variant (56×56 themed circle + inline SVG) for feature highlight cards.
- **Card grid gap**: Increased from 20px to 28px across all themes for better visual breathing room.
- **Apple Keynote card borders**: Added visible `#d2d2d7` border for clearer card separation.
- **Footer-note positioning**: Documented and enforced correct placement (outside `flex:1` centering wrapper) to prevent vertical centering bugs.
- **Navigation sidebar**: Language-aware labels — uses "Navigation" for English, "导航" for Chinese presentations.

### Fixed
- Vertical centering bug caused by `.footer-note` with `margin-top:auto` inside `justify-content:center` wrapper.
- Flowchart text sizes too large in reveal.js context (now uses `0.72em` / `0.42em` instead of `1.1rem` / `0.75em`).

### Added
- `.icon-wrap` CSS to all 6 themes with theme-appropriate colors.
- Theme color reference table in flowchart layout for quick assembly.
- Footer-note placement section in `rules/positioning.md` with correct/wrong examples.
- Quality checklist items for footer-note placement and Design C flowchart.

## [1.0.0] - 2025-05-09

### Added
- Complete component-assembly architecture with 16 layouts, 8 chart presets, 6 themes
- Layouts: title-hero, toc (4 adaptive variants), section-divider, two-column, card-grid, comparison, quote-highlight, code-showcase, flowchart, bullet-points, icon-grid, stats-dashboard, timeline, full-image, table, end-cta
- Charts: bar, line, pie, radar, scatter, funnel, gauge, treemap (ECharts 5)
- Themes: glassmorphism, apple-keynote, cyberpunk, gradient-story, editorial, luxury-minimal
- Collapsible navigation sidebar component
- Speaker notes support (press S for speaker view)
- PDF export guidance (append ?print-pdf)
- Slide number (c/t format) and progress bar
- Per-slide transition support
- Document reader supporting: Markdown, Text, PDF, Word, PowerPoint, Images
- ink-graph integration for complex SVG diagrams (on-demand install)
- Composition rules with narrative arc templates
- Quality checklist (31 items)
- Portable path system using {SKILL_DIR} and {HOME} placeholders

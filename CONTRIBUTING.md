# Contributing to html-presentation-skill

Thank you for your interest in contributing! This guide explains how to add new components to the skill.

## Adding a New Theme

1. Create `themes/your-theme-name.md`
2. Include: CDN Links, Complete CSS, ECharts Palette, Image Treatment, Theme Auto-select Keywords
3. Add `.styled-table` CSS (copy structure from existing themes)
4. Add panel border-top styling for visual consistency
5. Update `references/library-reference.md` with a new row in the Theme table
6. Update `rules/composition.md` → Theme Selection Guide with your theme's best-fit topics

## Adding a New Layout

1. Create `layouts/your-layout.md`
2. Include: Fragment count, Best for, Avoid when, HTML Template, Usage Notes
3. Follow positioning rules from `rules/positioning.md`
4. Update `references/library-reference.md` with a new row in the Layout table
5. Update `rules/composition.md` → all relevant sequencing/density tables

## Adding a New Chart Preset

1. Create `charts/your-chart.md`
2. Include: Best for, Avoid when, Preset Option (ECharts config), Theme Adaptation Notes
3. Update `references/library-reference.md` with a new row in the Chart table

## Quality Standards

- All CSS must be copied from theme files, never written from scratch
- All HTML templates must be copied from layout files
- Every `<section>` must have `style="overflow:hidden;"`
- Run the quality checklist (`rules/quality-checklist.md`) before submitting

## Testing

Generate a test presentation using your new component and verify it renders correctly in Chrome/Edge.

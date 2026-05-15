# Theme, Layout, Chart & Diagram Reference

## Theme Reference

Available themes (read the corresponding file for full CSS):

| Theme | File | Best For |
|-------|------|----------|
| Glassmorphism / 科技玻璃态 | `themes/glassmorphism.md` | 技术分享、架构设计 |
| Apple Keynote / 苹果简约 | `themes/apple-keynote.md` | 产品发布、商业汇报 |
| Cyberpunk / 赛博朋克 | `themes/cyberpunk.md` | AI/ML、安全主题 |
| Gradient Story / 渐变叙事 | `themes/gradient-story.md` | 博客、学习分享 |
| Editorial / 杂志排版 | `themes/editorial.md` | 学术报告、数据分析 |
| Luxury Minimal / 奢华极简 | `themes/luxury-minimal.md` | CEO汇报、投资路演 |

## Layout Reference

Available layouts (read the corresponding file for HTML template):

| Layout | File | Fragments | Best For |
|--------|------|-----------|----------|
| Title Hero | `layouts/title-hero.md` | 0 | Opening slide |
| Bullet Points | `layouts/bullet-points.md` | max 3 | Key points |
| Two Column | `layouts/two-column.md` | 1 | Comparison, text+code |
| Stats Dashboard | `layouts/stats-dashboard.md` | 0 | Key metrics |
| Timeline | `layouts/timeline.md` | max 3 | History, roadmap |
| Card Grid | `layouts/card-grid.md` | 0 | Features, concepts |
| Comparison | `layouts/comparison.md` | 1 | Before/after |
| Code Showcase | `layouts/code-showcase.md` | 0 | Code demo |
| Full Image | `layouts/full-image.md` | 0 | Screenshots, diagrams |
| Quote Highlight | `layouts/quote-highlight.md` | 0 | Quotes, emphasis |
| Flowchart | `layouts/flowchart.md` | 0 | Process flows (Design C: progress track + numbered circles, fully inline-styled) |
| Icon Grid | `layouts/icon-grid.md` | 0 | Tech stacks, feature lists |
| Table | `layouts/table.md` | 0 | Structured data, specs |
| TOC | `layouts/toc.md` | 0 | Agenda, chapter navigation |
| Section Divider | `layouts/section-divider.md` | 0 | Chapter transitions |
| End CTA | `layouts/end-cta.md` | 0 | Closing slide |

## Chart Reference

Available chart presets (read the corresponding file for ECharts config):

| Chart | File | Best For |
|-------|------|----------|
| Bar | `charts/bar.md` | Category comparison |
| Line | `charts/line.md` | Trends over time |
| Pie | `charts/pie.md` | Proportions |
| Radar | `charts/radar.md` | Multi-dimension compare |
| Gauge | `charts/gauge.md` | Single KPI |
| Scatter | `charts/scatter.md` | Correlation |
| Funnel | `charts/funnel.md` | Conversion pipelines |
| Treemap | `charts/treemap.md` | Hierarchical proportions |

## Diagram Reference (ink-graph — on-demand install)

For complex diagrams that go beyond simple CSS flowcharts, use the **ink-graph** skill (install from `qaz1230sp/ink-graph` if not present):

| Diagram Type | Key Signals | ink-graph Theme |
|-------------|-------------|-----------------|
| Architecture | services, layers, APIs, tiers | dark-tech / modern-light |
| Data Flow | ETL, pipeline, input/output | dark-tech |
| Sequence | request/response, timing | dark-tech / blueprint |
| Flowchart (complex) | branching, decisions, >5 nodes | modern-light |
| Mind Map | brainstorm, concepts, hierarchy | warm-minimal |
| Dependency | imports, modules, coupling | monochrome |

Invoke ink-graph skill → get SVG → inline into slide `<section>`.

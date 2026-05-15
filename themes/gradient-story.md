# Gradient Story Theme

Base: `moon.min.css` | Highlight: `monokai.min.css` | Best for: Tech blogs, learning shares, project summaries, open-source introductions

## CDN Links
- reveal.js core CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css`
- reveal.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/moon.min.css`
- highlight.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/monokai.min.css`

## Complete CSS
```css
:root {
  --r-background-color: #1a1a2e;
  --r-main-font: "Segoe UI", "PingFang SC", "Microsoft YaHei", system-ui, sans-serif;
  --r-heading-font: "Segoe UI", "PingFang SC", "Microsoft YaHei", system-ui, sans-serif;
  --r-code-font: "Cascadia Code", "Fira Code", Consolas, monospace;
  --r-main-color: #eaeaea;
  --r-heading-color: #ffffff;
  --r-link-color: #16c79a;
  --r-link-color-hover: #4de7bf;
  --r-selection-background-color: rgba(233, 69, 96, 0.34);
  --r-body-color: #b8b8d0;
  --r-muted-color: #7878a0;
  --r-strong-color: #e94560;
  --story-bg-start: #1a1a2e;
  --story-bg-mid: #16213e;
  --story-bg-end: #0f3460;
  --story-bg-gradient: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
  --card-bg: rgba(255, 255, 255, 0.06);
  --card-border: rgba(255, 255, 255, 0.1);
  --card-shadow: 0 18px 42px rgba(4, 8, 20, 0.28);
  --accent-primary: #e94560;
  --accent-secondary: #0f3460;
  --accent-tertiary: #533483;
  --accent-info: #16c79a;
  --accent-warning: #f5a623;
  --accent-gradient: linear-gradient(90deg, #e94560 0%, #533483 100%);
  --accent-gradient-soft: linear-gradient(135deg, rgba(233, 69, 96, 0.16) 0%, rgba(83, 52, 131, 0.16) 100%);
}
.reveal {
  position: relative;
  background:
    radial-gradient(circle at 18% 20%, rgba(233, 69, 96, 0.16) 0%, transparent 28%),
    radial-gradient(circle at 84% 12%, rgba(22, 199, 154, 0.08) 0%, transparent 22%),
    radial-gradient(circle at 88% 84%, rgba(83, 52, 131, 0.18) 0%, transparent 30%),
    var(--story-bg-gradient);
  color: var(--r-main-color);
  font-family: var(--r-main-font);
}
.reveal::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.03), transparent 28%);
  pointer-events: none;
}
.reveal .slides,
.reveal .slides section {
  text-align: left;
}
.reveal .slides section {
  display: flex !important;
  flex-direction: column;
  justify-content: flex-start;
  height: 100%;
  padding: 60px 46px 42px;
  overflow: hidden;
  box-sizing: border-box;
}
.reveal h1,
.reveal h2,
.reveal h3,
.reveal h4 {
  margin: 0 0 0.45em;
  font-family: var(--r-heading-font);
  letter-spacing: -0.022em;
  text-transform: none;
}
.reveal h1 {
  color: var(--r-heading-color);
  font-size: 2.5em;
  font-weight: 900;
  line-height: 1.06;
  margin-bottom: 0.28em;
}
.reveal h2 {
  color: var(--r-heading-color);
  font-size: 1.52em;
  padding-left: 18px;
  border-left: 5px solid var(--accent-primary);
}
.reveal h3 {
  color: #f7eef8;
  font-size: 1.08em;
}
.reveal h4 {
  color: #f8c8dc;
  font-size: 0.86em;
  letter-spacing: 0.01em;
}
.reveal p,
.reveal li {
  color: var(--r-body-color);
  line-height: 1.72;
  font-size: 0.82em;
}
.reveal strong {
  color: var(--r-strong-color);
  font-weight: 700;
}
.reveal a {
  color: var(--r-link-color);
  text-decoration-color: rgba(22, 199, 154, 0.4);
}
.reveal ul,
.reveal ol {
  display: block;
  margin: 0.35em 0 0.2em 0.45em;
}
.reveal li + li {
  margin-top: 0.42em;
}
.reveal .title-slide {
  display: flex;
  flex-direction: column;
  justify-content: center !important;
  align-items: center;
  text-align: center;
  gap: 10px;
}
.reveal .hero-title {
  width: 100%;
  max-width: 1400px;
  white-space: nowrap;
  text-align: center;
  font-size: 2.54em;
  line-height: 1.03;
  margin-bottom: 0.1em;
  color: #ffffff;
  animation: slideInUp 0.92s ease-out both;
}
.reveal .subtitle,
.reveal .meta {
  color: var(--r-muted-color);
  font-size: 0.74em;
}
.reveal .subtitle {
  font-size: 0.98em;
  max-width: 920px;
}
.reveal .meta {
  font-size: 0.74em;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.reveal .accent-line {
  width: 108px;
  height: 4px;
  border-radius: 999px;
  background: linear-gradient(90deg, #e94560 0%, #533483 100%);
  margin: 14px auto 18px;
}
.reveal .panel,
.reveal .glass-card,
.reveal .info-card,
.reveal .compare-col,
.reveal .flow-node,
.reveal .stat-item,
.reveal .img-frame {
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  box-shadow: var(--card-shadow);
}
.reveal .panel,
.reveal .glass-card {
  border-radius: 18px;
  padding: 22px 24px;
  border-top: 3px solid #f093fb;
  background: linear-gradient(180deg, rgba(240, 147, 251, 0.08) 0%, rgba(245, 87, 108, 0.05) 18%, rgba(255, 255, 255, 0.06) 42%, rgba(255, 255, 255, 0.06) 100%);
}
.reveal .tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  border-radius: 999px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  color: #ffffff;
  font-size: 0.66em;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  background: linear-gradient(90deg, rgba(233, 69, 96, 0.88) 0%, rgba(83, 52, 131, 0.88) 100%);
}
.reveal .tag + .tag {
  margin-left: 8px;
}
.reveal .tag.tag-coral {
  background: linear-gradient(90deg, #e94560 0%, #ff6b81 100%);
}
.reveal .tag.tag-teal {
  background: linear-gradient(90deg, #16c79a 0%, #2ed3c8 100%);
}
.reveal .tag.tag-purple {
  background: linear-gradient(90deg, #533483 0%, #7c5bc2 100%);
}
.reveal .tag.tag-amber {
  background: linear-gradient(90deg, #f5a623 0%, #ffca55 100%);
  color: #1a1a2e;
}
.reveal .footer-note {
  margin-top: auto;
  padding-top: 16px;
  color: var(--r-muted-color);
  font-size: 0.7em;
  font-style: italic;
  opacity: 0.95;
}
.reveal .two-col {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
  gap: 24px;
  align-items: stretch;
}
.reveal .stats-row {
  display: flex;
  justify-content: center;
  align-items: stretch;
  gap: 22px;
  flex-wrap: wrap;
  margin-top: 22px;
}
.reveal .stat-item {
  flex: 1 1 220px;
  text-align: center;
  padding: 22px 18px;
  border-radius: 18px;
  background: rgba(255, 255, 255, 0.08);
  min-width: 220px;
}
.reveal .stat-number {
  font-size: 2.42em;
  line-height: 1;
  font-weight: 900;
  background: linear-gradient(90deg, #ff92a5 0%, #e94560 45%, #f5a623 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 10px;
}
.reveal .stat-label {
  color: var(--r-muted-color);
  font-size: 0.74em;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}
.reveal .timeline {
  position: relative;
  margin-top: 14px;
  padding-left: 0;
}
.reveal .timeline::before {
  content: "";
  position: absolute;
  left: 42px;
  top: 8px;
  bottom: 8px;
  width: 2px;
  background: linear-gradient(180deg, #e94560 0%, #533483 55%, #0f3460 100%);
}
.reveal .timeline-item {
  position: relative;
  display: flex;
  align-items: flex-start;
  gap: 22px;
  margin: 0 0 24px;
}
.reveal .timeline-marker {
  position: relative;
  z-index: 1;
  min-width: 84px;
  flex-shrink: 0;
  border-radius: 999px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #1a1a2e;
  border: 3px solid #e94560;
  color: #ffffff;
  font-size: 0.78em;
  font-weight: 700;
  box-shadow: 0 10px 24px rgba(15, 52, 96, 0.24);
  padding: 8px 18px;
  white-space: nowrap;
}
.reveal .timeline-content {
  flex: 1;
  padding: 6px 0 0;
}
.reveal .timeline-content h4,
.reveal .timeline-content p {
  margin-bottom: 0.28em;
  font-size: 0.76em;
}
.reveal .timeline-content h4 {
  font-size: 0.86em;
}
.reveal .timeline-content p {
  font-size: 0.76em;
  color: #b6b4cf;
}
.reveal .card-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px;
  margin-top: 16px;
}
.reveal .info-card {
  border-radius: 18px;
  padding: 22px 22px 20px;
  animation: fadeInScale 0.7s ease-out both;
}
.reveal .info-card h3,
.reveal .compare-col h3,
.reveal .panel h3,
.reveal .glass-card h3 {
  margin-top: 0;
  background: linear-gradient(135deg, #f093fb, #f5576c);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.reveal .icon-wrap {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 14px;
  background: rgba(251, 146, 60, 0.15);
  color: #fb923c;
}
.reveal .compare-table {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
  gap: 24px;
  margin-top: 16px;
}
.reveal .compare-col {
  border-radius: 18px;
  padding: 22px 24px;
}
.reveal .compare-bad {
  background: rgba(233, 69, 96, 0.12);
  border-color: rgba(233, 69, 96, 0.26);
}
.reveal .compare-good {
  background: rgba(22, 199, 154, 0.12);
  border-color: rgba(22, 199, 154, 0.26);
}
.reveal .flow-diagram {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
  margin-top: 20px;
}
.reveal .flow-node {
  padding: 16px 20px;
  border-radius: 18px;
  min-width: 150px;
  text-align: center;
}
.reveal .flow-arrow {
  color: var(--accent-primary);
  font-size: 1.1em;
  font-weight: 700;
}
.reveal pre,
.reveal .code-showcase pre {
  width: 100%;
  margin: 0;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 18px 38px rgba(4, 8, 20, 0.34);
  border: 1px solid rgba(255, 255, 255, 0.08);
  background: rgba(9, 12, 26, 0.92);
}
.reveal pre code,
.reveal .code-showcase pre code {
  max-height: 480px;
  padding: 1.25em 1.35em;
  font-family: var(--r-code-font);
  font-size: 0.7em;
  line-height: 1.58;
  border-radius: 18px;
  color: #f8f8f2;
}
.reveal .img-frame {
  border-radius: 18px;
  padding: 14px;
  overflow: hidden;
  background: rgba(255, 255, 255, 0.07);
}
.reveal .img-frame img,
.reveal .img-frame svg,
.reveal img {
  display: block;
  width: 100%;
  border-radius: 14px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  max-width: 100%;
  max-height: 520px;
  height: auto;
  object-fit: contain;
}
.reveal .quote-section {
  display: flex;
  align-items: center;
  justify-content: center !important;
}
.reveal .quote-section blockquote,
.reveal blockquote {
  width: 100%;
  margin: 0 auto;
  padding: 20px 24px;
  border-left: 5px solid var(--accent-primary);
  border-radius: 0 18px 18px 0;
  background: rgba(255, 255, 255, 0.06);
  color: #f4f0f7;
  box-shadow: 0 14px 30px rgba(4, 8, 20, 0.2);
  max-width: 1180px;
}
.reveal .end-slide {
  display: flex;
  flex-direction: column;
  justify-content: center !important;
  align-items: center;
  text-align: center;
  gap: 14px;
}
.reveal .end-slide h2 {
  border-left: none;
  padding-left: 0;
  font-size: 2.4em;
  color: #ffffff;
}
.reveal .end-slide p {
  max-width: 760px;
  text-align: center;
}
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(56px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes glowPulse {
  0%,
  100% {
    text-shadow: 0 0 0 rgba(233, 69, 96, 0), 0 0 0 rgba(83, 52, 131, 0);
  }
  50% {
    text-shadow: 0 0 12px rgba(233, 69, 96, 0.08), 0 0 18px rgba(83, 52, 131, 0.08);
  }
}
@keyframes fadeInScale {
  from {
    opacity: 0;
    transform: scale(0.88);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
.reveal .styled-table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  font-size: 0.82em;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: var(--card-shadow);
}
.reveal .styled-table thead th {
  background: rgba(240, 147, 251, 0.12);
  color: var(--r-heading-color);
  font-weight: 700;
  padding: 14px 20px;
  text-align: left;
  font-size: 0.9em;
  letter-spacing: 0.02em;
  border-bottom: 2px solid #f093fb;
}
.reveal .styled-table tbody td {
  padding: 12px 20px;
  border-bottom: 1px solid var(--card-border);
  color: var(--r-body-color);
}
.reveal .styled-table tbody tr {
  background: var(--card-bg);
  transition: background 0.2s;
}
.reveal .styled-table tbody tr:nth-child(even) {
  background: rgba(18, 25, 46, 0.56);
}
.reveal .styled-table tbody tr:hover {
  background: rgba(240, 147, 251, 0.12);
}
@media (max-width: 1200px) {
  .reveal .slides section {
    padding: 20px 24px 30px;
  }
  .reveal .two-col,
  .reveal .card-grid,
  .reveal .compare-table {
    grid-template-columns: 1fr;
  }
  .reveal .flow-diagram {
    flex-direction: column;
  }
  .reveal .flow-arrow {
    transform: rotate(90deg);
  }
}
.reveal .fade-up {
  will-change: transform, opacity;
}
.reveal .code-showcase {
  width: 100%;
}
.reveal pre code.language-js,
.reveal pre code.language-xxx {
  font-family: var(--r-code-font);
}
.reveal .progress {
  height: 4px;
  color: #e94560;
  background: rgba(255, 255, 255, 0.06);
}
.reveal .progress span {
  background: linear-gradient(90deg, #e94560 0%, #533483 60%, #16c79a 100%);
  box-shadow: 0 0 14px rgba(233, 69, 96, 0.16);
}
.reveal .fragment.highlight-current-blue.visible {
  color: var(--accent-info);
  text-shadow: 0 0 10px rgba(22, 199, 154, 0.12);
}
```

## ECharts Palette
```js
const gradientStoryPalette = ['#e94560', '#16c79a', '#533483', '#f5a623', '#0f3460'];

const gradientStoryEChartsTheme = {
  color: ['#e94560', '#16c79a', '#533483', '#f5a623', '#0f3460'],
  backgroundColor: 'transparent',
  textStyle: {
    color: '#eaeaea',
    fontFamily: 'Segoe UI, PingFang SC, Microsoft YaHei, system-ui, sans-serif'
  },
  title: {
    textStyle: { color: '#ffffff', fontWeight: 700 },
    subtextStyle: { color: '#b8b8d0' }
  },
  legend: {
    textStyle: { color: '#d7d6e8' },
    pageTextStyle: { color: '#d7d6e8' }
  },
  tooltip: {
    backgroundColor: 'rgba(18, 25, 46, 0.94)',
    borderColor: '#e94560',
    borderWidth: 1,
    textStyle: { color: '#eaeaea' },
    extraCssText: 'box-shadow: 0 18px 42px rgba(4, 8, 20, 0.32); border-radius: 14px;'
  },
  grid: {
    left: 56,
    right: 28,
    top: 54,
    bottom: 48,
    containLabel: true
  },
  categoryAxis: {
    axisLine: { lineStyle: { color: 'rgba(184,184,208,0.34)' } },
    axisTick: { lineStyle: { color: 'rgba(184,184,208,0.34)' } },
    axisLabel: { color: '#d7d6e8' },
    splitLine: { show: false },
    nameTextStyle: { color: '#d7d6e8' }
  },
  valueAxis: {
    axisLine: { show: true, lineStyle: { color: 'rgba(184,184,208,0.34)' } },
    axisTick: { show: false },
    axisLabel: { color: '#d7d6e8' },
    splitLine: { lineStyle: { color: 'rgba(184,184,208,0.08)' } },
    nameTextStyle: { color: '#d7d6e8' }
  },
  timeAxis: {
    axisLine: { lineStyle: { color: 'rgba(184,184,208,0.34)' } },
    axisLabel: { color: '#d7d6e8' },
    splitLine: { lineStyle: { color: 'rgba(184,184,208,0.08)' } },
    nameTextStyle: { color: '#d7d6e8' }
  },
  logAxis: {
    axisLine: { lineStyle: { color: 'rgba(184,184,208,0.34)' } },
    axisLabel: { color: '#d7d6e8' },
    splitLine: { lineStyle: { color: 'rgba(184,184,208,0.08)' } },
    nameTextStyle: { color: '#d7d6e8' }
  },
  toolbox: {
    iconStyle: {
      borderColor: '#d7d6e8'
    },
    emphasis: {
      iconStyle: {
        borderColor: '#e94560'
      }
    }
  },
  dataZoom: {
    textStyle: { color: '#d7d6e8' },
    borderColor: 'rgba(255,255,255,0.12)',
    fillerColor: 'rgba(233,69,96,0.18)',
    handleStyle: { color: '#e94560' }
  },
  line: {
    smooth: true,
    symbol: 'circle',
    symbolSize: 8,
    lineStyle: { width: 3 },
    itemStyle: {
      borderWidth: 2,
      borderColor: '#1a1a2e'
    }
  },
  bar: {
    itemStyle: {
      borderRadius: [10, 10, 4, 4]
    }
  },
  pie: {
    itemStyle: {
      borderWidth: 2,
      borderColor: '#1a1a2e'
    },
    label: { color: '#eaeaea' },
    labelLine: { lineStyle: { color: 'rgba(184,184,208,0.3)' } }
  },
  radar: {
    axisName: { color: '#d7d6e8' },
    axisLine: { lineStyle: { color: 'rgba(184,184,208,0.2)' } },
    splitLine: { lineStyle: { color: ['rgba(184,184,208,0.1)'] } },
    splitArea: {
      areaStyle: {
        color: ['rgba(233,69,96,0.04)', 'rgba(83,52,131,0.03)']
      }
    }
  }
};
```

## Image Treatment
- Wrap screenshots, charts, and diagrams in `<div class="img-frame">...</div>` to get rounded 18px corners, subtle white-tinted framing, and balanced padding on the dark gradient canvas.
- The CSS already styles `.img-frame`, `.img-frame img`, `.img-frame svg`, and generic `.reveal img`, so inserted visuals automatically inherit the soft border, gentle shadow, and presentation-safe rounding.
- For story-driven slides, combine `.img-frame` with `.panel` or `.glass-card` so bright visuals sit inside the same narrative card language as the text instead of floating on the background.
- For comparisons or walkthroughs, place two `.img-frame` blocks inside `.two-col`; use `.footer-note` for captions so the visual hierarchy stays clean and understated.

## Theme Auto-select Keywords
gradient story, gradient card, storytelling dark, deep blue gradient, tech blog, learning shares, project summary, open-source intro, migration guide, timeline, tutorial demo, colorful tags, async guide, project retrospective, dark tutorial

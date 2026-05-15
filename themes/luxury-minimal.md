# Luxury Minimal Theme / 奢华极简

Base: `black.min.css` | Highlight: `atom-one-dark.min.css` | Best for: 高端产品、品牌展示、CEO汇报、投资路演

## CDN Links
- reveal.js core CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css`
- reveal.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/black.min.css`
- highlight.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/atom-one-dark.min.css`

## Complete CSS
```css
:root {
  --r-background-color: #0d0d0d;
  --r-main-font: "Segoe UI", "PingFang SC", "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif;
  --r-heading-font: "Segoe UI", "PingFang SC", "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif;
  --r-code-font: "Cascadia Code", "Fira Code", Consolas, monospace;
  --r-main-color: #f0ece2;
  --r-heading-color: #f0ece2;
  --r-link-color: #c9a96e;
  --r-link-color-hover: #d4af37;
  --r-selection-background-color: rgba(201, 169, 110, 0.24);
  --r-body-color: #f0ece2;
  --r-muted-color: #a09880;
  --r-strong-color: #d4af37;
  --r-soft-color: #6b6355;
  --surface-card: rgba(201, 169, 110, 0.06);
  --surface-border: rgba(201, 169, 110, 0.15);
  --surface-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
  --accent-primary: #c9a96e;
  --accent-secondary: #b8860b;
  --accent-tertiary: #d4af37;
  --accent-soft: rgba(201, 169, 110, 0.08);
  --accent-line: rgba(201, 169, 110, 0.72);
}
.reveal {
  position: relative;
  background: #0d0d0d;
  color: var(--r-main-color);
  font-family: var(--r-main-font);
}
.reveal::before {
  content: "";
  position: absolute;
  inset: 18px;
  border: 1px solid rgba(201, 169, 110, 0.05);
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
  padding: 60px 50px 44px;
  overflow: hidden;
  box-sizing: border-box;
}
.reveal h1,
.reveal h2,
.reveal h3,
.reveal h4 {
  margin: 0 0 0.52em;
  font-family: var(--r-heading-font);
  text-transform: none;
}
.reveal h1 {
  color: var(--accent-primary);
  font-size: 2.5em;
  font-weight: 300;
  line-height: 1.08;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 0.26em;
}
.reveal h2 {
  color: var(--r-heading-color);
  font-size: 1.56em;
  font-weight: 300;
  letter-spacing: 0.04em;
}
.reveal h3 {
  color: #dcc08f;
  font-size: 1.06em;
  font-weight: 400;
  letter-spacing: 0.03em;
}
.reveal h4 {
  color: var(--r-muted-color);
  font-size: 0.78em;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.reveal p,
.reveal li {
  color: var(--r-body-color);
  line-height: 1.78;
  font-size: 0.82em;
  font-weight: 400;
}
.reveal strong {
  color: var(--r-strong-color);
  font-weight: 600;
}
.reveal a {
  color: var(--r-link-color);
  text-decoration-color: rgba(201, 169, 110, 0.3);
  transition: color 180ms ease, text-decoration-color 180ms ease;
}
.reveal a:hover {
  color: var(--r-link-color-hover);
  text-decoration-color: rgba(212, 175, 55, 0.5);
}
.reveal ul,
.reveal ol {
  display: block;
  margin: 0.42em 0 0.2em 0.5em;
}
.reveal li + li {
  margin-top: 0.5em;
}
.reveal .slides section.title-slide {
  display: flex;
  flex-direction: column;
  justify-content: center !important;
  align-items: flex-start;
  text-align: left;
  gap: 16px;
}
.reveal .hero-title {
  width: 100%;
  max-width: 1400px;
  white-space: nowrap;
  text-align: center;
  font-size: 2.22em;
  line-height: 1.08;
  margin-bottom: 0;
  animation: slideInUp 1s ease-out both, glowPulse 6s ease-in-out 1.2s infinite;
}
.reveal .subtitle,
.reveal .meta {
  color: var(--r-muted-color);
  font-size: 0.74em;
}
.reveal .subtitle {
  max-width: 920px;
  font-size: 0.96em;
  letter-spacing: 0.02em;
}
.reveal .meta {
  font-size: 0.74em;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
.reveal .accent-line {
  width: 88px;
  height: 1px;
  background: var(--accent-line);
  margin: 10px 0 18px;
}
.reveal .title-slide .panel {
  width: 100%;
  max-width: 920px;
}
.reveal .panel,
.reveal .glass-card,
.reveal .info-card,
.reveal .compare-col,
.reveal .flow-node,
.reveal .stat-item,
.reveal .img-frame {
  background: var(--surface-card);
  border: 1px solid var(--surface-border);
  box-shadow: var(--surface-shadow);
}
.reveal .panel,
.reveal .glass-card {
  border-radius: 18px;
  padding: 22px 24px;
  border-top: 3px solid #d4a574;
  background: linear-gradient(180deg, rgba(212, 165, 116, 0.04) 0%, var(--surface-card) 40%);
}
.reveal .tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 16px;
  border-radius: 999px;
  background: transparent;
  border: 1px solid rgba(201, 169, 110, 0.35);
  color: var(--accent-primary);
  font-size: 0.66em;
  letter-spacing: 0.18em;
  text-transform: uppercase;
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
  padding: 24px 18px;
  border-radius: 18px;
  background: rgba(201, 169, 110, 0.05);
  min-width: 220px;
}
.reveal .stat-number {
  font-size: 2.4em;
  line-height: 1;
  font-weight: 300;
  color: var(--accent-primary);
  letter-spacing: 0.04em;
  margin-bottom: 12px;
}
.reveal .stat-label {
  color: var(--r-muted-color);
  font-size: 0.74em;
  letter-spacing: 0.14em;
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
  width: 1px;
  background: rgba(201, 169, 110, 0.28);
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
  background: #111111;
  border: 1px solid rgba(201, 169, 110, 0.38);
  color: var(--accent-primary);
  font-size: 0.78em;
  font-weight: 500;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.32);
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
  color: var(--r-heading-color);
  font-size: 0.86em;
}
.reveal .timeline-content p {
  font-size: 0.76em;
  color: #d8d1c4;
}
.reveal .card-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px;
  margin-top: 16px;
}
.reveal .info-card {
  border-radius: 18px;
  padding: 22px 24px 20px;
  animation: fadeInScale 1.05s ease-out both;
}
.reveal .info-card h3,
.reveal .compare-col h3,
.reveal .panel h3,
.reveal .glass-card h3 {
  margin-top: 0;
  background: linear-gradient(135deg, #d4a574, #c9a96e);
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
  background: rgba(212, 175, 55, 0.12);
  color: #d4af37;
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
  background: rgba(107, 99, 85, 0.16);
  border-color: rgba(160, 152, 128, 0.18);
}
.reveal .compare-good {
  background: rgba(201, 169, 110, 0.09);
  border-color: rgba(201, 169, 110, 0.24);
}
.reveal .flow-diagram {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 18px;
  flex-wrap: wrap;
  margin-top: 20px;
}
.reveal .flow-node {
  min-width: 160px;
  padding: 22px 26px;
  border-radius: 18px;
  text-align: center;
}
.reveal .flow-arrow {
  color: var(--accent-primary);
  font-size: 1.02em;
  font-weight: 300;
}
.reveal pre,
.reveal .code-showcase pre {
  width: 100%;
  margin: 0;
  border-radius: 16px;
  overflow: hidden;
  background: #121110;
  border: 1px solid rgba(201, 169, 110, 0.16);
  box-shadow: 0 14px 30px rgba(0, 0, 0, 0.32);
}
.reveal pre code,
.reveal .code-showcase pre code {
  max-height: 480px;
  padding: 1.25em 1.35em;
  font-family: var(--r-code-font);
  font-size: 0.7em;
  line-height: 1.62;
  border-radius: 16px;
  background: #121110;
  color: #f0ece2;
}
.reveal .img-frame {
  border-radius: 20px;
  padding: 14px;
  overflow: hidden;
  background: rgba(201, 169, 110, 0.04);
  box-shadow: 0 0 0 1px rgba(201, 169, 110, 0.08), 0 16px 28px rgba(0, 0, 0, 0.34);
}
.reveal .img-frame img,
.reveal .img-frame svg,
.reveal img {
  display: block;
  width: 100%;
  border-radius: 14px;
  border: 1px solid rgba(201, 169, 110, 0.14);
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
  border-left: 2px solid var(--accent-primary);
  border-radius: 0 14px 14px 0;
  background: rgba(201, 169, 110, 0.04);
  color: #e8dfcf;
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.22);
  font-style: italic;
  max-width: 1180px;
}
.reveal .slides section.end-slide {
  display: flex;
  flex-direction: column;
  justify-content: center !important;
  align-items: center;
  text-align: center;
  gap: 16px;
}
.reveal .end-slide h2 {
  color: var(--accent-primary);
  padding-left: 0;
  font-size: 2.45em;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.reveal .end-slide p {
  max-width: 760px;
  text-align: center;
}
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(48px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes glowPulse {
  0%,
  100% {
    text-shadow: 0 0 0 rgba(201, 169, 110, 0);
  }
  50% {
    text-shadow: 0 0 18px rgba(201, 169, 110, 0.12);
  }
}
@keyframes fadeInScale {
  from {
    opacity: 0;
    transform: scale(0.97);
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
  border-radius: 10px;
  overflow: hidden;
  box-shadow: var(--surface-shadow);
}
.reveal .styled-table thead th {
  background: rgba(212, 165, 116, 0.1);
  color: var(--r-heading-color);
  font-weight: 700;
  padding: 14px 20px;
  text-align: left;
  font-size: 0.9em;
  letter-spacing: 0.08em;
  border-bottom: 2px solid #d4a574;
}
.reveal .styled-table tbody td {
  padding: 12px 20px;
  border-bottom: 1px solid var(--surface-border);
  color: var(--r-body-color);
}
.reveal .styled-table tbody tr {
  background: var(--surface-card);
  transition: background 0.2s;
}
.reveal .styled-table tbody tr:nth-child(even) {
  background: rgba(17, 17, 17, 0.88);
}
.reveal .styled-table tbody tr:hover {
  background: rgba(212, 165, 116, 0.1);
}
@media (max-width: 1200px) {
  .reveal .slides section {
    padding: 24px 28px 40px;
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
  height: 2px;
  color: var(--accent-primary);
  background: rgba(201, 169, 110, 0.08);
}
.reveal .progress span {
  background: var(--accent-primary);
  box-shadow: 0 0 14px rgba(201, 169, 110, 0.2);
}
.reveal .fragment.highlight-current-blue.visible {
  color: var(--accent-primary);
  text-shadow: 0 0 12px rgba(201, 169, 110, 0.18);
}
```

## ECharts Palette
```js
const luxuryMinimalPalette = ['#c9a96e', '#d4af37', '#b8860b', '#f0ece2', '#6b6355'];

const luxuryMinimalEChartsTheme = {
  color: ['#c9a96e', '#d4af37', '#b8860b', '#f0ece2', '#6b6355'],
  backgroundColor: 'transparent',
  textStyle: {
    color: '#f0ece2',
    fontFamily: 'Segoe UI, PingFang SC, Microsoft YaHei, Helvetica Neue, Arial, sans-serif'
  },
  title: {
    textStyle: { color: '#c9a96e', fontWeight: 400 },
    subtextStyle: { color: '#a09880' }
  },
  legend: {
    textStyle: { color: '#d9d0c1' },
    pageTextStyle: { color: '#d9d0c1' }
  },
  tooltip: {
    backgroundColor: 'rgba(13, 13, 13, 0.96)',
    borderColor: '#c9a96e',
    borderWidth: 1,
    textStyle: { color: '#f0ece2' },
    extraCssText: 'box-shadow: 0 18px 36px rgba(0, 0, 0, 0.45); border-radius: 10px;'
  },
  grid: {
    left: 56,
    right: 28,
    top: 54,
    bottom: 48,
    containLabel: true
  },
  categoryAxis: {
    axisLine: { lineStyle: { color: 'rgba(160, 152, 128, 0.32)' } },
    axisTick: { lineStyle: { color: 'rgba(160, 152, 128, 0.22)' } },
    axisLabel: { color: '#d9d0c1' },
    splitLine: { show: false },
    nameTextStyle: { color: '#d9d0c1' }
  },
  valueAxis: {
    axisLine: { show: true, lineStyle: { color: 'rgba(160, 152, 128, 0.32)' } },
    axisTick: { show: false },
    axisLabel: { color: '#d9d0c1' },
    splitLine: { lineStyle: { color: 'rgba(201, 169, 110, 0.12)' } },
    nameTextStyle: { color: '#d9d0c1' }
  },
  timeAxis: {
    axisLine: { lineStyle: { color: 'rgba(160, 152, 128, 0.32)' } },
    axisLabel: { color: '#d9d0c1' },
    splitLine: { lineStyle: { color: 'rgba(201, 169, 110, 0.12)' } },
    nameTextStyle: { color: '#d9d0c1' }
  },
  logAxis: {
    axisLine: { lineStyle: { color: 'rgba(160, 152, 128, 0.32)' } },
    axisLabel: { color: '#d9d0c1' },
    splitLine: { lineStyle: { color: 'rgba(201, 169, 110, 0.12)' } },
    nameTextStyle: { color: '#d9d0c1' }
  },
  toolbox: {
    iconStyle: {
      borderColor: '#d9d0c1'
    },
    emphasis: {
      iconStyle: {
        borderColor: '#c9a96e'
      }
    }
  },
  dataZoom: {
    textStyle: { color: '#d9d0c1' },
    borderColor: 'rgba(201, 169, 110, 0.16)',
    fillerColor: 'rgba(201, 169, 110, 0.16)',
    handleStyle: { color: '#c9a96e' }
  },
  line: {
    smooth: true,
    symbol: 'circle',
    symbolSize: 8,
    lineStyle: { width: 3 },
    itemStyle: {
      borderWidth: 2,
      borderColor: '#0d0d0d'
    }
  },
  bar: {
    itemStyle: {
      borderRadius: [8, 8, 2, 2]
    }
  },
  pie: {
    itemStyle: {
      borderWidth: 2,
      borderColor: '#0d0d0d'
    },
    label: { color: '#f0ece2' },
    labelLine: { lineStyle: { color: 'rgba(201, 169, 110, 0.24)' } }
  },
  radar: {
    axisName: { color: '#d9d0c1' },
    axisLine: { lineStyle: { color: 'rgba(201, 169, 110, 0.18)' } },
    splitLine: { lineStyle: { color: ['rgba(201, 169, 110, 0.12)'] } },
    splitArea: {
      areaStyle: {
        color: ['rgba(201, 169, 110, 0.04)', 'rgba(107, 99, 85, 0.06)']
      }
    }
  }
};
```

## Image Treatment
- Wrap screenshots, UI mockups, and diagrams in `<div class="img-frame">...</div>` so the visual gets a thin gold border, disciplined padding, and a restrained luxury shadow instead of a loud card treatment.
- The CSS styles `.img-frame`, `.img-frame img`, `.img-frame svg`, and generic `.reveal img`, so copied visuals automatically inherit rounded corners, a subtle metallic outline, and a gallery-like presentation.
- For image-heavy slides, place the visual inside `.img-frame` and optionally pair it with `.panel` or `.glass-card` to keep the composition grounded while preserving the extreme whitespace that defines this style.
- For side-by-side visuals, use two `.img-frame` blocks inside `.two-col`; keep captions minimal with `.footer-note` so the slide still feels premium, calm, and uncluttered.

## Theme Auto-select Keywords
奢华极简, luxury minimal, 极简黑金, black gold, luxe dark, premium minimal, 高端汇报, 品牌展示, CEO 汇报, 投资路演, 年度总结, 董事会汇报, 高端产品发布, executive presentation, luxury brand



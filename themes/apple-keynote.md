# Apple Keynote Theme

Base: `white.min.css` | Highlight: `github.min.css` | Best for: Product launches, business reports, UX sharing

## CDN Links
- reveal.js core CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css`
- reveal.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/white.min.css`
- highlight.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/github.min.css`

## Complete CSS
```css
:root {
  --r-background-color: #ffffff;
  --r-main-font: -apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "Segoe UI", "PingFang SC", "Microsoft YaHei", system-ui, sans-serif;
  --r-heading-font: -apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "Segoe UI", "PingFang SC", "Microsoft YaHei", system-ui, sans-serif;
  --r-code-font: "SFMono-Regular", "Cascadia Code", Consolas, monospace;
  --r-main-color: #1d1d1f;
  --r-heading-color: #1d1d1f;
  --r-link-color: #0071e3;
  --r-link-color-hover: #005bb5;
  --r-selection-background-color: rgba(0, 113, 227, 0.18);
  --r-body-color: #1d1d1f;
  --r-muted-color: #86868b;
  --r-strong-color: #1d1d1f;
  --card-bg: #f5f5f7;
  --card-border: rgba(0, 0, 0, 0.06);
  --card-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
  --card-shadow-hover: 0 10px 28px rgba(0, 0, 0, 0.1);
  --accent-primary: #0071e3;
  --accent-secondary: #1d1d1f;
  --accent-success: #34c759;
  --accent-warning: #ff9500;
  --accent-danger: #ff3b30;
  --accent-purple: #5856d6;
  --accent-soft: rgba(0, 113, 227, 0.08);
  --line-subtle: rgba(29, 29, 31, 0.1);
  --highlight-bg: linear-gradient(to bottom, transparent 60%, rgba(0, 113, 227, 0.15) 60%);
}
.reveal {
  position: relative;
  background: #ffffff;
  color: var(--r-main-color);
  font-family: var(--r-main-font);
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
  padding: 60px 48px 42px;
  overflow: hidden;
  box-sizing: border-box;
}
.reveal h1,
.reveal h2,
.reveal h3,
.reveal h4 {
  margin: 0 0 0.45em;
  font-family: var(--r-heading-font);
  letter-spacing: -0.03em;
  text-transform: none;
}
.reveal h1 {
  color: var(--r-heading-color);
  font-size: 2.46em;
  font-weight: 700;
  line-height: 1.03;
  margin-bottom: 0.26em;
}
.reveal h2 {
  color: var(--r-heading-color);
  font-size: 1.46em;
  font-weight: 650;
  line-height: 1.18;
  padding-bottom: 0.3em;
  border-bottom: 2px solid rgba(0, 113, 227, 0.18);
}
.reveal h3 {
  color: var(--r-heading-color);
  font-size: 1.08em;
  font-weight: 600;
}
.reveal h4 {
  color: #424245;
  font-size: 0.82em;
  font-weight: 600;
  letter-spacing: 0;
}
.reveal p,
.reveal li {
  color: #424245;
  line-height: 1.7;
  font-size: 0.82em;
  font-weight: 400;
}
.reveal strong,
.reveal .highlight-word {
  color: var(--r-strong-color);
  font-weight: 650;
  background: var(--highlight-bg);
}
.reveal a {
  color: var(--r-link-color);
  text-decoration-color: rgba(0, 113, 227, 0.28);
  text-underline-offset: 0.12em;
}
.reveal ul,
.reveal ol {
  display: block;
  margin: 0.4em 0 0.2em 0.5em;
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
  gap: 12px;
}
.reveal .hero-title {
  width: 100%;
  max-width: 1400px;
  white-space: nowrap;
  text-align: center;
  font-size: 2.56em;
  line-height: 1.02;
  margin-bottom: 0.08em;
  animation: slideInUp 0.9s cubic-bezier(0.22, 1, 0.36, 1) both, glowPulse 5.2s ease-in-out 1s infinite;
}
.reveal .subtitle,
.reveal .meta {
  color: #6e6e73;
  font-size: 0.74em;
}
.reveal .subtitle {
  font-size: 0.98em;
  max-width: 920px;
  line-height: 1.62;
}
.reveal .meta {
  font-size: 0.74em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
.reveal .accent-line {
  width: 104px;
  height: 4px;
  border-radius: 999px;
  background: #0071e3;
  box-shadow: 0 4px 14px rgba(0, 113, 227, 0.16);
  margin: 14px auto 20px;
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
  border-radius: 22px;
  padding: 22px 24px;
  border-top: 3px solid #0071e3;
  background: linear-gradient(180deg, rgba(0, 113, 227, 0.04) 0%, var(--card-bg) 40%);
}
.reveal .tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  border-radius: 999px;
  background: rgba(0, 113, 227, 0.08);
  border: 1px solid rgba(0, 113, 227, 0.12);
  color: var(--accent-primary);
  font-size: 0.66em;
  font-weight: 600;
  letter-spacing: 0.08em;
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
  padding: 22px 18px;
  border-radius: 22px;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  min-width: 220px;
}
.reveal .stat-number {
  font-size: 2.34em;
  line-height: 1;
  font-weight: 700;
  color: var(--accent-secondary);
  margin-bottom: 10px;
}
.reveal .stat-label {
  color: #6e6e73;
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
  background: rgba(0, 113, 227, 0.14);
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
  background: #ffffff;
  color: var(--accent-primary);
  border: 2px solid rgba(0, 113, 227, 0.24);
  font-size: 0.78em;
  font-weight: 700;
  box-shadow: 0 8px 20px rgba(0, 113, 227, 0.12);
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
  color: #6e6e73;
}
.reveal .card-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px;
  margin-top: 16px;
}
.reveal .info-card {
  border-radius: 22px;
  padding: 22px 22px 20px;
  border: 1px solid #d2d2d7;
  animation: fadeInScale 0.7s ease-out both;
}
.reveal .info-card h3,
.reveal .compare-col h3,
.reveal .panel h3,
.reveal .glass-card h3 {
  margin-top: 0;
  color: #0071e3;
}
.reveal .icon-wrap {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 14px;
  background: rgba(0, 113, 227, 0.1);
  color: #0071e3;
}
.reveal .compare-table {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
  gap: 24px;
  margin-top: 16px;
}
.reveal .compare-col {
  border-radius: 22px;
  padding: 22px 24px;
}
.reveal .compare-bad {
  background: rgba(255, 59, 48, 0.06);
  border-color: rgba(255, 59, 48, 0.14);
}
.reveal .compare-good {
  background: rgba(52, 199, 89, 0.08);
  border-color: rgba(52, 199, 89, 0.16);
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
  padding: 18px 20px;
  border-radius: 22px;
  min-width: 150px;
  text-align: center;
}
.reveal .flow-arrow {
  color: var(--accent-primary);
  font-size: 1.1em;
  font-weight: 700;
}
.reveal pre {
  width: 100%;
  margin: 0;
  border-radius: 22px;
  overflow: hidden;
  background: #f5f5f7;
  box-shadow: var(--card-shadow);
  border: 1px solid var(--card-border);
}
.reveal pre code {
  max-height: 480px;
  padding: 1.25em 1.35em;
  font-family: var(--r-code-font);
  font-size: 0.7em;
  line-height: 1.58;
  color: #1d1d1f;
  background: #f5f5f7;
  border-radius: 22px;
}
.reveal .img-frame {
  border-radius: 26px;
  padding: 14px;
  overflow: hidden;
  background: #ffffff;
  box-shadow: 0 8px 26px rgba(0, 0, 0, 0.08);
}
.reveal .img-frame img,
.reveal .img-frame svg,
.reveal img {
  display: block;
  width: 100%;
  border-radius: 18px;
  border: 1px solid rgba(0, 0, 0, 0.05);
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
  border-left: 4px solid var(--accent-primary);
  border-radius: 0 22px 22px 0;
  background: rgba(0, 113, 227, 0.05);
  color: var(--accent-secondary);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
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
  border-bottom: none;
  padding-bottom: 0;
  font-size: 2.4em;
}
.reveal .end-slide p {
  max-width: 760px;
  text-align: center;
}
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(44px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes glowPulse {
  0%,
  100% {
    text-shadow: 0 0 0 rgba(0, 113, 227, 0);
  }
  50% {
    text-shadow: 0 8px 22px rgba(0, 113, 227, 0.12);
  }
}
@keyframes fadeInScale {
  from {
    opacity: 0;
    transform: scale(0.96);
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
  background: rgba(0, 113, 227, 0.08);
  color: var(--r-heading-color);
  font-weight: 700;
  padding: 14px 20px;
  text-align: left;
  font-size: 0.9em;
  letter-spacing: 0.02em;
  border-bottom: 2px solid var(--accent-primary);
}
.reveal .styled-table tbody td {
  padding: 12px 20px;
  border-bottom: 1px solid var(--card-border);
  color: var(--r-body-color);
}
.reveal .styled-table tbody tr {
  background: #ffffff;
  transition: background 0.2s;
}
.reveal .styled-table tbody tr:nth-child(even) {
  background: rgba(0, 113, 227, 0.03);
}
.reveal .styled-table tbody tr:hover {
  background: rgba(0, 113, 227, 0.08);
}
@media (max-width: 1200px) {
  .reveal .slides section {
    padding: 24px 28px 34px;
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
  .reveal .hero-title {
    font-size: 2.7em;
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
  color: #0071e3;
  background: rgba(0, 0, 0, 0.06);
}
.reveal .progress span {
  background: #0071e3;
  box-shadow: 0 0 12px rgba(0, 113, 227, 0.18);
}
.reveal .fragment.highlight-current-blue.visible {
  color: var(--accent-primary);
  background: var(--highlight-bg);
}
```

## ECharts Palette
```js
const appleKeynotePalette = ['#0071e3', '#34c759', '#ff9500', '#ff3b30', '#5856d6'];

const appleKeynoteEChartsTheme = {
  color: ['#0071e3', '#34c759', '#ff9500', '#ff3b30', '#5856d6'],
  backgroundColor: 'transparent',
  textStyle: {
    color: '#1d1d1f',
    fontFamily: '-apple-system, BlinkMacSystemFont, SF Pro Display, SF Pro Text, Segoe UI, PingFang SC, Microsoft YaHei, system-ui, sans-serif'
  },
  title: {
    textStyle: { color: '#1d1d1f', fontWeight: 700 },
    subtextStyle: { color: '#6e6e73' }
  },
  legend: {
    textStyle: { color: '#424245' },
    pageTextStyle: { color: '#424245' }
  },
  tooltip: {
    backgroundColor: '#ffffff',
    borderColor: 'rgba(0, 0, 0, 0.08)',
    borderWidth: 1,
    textStyle: { color: '#1d1d1f' },
    extraCssText: 'box-shadow: 0 10px 28px rgba(0,0,0,0.10); border-radius: 16px; padding: 12px 14px;'
  },
  grid: {
    left: 56,
    right: 28,
    top: 54,
    bottom: 48,
    containLabel: true
  },
  categoryAxis: {
    axisLine: { lineStyle: { color: 'rgba(29,29,31,0.16)' } },
    axisTick: { lineStyle: { color: 'rgba(29,29,31,0.16)' } },
    axisLabel: { color: '#6e6e73' },
    splitLine: { show: false },
    nameTextStyle: { color: '#6e6e73' }
  },
  valueAxis: {
    axisLine: { show: true, lineStyle: { color: 'rgba(29,29,31,0.16)' } },
    axisTick: { show: false },
    axisLabel: { color: '#6e6e73' },
    splitLine: { lineStyle: { color: 'rgba(29,29,31,0.08)' } },
    nameTextStyle: { color: '#6e6e73' }
  },
  timeAxis: {
    axisLine: { lineStyle: { color: 'rgba(29,29,31,0.16)' } },
    axisLabel: { color: '#6e6e73' },
    splitLine: { lineStyle: { color: 'rgba(29,29,31,0.08)' } },
    nameTextStyle: { color: '#6e6e73' }
  },
  logAxis: {
    axisLine: { lineStyle: { color: 'rgba(29,29,31,0.16)' } },
    axisLabel: { color: '#6e6e73' },
    splitLine: { lineStyle: { color: 'rgba(29,29,31,0.08)' } },
    nameTextStyle: { color: '#6e6e73' }
  },
  toolbox: {
    iconStyle: {
      borderColor: '#6e6e73'
    },
    emphasis: {
      iconStyle: {
        borderColor: '#0071e3'
      }
    }
  },
  dataZoom: {
    textStyle: { color: '#6e6e73' },
    borderColor: 'rgba(29,29,31,0.08)',
    fillerColor: 'rgba(0,113,227,0.12)',
    handleStyle: { color: '#0071e3' }
  },
  line: {
    smooth: true,
    symbol: 'circle',
    symbolSize: 8,
    lineStyle: { width: 3 },
    itemStyle: {
      borderWidth: 2,
      borderColor: '#ffffff'
    }
  },
  bar: {
    itemStyle: {
      borderRadius: [12, 12, 6, 6]
    }
  },
  pie: {
    itemStyle: {
      borderWidth: 2,
      borderColor: '#ffffff'
    },
    label: { color: '#1d1d1f' },
    labelLine: { lineStyle: { color: 'rgba(29,29,31,0.18)' } }
  },
  radar: {
    axisName: { color: '#6e6e73' },
    axisLine: { lineStyle: { color: 'rgba(29,29,31,0.14)' } },
    splitLine: { lineStyle: { color: ['rgba(29,29,31,0.08)'] } },
    splitArea: {
      areaStyle: {
        color: ['rgba(0,113,227,0.03)', 'rgba(0,113,227,0.015)']
      }
    }
  }
};
```

## Image Treatment
- Wrap screenshots, UI mockups, and product renders in `<div class="img-frame">...</div>` to get Apple-like white framing, generous padding, rounded corners, and a soft product-shot shadow.
- The CSS already styles `.img-frame`, `.img-frame img`, `.img-frame svg`, and generic `.reveal img` so pasted visuals inherit clean borders, white space, and presentation-safe rounding.
- For interface walkthroughs, pair `.img-frame` with `.panel` or `.glass-card` so charts and screenshots sit on a light-gray surface instead of floating on the white canvas.
- For product comparisons, place two `.img-frame` blocks inside `.two-col`; for hero visuals, keep captions minimal with `.footer-note` to preserve the keynote-style restraint.

## Theme Auto-select Keywords
apple keynote, apple style, keynote, clean white, minimal launch, product release, business report, user experience, UX sharing, minimal cards, whitespace, blue accents, keynote style

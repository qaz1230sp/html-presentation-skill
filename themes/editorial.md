# Editorial Theme

Base: `white.min.css` | Highlight: `stackoverflow-light.min.css` | Best for: Academic reports, industry analysis, data reports, research sharing

## CDN Links
- reveal.js core CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css`
- reveal.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/white.min.css`
- highlight.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/stackoverflow-light.min.css`

## Complete CSS
```css
:root {
  --r-background-color: #fafaf8;
  --r-main-font: "Segoe UI", system-ui, sans-serif;
  --r-heading-font: "Georgia", "Noto Serif SC", "Times New Roman", serif;
  --r-code-font: "Cascadia Code", "Fira Code", Consolas, monospace;
  --r-main-color: #2c3e50;
  --r-heading-color: #1a1a1a;
  --r-link-color: #2980b9;
  --r-link-color-hover: #1f6692;
  --r-selection-background-color: rgba(192, 57, 43, 0.16);
  --r-body-color: #2c3e50;
  --r-muted-color: #95a5a6;
  --r-strong-color: #c0392b;
  --paper-bg: #fafaf8;
  --paper-panel: #ffffff;
  --paper-border: rgba(0, 0, 0, 0.08);
  --paper-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
  --rule-color: rgba(44, 62, 80, 0.18);
  --accent-primary: #c0392b;
  --accent-secondary: #2c3e50;
  --accent-tertiary: #27ae60;
  --accent-info: #2980b9;
  --accent-warm: #f4efe6;
}
.reveal {
  position: relative;
  background:
    linear-gradient(180deg, rgba(255, 255, 255, 0.65), rgba(255, 255, 255, 0) 22%),
    linear-gradient(90deg, rgba(44, 62, 80, 0.03) 0, rgba(44, 62, 80, 0.03) 1px, transparent 1px, transparent 100%),
    linear-gradient(180deg, #fafaf8 0%, #f5f3ee 100%);
  background-size: auto, 32px 32px, auto;
  color: var(--r-main-color);
  font-family: var(--r-main-font);
}
.reveal::before {
  content: "";
  position: absolute;
  inset: 0;
  background:
    linear-gradient(180deg, rgba(0, 0, 0, 0.03), transparent 18%),
    linear-gradient(180deg, transparent 72%, rgba(0, 0, 0, 0.03) 100%);
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
  text-transform: none;
}
.reveal h1 {
  color: var(--r-heading-color);
  font-size: 2.48em;
  font-weight: 700;
  letter-spacing: -0.03em;
  line-height: 1.04;
  margin-bottom: 0.26em;
}
.reveal h2 {
  color: var(--r-heading-color);
  font-size: 1.5em;
  font-weight: 700;
  letter-spacing: -0.02em;
  line-height: 1.18;
  padding-bottom: 0.22em;
  border-bottom: 1px solid rgba(44, 62, 80, 0.18);
}
.reveal h3 {
  color: var(--accent-secondary);
  font-size: 1.06em;
  font-weight: 700;
}
.reveal h4 {
  color: var(--accent-primary);
  font-size: 0.84em;
  font-weight: 700;
  letter-spacing: 0.02em;
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
  color: var(--accent-info);
  text-decoration: underline;
  text-decoration-color: rgba(41, 128, 185, 0.4);
  text-underline-offset: 0.14em;
}
.reveal blockquote {
  width: 100%;
  margin: 1.1em 0 0;
  padding: 18px 22px;
  border-left: 5px solid var(--accent-primary);
  background: #f4efe6;
  color: #4a4039;
  font-family: var(--r-heading-font);
  font-size: 0.96em;
  font-style: italic;
  line-height: 1.58;
  border-radius: 0 4px 4px 0;
  box-shadow: none;
}
.reveal ul,
.reveal ol {
  display: block;
  margin: 0.36em 0 0.2em 0.45em;
  padding-left: 0.6em;
}
.reveal li + li {
  margin-top: 0.4em;
}
.reveal .panel li,
.reveal .glass-card li,
.reveal .info-card li,
.reveal .compare-col li {
  font-size: 0.76em;
  color: #5a6a7a;
  line-height: 1.68;
}
.reveal .panel ul,
.reveal .glass-card ul,
.reveal .info-card ul,
.reveal .compare-col ul {
  list-style: none;
  padding-left: 0.2em;
}
.reveal .panel ul li::before,
.reveal .glass-card ul li::before,
.reveal .info-card ul li::before,
.reveal .compare-col ul li::before {
  content: "▸";
  color: var(--accent-primary);
  font-weight: 700;
  margin-right: 0.5em;
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
  font-size: 2.5em;
  line-height: 1.04;
  margin-bottom: 0.08em;
  animation: slideInUp 0.85s ease-out both, glowPulse 6s ease-in-out 1s infinite;
}
.reveal .subtitle,
.reveal .meta {
  color: #5d6d7e;
  font-size: 0.74em;
}
.reveal .subtitle {
  max-width: 920px;
  font-size: 0.98em;
}
.reveal .meta {
  font-size: 0.74em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
.reveal .accent-line {
  width: 104px;
  height: 2px;
  background: var(--accent-primary);
  margin: 14px auto 18px;
}
.reveal .panel,
.reveal .glass-card,
.reveal .info-card,
.reveal .compare-col,
.reveal .flow-node,
.reveal .stat-item,
.reveal .img-frame {
  background: var(--paper-panel);
  border: 1px solid var(--paper-border);
  box-shadow: var(--paper-shadow);
}
.reveal .panel,
.reveal .glass-card {
  padding: 22px 24px;
  border-radius: 4px;
  border-top: 3px solid var(--accent-primary);
  background: linear-gradient(180deg, rgba(192, 57, 43, 0.04) 0%, var(--paper-panel) 40%);
}
.reveal .tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  border-radius: 999px;
  background: var(--accent-primary);
  color: #ffffff;
  font-size: 0.66em;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  box-shadow: none;
}
.reveal .tag-blue {
  background: var(--accent-info);
}
.reveal .tag-green {
  background: var(--accent-tertiary);
}
.reveal .tag-dark {
  background: var(--accent-secondary);
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
  padding: 22px 18px;
  text-align: center;
  border-radius: 4px;
  min-width: 220px;
}
.reveal .stat-number {
  font-family: var(--r-heading-font);
  font-size: 2.34em;
  line-height: 1;
  font-weight: 700;
  color: var(--accent-primary);
  margin-bottom: 10px;
}
.reveal .stat-label {
  color: #5d6d7e;
  font-size: 0.74em;
  letter-spacing: 0.06em;
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
  background: rgba(44, 62, 80, 0.22);
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
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(192, 57, 43, 0.28);
  background: #fffaf7;
  color: var(--accent-primary);
  border-radius: 999px;
  font-family: var(--r-heading-font);
  font-size: 0.78em;
  font-weight: 700;
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
  color: #5d6d7e;
}
.reveal .card-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px;
  margin-top: 16px;
}
.reveal .info-card {
  padding: 22px 22px 20px;
  border-radius: 4px;
  animation: fadeInScale 0.65s ease-out both;
}
.reveal .info-card h3,
.reveal .compare-col h3,
.reveal .panel h3,
.reveal .glass-card h3 {
  margin-top: 0;
  color: #c0392b;
}
.reveal .icon-wrap {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 14px;
  background: rgba(192, 57, 43, 0.1);
  color: #c0392b;
}
.reveal .compare-table {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
  gap: 24px;
  margin-top: 16px;
}
.reveal .compare-col {
  padding: 22px 24px;
  border-radius: 4px;
  border-top: 3px solid var(--accent-info);
}
.reveal .compare-bad {
  background: #fdf0ee;
  border-color: rgba(192, 57, 43, 0.2);
}
.reveal .compare-good {
  background: #eef8f1;
  border-color: rgba(39, 174, 96, 0.22);
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
  min-width: 150px;
  padding: 16px 20px;
  text-align: center;
  border-radius: 4px;
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
  overflow: hidden;
  border-radius: 4px;
  border: 1px solid rgba(44, 62, 80, 0.12);
  box-shadow: none;
  background: #fcfcfa;
}
.reveal pre code,
.reveal .code-showcase pre code {
  display: block;
  max-height: 480px;
  padding: 1.2em 1.35em;
  font-family: var(--r-code-font);
  font-size: 0.7em;
  line-height: 1.58;
  color: #2c3e50;
  background: #fcfcfa;
  border-radius: 4px;
}
.reveal .img-frame {
  padding: 12px;
  border-radius: 4px;
  overflow: hidden;
}
.reveal .img-frame img,
.reveal .img-frame svg,
.reveal img {
  display: block;
  width: 100%;
  border-radius: 2px;
  border: 1px solid rgba(0, 0, 0, 0.06);
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
  box-shadow: none;
  max-width: 1180px;
  margin: 0 auto;
  padding: 22px 26px;
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
  font-size: 2.36em;
}
.reveal .end-slide p {
  max-width: 760px;
  text-align: center;
}
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes glowPulse {
  0%,
  100% {
    text-shadow: 0 0 0 rgba(192, 57, 43, 0);
  }
  50% {
    text-shadow: 0 1px 0 rgba(192, 57, 43, 0.08);
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
  border-radius: 4px;
  overflow: hidden;
  box-shadow: var(--paper-shadow);
}
.reveal .styled-table thead th {
  background: rgba(192, 57, 43, 0.08);
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
  border-bottom: 1px solid var(--paper-border);
  color: var(--r-body-color);
}
.reveal .styled-table tbody tr {
  background: var(--paper-panel);
  transition: background 0.2s;
}
.reveal .styled-table tbody tr:nth-child(even) {
  background: rgba(244, 239, 230, 0.5);
}
.reveal .styled-table tbody tr:hover {
  background: rgba(192, 57, 43, 0.06);
}
@media (max-width: 1200px) {
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
  color: var(--accent-primary);
  background: rgba(44, 62, 80, 0.08);
}
.reveal .progress span {
  background: var(--accent-primary);
}
.reveal .fragment.highlight-current-blue.visible {
  color: var(--accent-info);
  background: rgba(41, 128, 185, 0.08);
}
```

## ECharts Palette
```js
const editorialPalette = ['#c0392b', '#2980b9', '#27ae60', '#f39c12', '#8e44ad'];

const editorialEChartsTheme = {
  color: ['#c0392b', '#2980b9', '#27ae60', '#f39c12', '#8e44ad'],
  backgroundColor: 'transparent',
  textStyle: {
    color: '#2c3e50',
    fontFamily: 'Segoe UI, system-ui, sans-serif'
  },
  title: {
    textStyle: {
      color: '#1a1a1a',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif',
      fontWeight: 700
    },
    subtextStyle: {
      color: '#5d6d7e'
    }
  },
  legend: {
    textStyle: {
      color: '#2c3e50',
      fontFamily: 'Segoe UI, system-ui, sans-serif'
    },
    pageTextStyle: {
      color: '#2c3e50'
    }
  },
  tooltip: {
    backgroundColor: '#ffffff',
    borderColor: 'rgba(44, 62, 80, 0.22)',
    borderWidth: 1,
    textStyle: {
      color: '#2c3e50',
      fontFamily: 'Segoe UI, system-ui, sans-serif'
    },
    extraCssText: 'box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06); border-radius: 4px;'
  },
  grid: {
    left: 56,
    right: 28,
    top: 54,
    bottom: 48,
    containLabel: true
  },
  categoryAxis: {
    axisLine: { lineStyle: { color: '#2c3e50', width: 1 } },
    axisTick: { lineStyle: { color: '#2c3e50' } },
    axisLabel: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    },
    splitLine: { show: false },
    nameTextStyle: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    }
  },
  valueAxis: {
    axisLine: { show: true, lineStyle: { color: '#2c3e50', width: 1 } },
    axisTick: { show: false },
    axisLabel: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    },
    splitLine: { lineStyle: { color: 'rgba(44, 62, 80, 0.12)' } },
    nameTextStyle: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    }
  },
  timeAxis: {
    axisLine: { lineStyle: { color: '#2c3e50', width: 1 } },
    axisLabel: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    },
    splitLine: { lineStyle: { color: 'rgba(44, 62, 80, 0.12)' } },
    nameTextStyle: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    }
  },
  logAxis: {
    axisLine: { lineStyle: { color: '#2c3e50', width: 1 } },
    axisLabel: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    },
    splitLine: { lineStyle: { color: 'rgba(44, 62, 80, 0.12)' } },
    nameTextStyle: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    }
  },
  toolbox: {
    iconStyle: {
      borderColor: '#2c3e50'
    },
    emphasis: {
      iconStyle: {
        borderColor: '#c0392b'
      }
    }
  },
  dataZoom: {
    textStyle: { color: '#2c3e50' },
    borderColor: 'rgba(44, 62, 80, 0.16)',
    fillerColor: 'rgba(192, 57, 43, 0.12)',
    handleStyle: { color: '#c0392b' }
  },
  line: {
    smooth: true,
    symbol: 'circle',
    symbolSize: 8,
    lineStyle: { width: 3 },
    itemStyle: {
      borderWidth: 2,
      borderColor: '#fafaf8'
    }
  },
  bar: {
    itemStyle: {
      borderRadius: [2, 2, 0, 0]
    }
  },
  pie: {
    itemStyle: {
      borderWidth: 2,
      borderColor: '#fafaf8'
    },
    label: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    },
    labelLine: { lineStyle: { color: 'rgba(44, 62, 80, 0.3)' } }
  },
  radar: {
    axisName: {
      color: '#2c3e50',
      fontFamily: 'Georgia, Noto Serif SC, Times New Roman, serif'
    },
    axisLine: { lineStyle: { color: 'rgba(44, 62, 80, 0.18)' } },
    splitLine: { lineStyle: { color: ['rgba(44, 62, 80, 0.12)'] } },
    splitArea: {
      areaStyle: {
        color: ['rgba(192, 57, 43, 0.03)', 'rgba(44, 62, 80, 0.015)']
      }
    }
  }
};
```

## Image Treatment
- Wrap screenshots, report charts, and scanned figures in `<div class="img-frame">...</div>` to place them on a crisp white mount with a thin editorial border.
- The CSS styles `.img-frame`, `.img-frame img`, `.img-frame svg`, and generic `.reveal img`, so imported visuals inherit a clean print-like frame without blur or heavy shadow.
- For data-led slides, pair `.img-frame` with `.panel` or `.glass-card` so charts sit inside a magazine-style content block rather than floating directly on the page.
- In image-heavy layouts, use `.two-col` with one narrative column and one `.img-frame` column; reserve `.footer-note` for source lines, photo credits, or methodology notes.

## Theme Auto-select Keywords
editorial, magazine style, report design, academic report, industry analysis, data report, research sharing, print layout, serif headings, clean white theme, annual report, insight deck, whitepaper, publication style

# Glassmorphism Theme / 科技玻璃态

Base: `night.min.css` | Highlight: `monokai.min.css` | Best for: 技术分享、架构设计、代码演示

## CDN Links
- reveal.js core CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css`
- reveal.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/night.min.css`
- highlight.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/monokai.min.css`

## Complete CSS
```css
:root {
  --r-background-color: #0b1020;
  --r-main-font: "Segoe UI", "PingFang SC", "Microsoft YaHei", system-ui, sans-serif;
  --r-heading-font: "Segoe UI", "PingFang SC", "Microsoft YaHei", system-ui, sans-serif;
  --r-code-font: "Cascadia Code", "Fira Code", Consolas, monospace;
  --r-main-color: #e6edf7;
  --r-heading-color: #f7f9ff;
  --r-link-color: #667eea;
  --r-link-color-hover: #4facfe;
  --r-selection-background-color: rgba(102, 126, 234, 0.32);
  --r-body-color: #d7e0f2;
  --r-muted-color: #9fb3d9;
  --r-strong-color: #f093fb;
  --glass-bg: rgba(18, 28, 52, 0.58);
  --glass-border: rgba(122, 184, 255, 0.25);
  --glass-shadow: 0 18px 44px rgba(0, 0, 0, 0.32);
  --glass-blur: blur(10px);
  --accent-primary: #667eea;
  --accent-secondary: #764ba2;
  --accent-tertiary: #f093fb;
  --accent-info: #4facfe;
  --accent-success: #43e97b;
  --accent-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 52%, #f093fb 100%);
  --accent-gradient-soft: linear-gradient(135deg, rgba(102, 126, 234, 0.24) 0%, rgba(118, 75, 162, 0.22) 52%, rgba(240, 147, 251, 0.22) 100%);
}
.reveal {
  position: relative;
  background:
    radial-gradient(circle at 88% 12%, rgba(118, 75, 162, 0.3) 0%, transparent 28%),
    radial-gradient(circle at 12% 88%, rgba(79, 172, 254, 0.24) 0%, transparent 26%),
    linear-gradient(135deg, #0b1020 0%, #121a31 52%, #171b2e 100%);
  color: var(--r-main-color);
  font-family: var(--r-main-font);
}
.reveal::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.02), transparent 32%);
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
  letter-spacing: -0.025em;
  text-transform: none;
}
.reveal h1 {
  background: linear-gradient(90deg, #f7f9ff 0%, #a9bcff 34%, #f093fb 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-size: 2.5em;
  font-weight: 900;
  line-height: 1.05;
  margin-bottom: 0.28em;
}
.reveal h2 {
  color: var(--r-heading-color);
  font-size: 1.54em;
  padding-left: 16px;
  border-left: 5px solid rgba(102, 126, 234, 0.95);
}
.reveal h3 {
  color: #edf3ff;
  font-size: 1.08em;
}
.reveal h4 {
  color: #dfe8ff;
  font-size: 0.86em;
  letter-spacing: 0.01em;
}
.reveal p,
.reveal li {
  color: var(--r-body-color);
  line-height: 1.68;
  font-size: 0.82em;
}
.reveal strong {
  color: var(--r-strong-color);
  font-weight: 700;
}
.reveal a {
  color: var(--accent-info);
  text-decoration-color: rgba(79, 172, 254, 0.42);
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
  font-size: 2.58em;
  white-space: nowrap;
  text-align: center;
  line-height: 1.04;
  margin-bottom: 0.1em;
  animation: slideInUp 0.95s ease-out both, glowPulse 4.8s ease-in-out 1.1s infinite;
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
  width: 104px;
  height: 4px;
  border-radius: 999px;
  background: linear-gradient(90deg, #667eea, #764ba2, #f093fb);
  box-shadow: 0 0 18px rgba(102, 126, 234, 0.35);
  margin: 14px auto 18px;
}
.reveal .panel,
.reveal .glass-card,
.reveal .info-card,
.reveal .compare-col,
.reveal .flow-node,
.reveal .stat-item,
.reveal .img-frame {
  background: var(--glass-bg);
  backdrop-filter: var(--glass-blur);
  -webkit-backdrop-filter: var(--glass-blur);
  border: 1px solid var(--glass-border);
  box-shadow: var(--glass-shadow);
}
.reveal .panel,
.reveal .glass-card {
  border-radius: 22px;
  padding: 22px 24px;
  border-top: 3px solid #667eea;
  background: linear-gradient(180deg, rgba(102, 126, 234, 0.08) 0%, rgba(18, 28, 52, 0.58) 42%, rgba(18, 28, 52, 0.58) 100%);
}
.reveal .tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  border-radius: 999px;
  background: rgba(102, 126, 234, 0.15);
  border: 1px solid rgba(122, 184, 255, 0.18);
  color: #d9e6ff;
  font-size: 0.66em;
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
  border-radius: 20px;
  background: rgba(102, 126, 234, 0.1);
  min-width: 220px;
}
.reveal .stat-number {
  font-size: 2.4em;
  line-height: 1;
  font-weight: 900;
  background: linear-gradient(90deg, #a9bcff 0%, #4facfe 50%, #43e97b 100%);
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
  background: linear-gradient(180deg, rgba(102, 126, 234, 0.9), rgba(79, 172, 254, 0.24));
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
  padding: 8px 18px;
  flex-shrink: 0;
  border-radius: 999px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: #f7f9ff;
  font-size: 0.78em;
  white-space: nowrap;
  font-weight: 700;
  box-shadow: 0 8px 24px rgba(102, 126, 234, 0.35);
  padding: 0 10px;
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
  color: #cfd9ee;
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
  animation: fadeInScale 0.7s ease-out both;
}
.reveal .info-card h3,
.reveal .compare-col h3,
.reveal .panel h3,
.reveal .glass-card h3 {
  margin-top: 0;
  background: linear-gradient(135deg, #667eea, #4facfe);
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
  background: rgba(102, 126, 234, 0.18);
  color: #667eea;
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
  background: rgba(255, 107, 107, 0.12);
  border-color: rgba(255, 107, 107, 0.28);
}
.reveal .compare-good {
  background: rgba(67, 233, 123, 0.12);
  border-color: rgba(67, 233, 123, 0.28);
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
  color: var(--accent-info);
  font-size: 1.1em;
  font-weight: 700;
}
.reveal .code-showcase pre {
  width: 100%;
  margin: 0;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 18px 42px rgba(0, 0, 0, 0.32);
  border: 1px solid rgba(255, 255, 255, 0.08);
}
.reveal .code-showcase pre code {
  max-height: 480px;
  padding: 1.25em 1.35em;
  font-family: var(--r-code-font);
  font-size: 0.7em;
  line-height: 1.58;
  border-radius: 18px;
}
.reveal .img-frame {
  border-radius: 24px;
  padding: 14px;
  overflow: hidden;
  box-shadow: 0 0 0 1px rgba(122, 184, 255, 0.1), 0 16px 34px rgba(79, 172, 254, 0.18);
}
.reveal .img-frame img,
.reveal .img-frame svg,
.reveal img {
  display: block;
  width: 100%;
  border-radius: 18px;
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
  border-left: 5px solid var(--accent-info);
  border-radius: 0 20px 20px 0;
  background: rgba(79, 172, 254, 0.08);
  color: #eef5ff;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
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
  background: linear-gradient(90deg, #f7f9ff 0%, #a9bcff 34%, #f093fb 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.reveal .end-slide p {
  max-width: 760px;
  text-align: center;
}
@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(60px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes glowPulse {
  0%,
  100% {
    text-shadow: 0 0 0 rgba(102, 126, 234, 0), 0 0 0 rgba(240, 147, 251, 0);
  }
  50% {
    text-shadow: 0 0 18px rgba(102, 126, 234, 0.28), 0 0 28px rgba(240, 147, 251, 0.18);
  }
}
@keyframes fadeInScale {
  from {
    opacity: 0;
    transform: scale(0.85);
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
  box-shadow: var(--glass-shadow);
}
.reveal .styled-table thead th {
  background: rgba(102, 126, 234, 0.15);
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
  border-bottom: 1px solid var(--glass-border);
  color: var(--r-body-color);
}
.reveal .styled-table tbody tr {
  background: var(--glass-bg);
  backdrop-filter: var(--glass-blur);
  transition: background 0.2s;
}
.reveal .styled-table tbody tr:nth-child(even) {
  background: rgba(18, 28, 52, 0.72);
}
.reveal .styled-table tbody tr:hover {
  background: rgba(102, 126, 234, 0.15);
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
  color: #667eea;
  background: rgba(255, 255, 255, 0.05);
}
.reveal .progress span {
  background: linear-gradient(90deg, #667eea 0%, #764ba2 55%, #f093fb 100%);
  box-shadow: 0 0 18px rgba(102, 126, 234, 0.32);
}
.reveal .fragment.highlight-current-blue.visible {
  color: var(--accent-info);
  text-shadow: 0 0 16px rgba(79, 172, 254, 0.26);
}
```

## ECharts Palette
```js
const glassmorphismPalette = ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'];

const glassmorphismEChartsTheme = {
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  backgroundColor: 'transparent',
  textStyle: {
    color: '#e6edf7',
    fontFamily: 'Segoe UI, PingFang SC, Microsoft YaHei, system-ui, sans-serif'
  },
  title: {
    textStyle: { color: '#f7f9ff', fontWeight: 700 },
    subtextStyle: { color: '#9fb3d9' }
  },
  legend: {
    textStyle: { color: '#cfd9ee' },
    pageTextStyle: { color: '#cfd9ee' }
  },
  tooltip: {
    backgroundColor: 'rgba(13, 20, 39, 0.9)',
    borderColor: 'rgba(122, 184, 255, 0.14)',
    borderWidth: 1,
    textStyle: { color: '#e6edf7' },
    extraCssText: 'backdrop-filter: blur(10px); box-shadow: 0 18px 44px rgba(0, 0, 0, 0.28);'
  },
  grid: {
    left: 56,
    right: 28,
    top: 54,
    bottom: 48,
    containLabel: true
  },
  categoryAxis: {
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.25)' } },
    axisTick: { lineStyle: { color: 'rgba(255,255,255,0.25)' } },
    axisLabel: { color: '#cfd9ee' },
    splitLine: { show: false },
    nameTextStyle: { color: '#cfd9ee' }
  },
  valueAxis: {
    axisLine: { show: true, lineStyle: { color: 'rgba(255,255,255,0.25)' } },
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    nameTextStyle: { color: '#cfd9ee' }
  },
  timeAxis: {
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.25)' } },
    axisLabel: { color: '#cfd9ee' },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    nameTextStyle: { color: '#cfd9ee' }
  },
  logAxis: {
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.25)' } },
    axisLabel: { color: '#cfd9ee' },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    nameTextStyle: { color: '#cfd9ee' }
  },
  toolbox: {
    iconStyle: {
      borderColor: '#cfd9ee'
    },
    emphasis: {
      iconStyle: {
        borderColor: '#4facfe'
      }
    }
  },
  dataZoom: {
    textStyle: { color: '#cfd9ee' },
    borderColor: 'rgba(255,255,255,0.12)',
    fillerColor: 'rgba(102,126,234,0.18)',
    handleStyle: { color: '#667eea' }
  },
  line: {
    smooth: true,
    symbol: 'circle',
    symbolSize: 8,
    lineStyle: { width: 3 },
    itemStyle: {
      borderWidth: 2,
      borderColor: '#0b1020'
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
      borderColor: '#0b1020'
    },
    label: { color: '#e6edf7' },
    labelLine: { lineStyle: { color: 'rgba(255,255,255,0.25)' } }
  },
  radar: {
    axisName: { color: '#cfd9ee' },
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.18)' } },
    splitLine: { lineStyle: { color: ['rgba(255,255,255,0.08)'] } },
    splitArea: {
      areaStyle: {
        color: ['rgba(102,126,234,0.05)', 'rgba(79,172,254,0.03)']
      }
    }
  }
};
```

## Image Treatment
- Wrap screenshots, UI mockups, and diagrams in `<div class="img-frame">...</div>` to get the rounded glass border, glow shadow, and safe padding.
- The CSS already styles `.img-frame`, `.img-frame img`, `.img-frame svg`, and generic `.reveal img` so copied images inherit rounded corners, a subtle border, and a high-end glass presentation.
- For image-heavy slides, pair `.img-frame` with `.panel` or `.glass-card` to keep bright images grounded against the dark background instead of letting them float directly on the canvas.
- For side-by-side visuals, place two `.img-frame` blocks inside `.two-col`; for terminal or dashboard captures, keep captions muted with `.footer-note` to preserve the premium technical feel.

## Theme Auto-select Keywords
科技玻璃态, glassmorphism, glass theme, frosted glass, cyber glass, 科技感, 高级暗色, 未来感, 架构设计, 技术分享, 代码演示, dashboard, metrics, 深色炫光

# Cyberpunk Theme

Base: `black.min.css` | Highlight: `dracula.min.css` | Best for: Cutting-edge tech, hacker culture, security topics, AI/ML

## CDN Links
- reveal.js core CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css`
- reveal.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/theme/black.min.css`
- highlight.js theme CSS: `https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/dracula.min.css`

## Complete CSS
```css
:root {
  --r-background-color: #0a0a0f;
  --r-main-font: "Cascadia Code", "Fira Code", "JetBrains Mono", Consolas, monospace;
  --r-heading-font: "Cascadia Code", "Fira Code", "JetBrains Mono", Consolas, monospace;
  --r-code-font: "Cascadia Code", "Fira Code", "JetBrains Mono", Consolas, monospace;
  --r-main-color: #e0e0e0;
  --r-heading-color: #00ff88;
  --r-link-color: #00d4ff;
  --r-link-color-hover: #7af7ff;
  --r-selection-background-color: rgba(0, 212, 255, 0.28);
  --r-body-color: #e0e0e0;
  --r-muted-color: #a0a0a0;
  --r-strong-color: #ff0066;
  --cyber-bg: #0a0a0f;
  --cyber-bg-elevated: rgba(8, 15, 18, 0.94);
  --cyber-card-bg: rgba(0, 255, 136, 0.05);
  --cyber-card-border: rgba(0, 255, 136, 0.2);
  --cyber-card-shadow: 0 0 0 1px rgba(0, 255, 136, 0.12), 0 0 24px rgba(0, 255, 136, 0.12), 0 0 48px rgba(0, 212, 255, 0.06);
  --cyber-pink-shadow: 0 0 20px rgba(255, 0, 102, 0.22);
  --accent-primary: #00ff88;
  --accent-secondary: #ff0066;
  --accent-tertiary: #00d4ff;
  --accent-warning: #ffaa00;
  --accent-purple: #a855f7;
  --accent-gradient: linear-gradient(90deg, #00ff88 0%, #00d4ff 55%, #ff0066 100%);
  --accent-gradient-soft: linear-gradient(135deg, rgba(0, 255, 136, 0.15) 0%, rgba(0, 212, 255, 0.1) 55%, rgba(255, 0, 102, 0.14) 100%);
}
.reveal {
  position: relative;
  background:
    radial-gradient(circle at 18% 18%, rgba(0, 255, 136, 0.08) 0%, transparent 28%),
    radial-gradient(circle at 82% 16%, rgba(0, 212, 255, 0.08) 0%, transparent 24%),
    radial-gradient(circle at 50% 88%, rgba(255, 0, 102, 0.06) 0%, transparent 26%),
    linear-gradient(135deg, #07070b 0%, #0a0a0f 48%, #05060a 100%);
  color: var(--r-main-color);
  font-family: var(--r-main-font);
}
.reveal::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, rgba(0, 255, 136, 0.03), transparent 28%, transparent 72%, rgba(0, 212, 255, 0.03));
  pointer-events: none;
}
.reveal::after {
  content: "";
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(180deg, rgba(255, 255, 255, 0.02) 0px, rgba(255, 255, 255, 0.02) 1px, transparent 1px, transparent 4px);
  opacity: 0.18;
  mix-blend-mode: screen;
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
  text-transform: uppercase;
}
.reveal h1 {
  color: var(--accent-primary);
  font-size: 2.48em;
  font-weight: 900;
  line-height: 1.02;
  letter-spacing: 0.08em;
  margin-bottom: 0.28em;
  text-shadow: 0 0 10px rgba(0, 255, 136, 0.55), 0 0 24px rgba(0, 255, 136, 0.28), 0 0 38px rgba(0, 212, 255, 0.16);
}
.reveal h2 {
  color: var(--accent-tertiary);
  font-size: 1.52em;
  padding-left: 16px;
  border-left: 4px solid rgba(0, 212, 255, 0.9);
  text-shadow: 0 0 14px rgba(0, 212, 255, 0.2);
}
.reveal h3 {
  color: #8affc8;
  font-size: 1.06em;
  letter-spacing: 0.05em;
}
.reveal h4 {
  color: #7af7ff;
  font-size: 0.84em;
  letter-spacing: 0.06em;
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
  text-shadow: 0 0 12px rgba(255, 0, 102, 0.26);
}
.reveal a {
  color: var(--accent-tertiary);
  text-decoration-color: rgba(0, 212, 255, 0.5);
  text-shadow: 0 0 8px rgba(0, 212, 255, 0.2);
  transition: color 0.2s ease, text-shadow 0.2s ease;
}
.reveal a:hover {
  color: var(--r-link-color-hover);
  text-shadow: 0 0 16px rgba(122, 247, 255, 0.35);
}
.reveal blockquote {
  width: 100%;
  margin: 1.1em 0 0;
  padding: 18px 22px;
  border-left: 4px solid var(--accent-secondary);
  border-radius: 0 12px 12px 0;
  background: rgba(255, 0, 102, 0.08);
  color: #ffd8e8;
  box-shadow: inset 0 0 0 1px rgba(255, 0, 102, 0.16), var(--cyber-pink-shadow);
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
  font-size: 2.52em;
  line-height: 1.04;
  margin-bottom: 0.1em;
  animation: slideInUp 0.95s ease-out both, glowPulse 4.6s ease-in-out 1.1s infinite;
}
.reveal .subtitle,
.reveal .meta {
  color: var(--r-muted-color);
  font-size: 0.74em;
}
.reveal .subtitle {
  font-size: 0.96em;
  max-width: 920px;
  text-shadow: 0 0 8px rgba(0, 255, 136, 0.08);
}
.reveal .meta {
  font-size: 0.74em;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
.reveal .accent-line {
  width: 112px;
  height: 3px;
  background: var(--accent-gradient);
  box-shadow: 0 0 16px rgba(0, 255, 136, 0.42), 0 0 24px rgba(0, 212, 255, 0.18);
  margin: 14px auto 18px;
}
.reveal .footer-note {
  margin-top: auto;
  padding-top: 16px;
  color: var(--r-muted-color);
  font-size: 0.7em;
  font-style: italic;
  opacity: 0.95;
}
.reveal .panel,
.reveal .glass-card,
.reveal .info-card,
.reveal .compare-col,
.reveal .flow-node,
.reveal .stat-item,
.reveal .img-frame {
  background: var(--cyber-card-bg);
  border: 1px solid var(--cyber-card-border);
  box-shadow: var(--cyber-card-shadow);
}
.reveal .panel,
.reveal .glass-card {
  border-radius: 10px;
  padding: 22px 24px;
  border-top: 3px solid #ff2a6d;
  background: linear-gradient(180deg, rgba(255, 42, 109, 0.06) 0%, rgba(8, 15, 18, 0.94) 42%, rgba(8, 15, 18, 0.94) 100%);
}
.reveal .tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  border-radius: 999px;
  background: rgba(0, 212, 255, 0.08);
  border: 1px solid rgba(0, 212, 255, 0.34);
  color: #9ff6ff;
  font-size: 0.66em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  box-shadow: 0 0 12px rgba(0, 212, 255, 0.12);
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
  border-radius: 10px;
  background: rgba(0, 255, 136, 0.06);
  min-width: 220px;
}
.reveal .stat-number {
  font-size: 2.4em;
  line-height: 1;
  font-weight: 900;
  color: var(--accent-primary);
  text-shadow: 0 0 14px rgba(0, 255, 136, 0.32), 0 0 24px rgba(0, 212, 255, 0.14);
  margin-bottom: 10px;
}
.reveal .stat-label {
  color: var(--r-muted-color);
  font-size: 0.74em;
  letter-spacing: 0.08em;
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
  background: linear-gradient(180deg, rgba(0, 255, 136, 0.9), rgba(0, 212, 255, 0.3), rgba(255, 0, 102, 0.24));
  box-shadow: 0 0 12px rgba(0, 255, 136, 0.22);
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
  background: #091318;
  border: 1px solid rgba(0, 255, 136, 0.45);
  color: #00ff88;
  font-size: 0.78em;
  font-weight: 700;
  box-shadow: 0 0 16px rgba(0, 255, 136, 0.2), inset 0 0 12px rgba(0, 212, 255, 0.08);
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
  color: #c8d2d2;
}
.reveal .card-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px;
  margin-top: 16px;
}
.reveal .info-card {
  border-radius: 10px;
  padding: 22px 22px 20px;
  animation: fadeInScale 0.7s ease-out both;
}
.reveal .info-card h3,
.reveal .compare-col h3,
.reveal .panel h3,
.reveal .glass-card h3 {
  margin-top: 0;
  background: linear-gradient(135deg, #ff2a6d, #d300c5);
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
  background: rgba(0, 255, 255, 0.12);
  color: #00ffff;
}
.reveal .compare-table {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
  gap: 24px;
  margin-top: 16px;
}
.reveal .compare-col {
  border-radius: 10px;
  padding: 22px 24px;
}
.reveal .compare-bad {
  background: rgba(255, 0, 102, 0.08);
  border-color: rgba(255, 0, 102, 0.32);
}
.reveal .compare-good {
  background: rgba(0, 255, 136, 0.08);
  border-color: rgba(0, 255, 136, 0.32);
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
  border-radius: 10px;
  min-width: 150px;
  text-align: center;
}
.reveal .flow-arrow {
  color: var(--accent-tertiary);
  font-size: 1.1em;
  font-weight: 700;
  text-shadow: 0 0 12px rgba(0, 212, 255, 0.28);
}
.reveal .code-showcase pre,
.reveal pre {
  width: 100%;
  margin: 0;
  border-radius: 12px;
  overflow: hidden;
  background: rgba(3, 8, 10, 0.96);
  border: 1px solid rgba(0, 255, 136, 0.24);
  box-shadow: 0 0 0 1px rgba(0, 255, 136, 0.08), 0 0 22px rgba(0, 255, 136, 0.1);
}
.reveal .code-showcase pre code,
.reveal pre code {
  max-height: 480px;
  padding: 1.25em 1.35em;
  font-family: var(--r-code-font);
  font-size: 0.7em;
  line-height: 1.58;
  border-radius: 12px;
  color: #d5ffe9;
  background: transparent;
}
.reveal .img-frame {
  border-radius: 12px;
  padding: 12px;
  overflow: hidden;
  background: rgba(0, 255, 136, 0.04);
  box-shadow: 0 0 0 1px rgba(0, 255, 136, 0.12), 0 0 26px rgba(0, 212, 255, 0.08);
}
.reveal .img-frame img,
.reveal .img-frame svg,
.reveal img {
  display: block;
  width: 100%;
  border-radius: 8px;
  border: 1px solid rgba(0, 212, 255, 0.16);
  filter: saturate(1.02) contrast(1.05);
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
  border-left: 4px solid var(--accent-secondary);
  border-radius: 0 12px 12px 0;
  background: rgba(255, 0, 102, 0.08);
  color: #ffd8e8;
  box-shadow: inset 0 0 0 1px rgba(255, 0, 102, 0.16), var(--cyber-pink-shadow);
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
  font-size: 2.3em;
  color: var(--accent-primary);
  text-shadow: 0 0 16px rgba(0, 255, 136, 0.35), 0 0 30px rgba(0, 212, 255, 0.16);
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
    text-shadow: 0 0 10px rgba(0, 255, 136, 0.48), 0 0 20px rgba(0, 212, 255, 0.12);
  }
  50% {
    text-shadow: 0 0 14px rgba(0, 255, 136, 0.7), 0 0 30px rgba(0, 212, 255, 0.3), 0 0 42px rgba(255, 0, 102, 0.16);
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
  box-shadow: var(--cyber-card-shadow);
}
.reveal .styled-table thead th {
  background: rgba(255, 42, 109, 0.15);
  color: #ffd8e8;
  font-weight: 700;
  padding: 14px 20px;
  text-align: left;
  font-size: 0.9em;
  letter-spacing: 0.02em;
  border-bottom: 2px solid #ff2a6d;
}
.reveal .styled-table tbody td {
  padding: 12px 20px;
  border-bottom: 1px solid var(--cyber-card-border);
  color: var(--r-body-color);
}
.reveal .styled-table tbody tr {
  background: rgba(8, 15, 18, 0.94);
  transition: background 0.2s;
}
.reveal .styled-table tbody tr:nth-child(even) {
  background: rgba(10, 10, 30, 0.72);
}
.reveal .styled-table tbody tr:hover {
  background: rgba(255, 42, 109, 0.15);
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
  color: #00ff88;
  background: rgba(255, 255, 255, 0.04);
}
.reveal .progress span {
  background: linear-gradient(90deg, #00ff88 0%, #00d4ff 50%, #ff0066 100%);
  box-shadow: 0 0 16px rgba(0, 255, 136, 0.3), 0 0 24px rgba(0, 212, 255, 0.16);
}
.reveal .fragment.highlight-current-blue.visible {
  color: var(--accent-tertiary);
  text-shadow: 0 0 16px rgba(0, 212, 255, 0.34);
}
```

## ECharts Palette
```js
const cyberpunkPalette = ['#00ff88', '#ff0066', '#00d4ff', '#ffaa00', '#a855f7'];

const cyberpunkEChartsTheme = {
  color: ['#00ff88', '#ff0066', '#00d4ff', '#ffaa00', '#a855f7'],
  backgroundColor: 'transparent',
  textStyle: {
    color: '#e0e0e0',
    fontFamily: 'Cascadia Code, Fira Code, JetBrains Mono, Consolas, monospace'
  },
  title: {
    textStyle: { color: '#00ff88', fontWeight: 700 },
    subtextStyle: { color: '#a0a0a0' }
  },
  legend: {
    textStyle: { color: '#cfd7d7' },
    pageTextStyle: { color: '#cfd7d7' }
  },
  tooltip: {
    backgroundColor: 'rgba(7, 10, 14, 0.95)',
    borderColor: 'rgba(0, 255, 136, 0.42)',
    borderWidth: 1,
    textStyle: { color: '#e0e0e0' },
    extraCssText: 'box-shadow: 0 0 0 1px rgba(0,255,136,0.16), 0 0 20px rgba(0,255,136,0.12);'
  },
  grid: {
    left: 56,
    right: 28,
    top: 54,
    bottom: 48,
    containLabel: true
  },
  categoryAxis: {
    axisLine: { lineStyle: { color: 'rgba(0,255,136,0.35)' } },
    axisTick: { lineStyle: { color: 'rgba(0,255,136,0.28)' } },
    axisLabel: { color: '#cfd7d7' },
    splitLine: { show: false },
    nameTextStyle: { color: '#a0a0a0' }
  },
  valueAxis: {
    axisLine: { show: true, lineStyle: { color: 'rgba(0,255,136,0.35)' } },
    axisTick: { show: false },
    axisLabel: { color: '#cfd7d7' },
    splitLine: { lineStyle: { color: 'rgba(0,212,255,0.12)' } },
    nameTextStyle: { color: '#a0a0a0' }
  },
  timeAxis: {
    axisLine: { lineStyle: { color: 'rgba(0,255,136,0.35)' } },
    axisLabel: { color: '#cfd7d7' },
    splitLine: { lineStyle: { color: 'rgba(0,212,255,0.12)' } },
    nameTextStyle: { color: '#a0a0a0' }
  },
  logAxis: {
    axisLine: { lineStyle: { color: 'rgba(0,255,136,0.35)' } },
    axisLabel: { color: '#cfd7d7' },
    splitLine: { lineStyle: { color: 'rgba(0,212,255,0.12)' } },
    nameTextStyle: { color: '#a0a0a0' }
  },
  toolbox: {
    iconStyle: {
      borderColor: '#cfd7d7'
    },
    emphasis: {
      iconStyle: {
        borderColor: '#00d4ff'
      }
    }
  },
  dataZoom: {
    textStyle: { color: '#cfd7d7' },
    borderColor: 'rgba(0,255,136,0.16)',
    fillerColor: 'rgba(0,255,136,0.16)',
    handleStyle: { color: '#00ff88' }
  },
  line: {
    smooth: true,
    symbol: 'circle',
    symbolSize: 8,
    lineStyle: { width: 3 },
    itemStyle: {
      borderWidth: 2,
      borderColor: '#0a0a0f'
    }
  },
  bar: {
    itemStyle: {
      borderRadius: [6, 6, 0, 0]
    }
  },
  pie: {
    itemStyle: {
      borderWidth: 2,
      borderColor: '#0a0a0f'
    },
    label: { color: '#e0e0e0' },
    labelLine: { lineStyle: { color: 'rgba(0,255,136,0.24)' } }
  },
  radar: {
    axisName: { color: '#cfd7d7' },
    axisLine: { lineStyle: { color: 'rgba(0,255,136,0.2)' } },
    splitLine: { lineStyle: { color: ['rgba(0,212,255,0.12)'] } },
    splitArea: {
      areaStyle: {
        color: ['rgba(0,255,136,0.04)', 'rgba(255,0,102,0.03)']
      }
    }
  }
};
```

## Image Treatment
- Wrap screenshots, terminal captures, system diagrams, and dashboards in `<div class="img-frame">...</div>` to add the neon border, dark chassis, and subtle cyan-green glow.
- The CSS already styles `.img-frame`, `.img-frame img`, `.img-frame svg`, and generic `.reveal img` so copied visuals inherit a crisp terminal-panel treatment instead of soft glass.
- Pair image-heavy slides with `.panel` or `.glass-card` to keep screenshots grounded inside cyberpunk HUD-style containers, especially on security or architecture decks.
- For side-by-side visuals, place two `.img-frame` blocks inside `.two-col`; for console screenshots, add a muted `.footer-note` caption to reinforce the operator-console feel.

## Theme Auto-select Keywords
cyberpunk, neon hacker, matrix style, terminal style, hacker aesthetic, security topics, cyan-green neon, AI security, red-blue team, SOC, threat intel, zero trust, machine learning ops, futuristic dark

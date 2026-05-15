# Radar Chart / 雷达图

Best for: capability comparisons, scorecards, maturity assessments, and showing strengths or gaps across a fixed set of dimensions

## Base Option

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt to theme surface
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  legend: {
    bottom: '2%',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  radar: {
    center: ['50%', '44%'],
    radius: '62%',
    shape: 'circle',
    indicator: [
      { name: 'Strategy', max: 100 },
      { name: 'Execution', max: 100 },
      { name: 'Quality', max: 100 },
      { name: 'Speed', max: 100 },
      { name: 'Adoption', max: 100 },
      { name: 'Impact', max: 100 }
    ], // REPLACE: indicators and max values
    axisName: {
      color: '#e6edf7' // THEME: adapt
    },
    splitLine: {
      lineStyle: { color: 'rgba(255,255,255,0.18)' } // THEME: adapt
    },
    splitArea: {
      areaStyle: {
        color: ['rgba(255,255,255,0.03)', 'rgba(255,255,255,0.01)'] // THEME: adapt
      }
    },
    axisLine: {
      lineStyle: { color: 'rgba(255,255,255,0.18)' } // THEME: adapt
    }
  },
  series: [
    {
      name: 'Current State', // REPLACE
      type: 'radar',
      symbol: 'circle',
      symbolSize: 8,
      data: [
        {
          value: [84, 72, 88, 76, 69, 81], // REPLACE
          name: 'Current State', // REPLACE
          areaStyle: {
            color: 'rgba(102,126,234,0.26)' // THEME_COLORS[0] with opacity
          }
        }
      ],
      lineStyle: { width: 3 },
      itemStyle: { borderColor: '#ffffff', borderWidth: 1 }, // THEME: adapt
      emphasis: { focus: 'series' }
    }
  ]
}
```

## Variants

### Variant 1: Multi-series radar comparison

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  legend: {
    bottom: '2%',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  radar: {
    center: ['50%', '42%'],
    radius: '60%',
    shape: 'polygon',
    indicator: [
      { name: 'UX', max: 10 },
      { name: 'Reliability', max: 10 },
      { name: 'Performance', max: 10 },
      { name: 'Security', max: 10 },
      { name: 'Scalability', max: 10 }
    ], // REPLACE
    axisName: { color: '#e6edf7' }, // THEME: adapt
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.18)' } },
    splitArea: {
      areaStyle: {
        color: ['rgba(255,255,255,0.03)', 'rgba(255,255,255,0.01)'] // THEME: adapt
      }
    },
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.18)' } }
  },
  series: [
    {
      type: 'radar',
      symbol: 'circle',
      symbolSize: 7,
      lineStyle: { width: 3 },
      data: [
        {
          value: [8, 7, 9, 8, 6], // REPLACE
          name: 'Product A', // REPLACE
          areaStyle: { color: 'rgba(102,126,234,0.18)' } // THEME_COLORS[0] with opacity
        },
        {
          value: [6, 8, 7, 9, 8], // REPLACE
          name: 'Product B', // REPLACE
          areaStyle: { color: 'rgba(118,75,162,0.16)' } // THEME_COLORS[1] with opacity
        }
      ],
      emphasis: { focus: 'series' }
    }
  ]
}
```

### Variant 2: Simple outline radar

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  radar: {
    center: ['50%', '44%'],
    radius: '64%',
    shape: 'polygon',
    indicator: [
      { name: 'Discover', max: 5 },
      { name: 'Build', max: 5 },
      { name: 'Ship', max: 5 },
      { name: 'Measure', max: 5 },
      { name: 'Learn', max: 5 }
    ], // REPLACE
    axisName: { color: '#e6edf7' }, // THEME: adapt
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.18)' } },
    splitArea: { areaStyle: { color: ['transparent'] } },
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.18)' } }
  },
  series: [
    {
      name: 'Process Score', // REPLACE
      type: 'radar',
      symbol: 'circle',
      symbolSize: 8,
      lineStyle: { width: 4 },
      itemStyle: { borderColor: '#ffffff', borderWidth: 1 }, // THEME: adapt
      areaStyle: { opacity: 0 },
      data: [
        {
          value: [4, 5, 3, 4, 4], // REPLACE
          name: 'Process Score' // REPLACE
        }
      ],
      emphasis: { focus: 'series' }
    }
  ]
}
```

## Data Replacement Guide

- Replace the `indicator` array with real dimensions and sensible `max` values.
- Replace every radar `value` array so it aligns exactly with the indicator order.
- Use single-series radar for one profile; use multi-series only for direct comparisons with the same scale.
- Keep the number of axes between 5 and 7 so labels remain readable on a slide.
- If you need percentages, set all indicator `max` values to 100 for consistency.

## Theme Integration

- Replace the `color` array with the theme's **ECharts Palette**.
- Adapt tooltip, legend, axis names, split lines, and split areas to the theme's neutral colors.
- Filled radar variants should use semi-transparent palette colors; outline variants should rely on stronger line contrast.
- Use a container such as `<div id="radarChart" style="width:100%;height:min(420px,55vh);max-height:420px;"></div>`.

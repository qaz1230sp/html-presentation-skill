# Line Chart / 折线图

Best for: trends over time, cumulative growth, progress tracking, and highlighting acceleration or seasonality

## Base Option

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt to theme surface
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  grid: {
    left: '8%',
    right: '5%',
    top: '14%',
    bottom: '14%',
    containLabel: true
  },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } }, // THEME: adapt
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } }, // THEME: adapt
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Active Users', // REPLACE
      type: 'line',
      smooth: true,
      symbol: 'circle',
      symbolSize: 10,
      data: [120, 132, 141, 156, 178, 190, 204], // REPLACE
      lineStyle: { width: 4 },
      itemStyle: { borderWidth: 2, borderColor: '#ffffff' }, // THEME: adapt marker border
      areaStyle: {
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
          { offset: 0, color: 'rgba(102,126,234,0.38)' }, // THEME_COLORS[0] with opacity
          { offset: 1, color: 'rgba(102,126,234,0.04)' }
        ])
      },
      emphasis: { focus: 'series' }
    }
  ]
}
```

## Variants

### Variant 1: Multi-line comparison

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  legend: {
    top: '4%',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  grid: {
    left: '8%',
    right: '5%',
    top: '18%',
    bottom: '12%',
    containLabel: true
  },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Current Year', // REPLACE
      type: 'line',
      smooth: true,
      symbolSize: 9,
      data: [82, 95, 121, 136, 154, 170], // REPLACE
      lineStyle: { width: 3 },
      emphasis: { focus: 'series' }
    },
    {
      name: 'Previous Year', // REPLACE
      type: 'line',
      smooth: true,
      symbolSize: 9,
      data: [74, 88, 103, 114, 128, 142], // REPLACE
      lineStyle: { width: 3, type: 'dashed' },
      emphasis: { focus: 'series' }
    },
    {
      name: 'Target', // REPLACE OR REMOVE
      type: 'line',
      smooth: true,
      symbolSize: 7,
      data: [80, 92, 110, 128, 145, 160], // REPLACE
      lineStyle: { width: 2, opacity: 0.8 },
      emphasis: { focus: 'series' }
    }
  ]
}
```

### Variant 2: Step line

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  grid: {
    left: '8%',
    right: '5%',
    top: '14%',
    bottom: '14%',
    containLabel: true
  },
  xAxis: {
    type: 'category',
    boundaryGap: true,
    data: ['Phase 1', 'Phase 2', 'Phase 3', 'Phase 4'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Coverage', // REPLACE
      type: 'line',
      step: 'end',
      smooth: false,
      symbolSize: 10,
      data: [25, 52, 71, 95], // REPLACE
      lineStyle: { width: 4 },
      areaStyle: {
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
          { offset: 0, color: 'rgba(79,172,254,0.30)' }, // THEME_COLORS[3] with opacity
          { offset: 1, color: 'rgba(79,172,254,0.02)' }
        ])
      },
      emphasis: { focus: 'series' }
    }
  ]
}
```

### Variant 3: Opaque area chart

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  grid: {
    left: '8%',
    right: '5%',
    top: '14%',
    bottom: '14%',
    containLabel: true
  },
  xAxis: {
    type: 'category',
    boundaryGap: false,
    data: ['Week 1', 'Week 2', 'Week 3', 'Week 4'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Bookings', // REPLACE
      type: 'line',
      smooth: true,
      symbolSize: 8,
      data: [40, 68, 92, 120], // REPLACE
      lineStyle: { width: 3 },
      areaStyle: {
        opacity: 0.78,
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
          { offset: 0, color: 'rgba(67,233,123,0.88)' }, // THEME_COLORS[4] with opacity
          { offset: 1, color: 'rgba(67,233,123,0.24)' }
        ])
      },
      emphasis: { focus: 'series' }
    }
  ]
}
```

## Data Replacement Guide

- Replace `xAxis.data` with ordered time labels, stages, or milestones.
- Replace each `series[n].data` with numeric values aligned to the same index positions.
- Keep `smooth: true` for narrative trend slides; switch to `smooth: false` only when exact step changes matter.
- For multi-line charts, keep series count to 2-3 for slide readability.
- Adjust `yAxis.axisLabel.formatter` when values represent currency, percentages, or units.

## Theme Integration

- Replace the `color` array with the theme's **ECharts Palette** and update the area gradient stops to matching palette hues.
- Tooltip, axis, and legend neutrals should come from the active theme's text and border colors.
- Use high-contrast marker borders on dark themes and softer neutral borders on light themes.
- Use a chart container such as `<div id="lineChart" style="width:100%;height:min(420px,55vh);max-height:420px;"></div>`.

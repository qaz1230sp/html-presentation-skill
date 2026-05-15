# Bar Chart / 柱状图

Best for: rankings, comparisons across categories, KPI snapshots, and before/after performance summaries

## Base Option

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    axisPointer: { type: 'shadow' },
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt to theme surface
    borderColor: 'rgba(255,255,255,0.12)', // THEME: adapt to theme border
    textStyle: { color: '#e6edf7' } // THEME: adapt to theme text
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
    data: ['Q1', 'Q2', 'Q3', 'Q4'], // REPLACE: category labels
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } }, // THEME: adapt
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } }, // THEME: adapt
    axisLine: { show: false },
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Revenue', // REPLACE: series name
      type: 'bar',
      data: [120, 168, 152, 210], // REPLACE: values
      barWidth: '46%',
      label: {
        show: true,
        position: 'top',
        color: '#e6edf7' // THEME: adapt
      },
      itemStyle: {
        borderRadius: [10, 10, 0, 0],
        color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
          { offset: 0, color: '#667eea' }, // THEME_COLORS[0]
          { offset: 1, color: '#4facfe' } // THEME_COLORS[3]
        ])
      },
      emphasis: {
        focus: 'series'
      }
    }
  ]
}
```

## Variants

### Variant 1: Horizontal bar

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    axisPointer: { type: 'shadow' },
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt to theme surface
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' } // THEME: adapt
  },
  grid: {
    left: '16%',
    right: '7%',
    top: '12%',
    bottom: '10%',
    containLabel: true
  },
  xAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'category',
    data: ['North', 'South', 'West', 'East', 'Central'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Pipeline', // REPLACE
      type: 'bar',
      data: [88, 132, 101, 156, 119], // REPLACE
      barWidth: '48%',
      label: {
        show: true,
        position: 'right',
        color: '#e6edf7' // THEME: adapt
      },
      itemStyle: {
        borderRadius: [0, 10, 10, 0],
        color: new echarts.graphic.LinearGradient(1, 0, 0, 0, [
          { offset: 0, color: '#43e97b' }, // THEME_COLORS[4]
          { offset: 1, color: '#4facfe' } // THEME_COLORS[3]
        ])
      },
      emphasis: { focus: 'series' }
    }
  ]
}
```

### Variant 2: Grouped bar

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    axisPointer: { type: 'shadow' },
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
    data: ['Jan', 'Feb', 'Mar', 'Apr'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Plan', // REPLACE
      type: 'bar',
      data: [90, 110, 126, 144], // REPLACE
      barWidth: '22%',
      label: { show: true, position: 'top', color: '#e6edf7' }, // THEME: adapt
      itemStyle: { borderRadius: [8, 8, 0, 0] }
    },
    {
      name: 'Actual', // REPLACE
      type: 'bar',
      data: [96, 124, 118, 160], // REPLACE
      barWidth: '22%',
      label: { show: true, position: 'top', color: '#e6edf7' }, // THEME: adapt
      itemStyle: { borderRadius: [8, 8, 0, 0] }
    },
    {
      name: 'Forecast', // REPLACE OR REMOVE
      type: 'bar',
      data: [100, 128, 136, 170], // REPLACE
      barWidth: '22%',
      label: { show: false },
      itemStyle: { borderRadius: [8, 8, 0, 0] }
    }
  ]
}
```

### Variant 3: Stacked bar

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'axis',
    axisPointer: { type: 'shadow' },
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
    data: ['Product A', 'Product B', 'Product C'], // REPLACE
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    axisTick: { show: false },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Design', // REPLACE
      type: 'bar',
      stack: 'total',
      data: [24, 30, 18], // REPLACE
      barWidth: '42%',
      label: { show: true, color: '#e6edf7' }, // THEME: adapt
      itemStyle: { borderRadius: [8, 8, 0, 0] }
    },
    {
      name: 'Build', // REPLACE
      type: 'bar',
      stack: 'total',
      data: [42, 36, 45], // REPLACE
      label: { show: true, color: '#e6edf7' }, // THEME: adapt
      itemStyle: { borderRadius: 0 }
    },
    {
      name: 'Launch', // REPLACE
      type: 'bar',
      stack: 'total',
      data: [18, 22, 16], // REPLACE
      label: { show: true, color: '#0d1427' }, // THEME: adapt for lightest palette color
      itemStyle: { borderRadius: [8, 8, 0, 0] }
    }
  ]
}
```

## Data Replacement Guide

- Replace `xAxis.data` or `yAxis.data` with real category labels.
- Replace every `series[n].name` and `series[n].data` array with real metrics.
- Keep `barWidth`, `borderRadius`, `grid`, and `tooltip` unless the slide layout is unusually dense.
- For grouped/stacked bars, remove unused series rather than leaving placeholder legends.
- If values are percentages, add a `yAxis.axisLabel.formatter` such as `'{value}%'`.

## Theme Integration

- Replace the `color` array with the active theme's **ECharts Palette**.
- Mirror theme neutrals into tooltip background/border, axis lines, split lines, and labels.
- For dark themes, keep label contrast high; for light themes, switch label text to a darker neutral.
- Use a chart container such as `<div id="barChart" style="width:100%;height:min(420px,55vh);max-height:420px;"></div>`.

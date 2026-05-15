# Gauge Chart

Best for: single KPI progress, target attainment, readiness scores, SLA status, and compact executive health indicators

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
  series: [
    {
      name: 'Readiness', // REPLACE
      type: 'gauge',
      center: ['50%', '54%'],
      radius: '84%',
      min: 0,
      max: 100,
      startAngle: 225,
      endAngle: -45,
      progress: {
        show: true,
        roundCap: true,
        width: 16
      },
      pointer: {
        show: true,
        length: '62%',
        width: 6
      },
      axisLine: {
        lineStyle: {
          width: 16,
          color: [
            [1, 'rgba(255,255,255,0.12)'] // THEME: adapt track color
          ]
        }
      },
      axisTick: { show: false },
      splitLine: { show: false },
      axisLabel: {
        color: '#cfd9ee', // THEME: adapt
        distance: 18
      },
      anchor: {
        show: true,
        showAbove: true,
        size: 12,
        itemStyle: {
          color: '#e6edf7' // THEME: adapt
        }
      },
      title: {
        offsetCenter: [0, '68%'],
        color: '#cfd9ee', // THEME: adapt
        fontSize: 16
      },
      detail: {
        valueAnimation: true,
        formatter: '{value}%',
        color: '#e6edf7', // THEME: adapt
        fontSize: 34,
        fontWeight: 700,
        offsetCenter: [0, '24%']
      },
      data: [
        { value: 78, name: 'Readiness' }
      ] // REPLACE
    }
  ]
}
```

## Variants

### Variant 1: Multi-gauge dashboard

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
  series: [
    {
      name: 'Quality', // REPLACE
      type: 'gauge',
      center: ['20%', '55%'],
      radius: '48%',
      min: 0,
      max: 100,
      startAngle: 220,
      endAngle: -40,
      progress: { show: true, roundCap: true, width: 12 },
      axisLine: { lineStyle: { width: 12, color: [[1, 'rgba(255,255,255,0.12)']] } },
      axisTick: { show: false },
      splitLine: { show: false },
      axisLabel: { show: false },
      pointer: { length: '56%', width: 5 },
      title: { offsetCenter: [0, '70%'], color: '#cfd9ee', fontSize: 13 }, // THEME: adapt
      detail: { formatter: '{value}%', color: '#e6edf7', fontSize: 24, offsetCenter: [0, '20%'] }, // THEME: adapt
      data: [{ value: 92, name: 'Quality' }] // REPLACE
    },
    {
      name: 'Speed', // REPLACE
      type: 'gauge',
      center: ['50%', '55%'],
      radius: '48%',
      min: 0,
      max: 100,
      startAngle: 220,
      endAngle: -40,
      progress: { show: true, roundCap: true, width: 12 },
      axisLine: { lineStyle: { width: 12, color: [[1, 'rgba(255,255,255,0.12)']] } },
      axisTick: { show: false },
      splitLine: { show: false },
      axisLabel: { show: false },
      pointer: { length: '56%', width: 5 },
      title: { offsetCenter: [0, '70%'], color: '#cfd9ee', fontSize: 13 }, // THEME: adapt
      detail: { formatter: '{value}%', color: '#e6edf7', fontSize: 24, offsetCenter: [0, '20%'] }, // THEME: adapt
      data: [{ value: 81, name: 'Speed' }] // REPLACE
    },
    {
      name: 'Risk', // REPLACE
      type: 'gauge',
      center: ['80%', '55%'],
      radius: '48%',
      min: 0,
      max: 100,
      startAngle: 220,
      endAngle: -40,
      progress: { show: true, roundCap: true, width: 12 },
      axisLine: { lineStyle: { width: 12, color: [[1, 'rgba(255,255,255,0.12)']] } },
      axisTick: { show: false },
      splitLine: { show: false },
      axisLabel: { show: false },
      pointer: { length: '56%', width: 5 },
      title: { offsetCenter: [0, '70%'], color: '#cfd9ee', fontSize: 13 }, // THEME: adapt
      detail: { formatter: '{value}%', color: '#e6edf7', fontSize: 24, offsetCenter: [0, '20%'] }, // THEME: adapt
      data: [{ value: 64, name: 'Risk' }] // REPLACE
    }
  ]
}
```

### Variant 2: Half gauge

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
  series: [
    {
      name: 'SLA', // REPLACE
      type: 'gauge',
      center: ['50%', '66%'],
      radius: '96%',
      min: 0,
      max: 100,
      startAngle: 180,
      endAngle: 0,
      progress: {
        show: true,
        roundCap: true,
        width: 18
      },
      pointer: {
        icon: 'path://M6 0 L-6 0 L0 -75 Z',
        length: '70%',
        width: 12,
        offsetCenter: [0, '-2%']
      },
      axisLine: {
        lineStyle: {
          width: 18,
          color: [[1, 'rgba(255,255,255,0.12)']] // THEME: adapt track color
        }
      },
      axisTick: { distance: -24, splitNumber: 5, lineStyle: { color: '#cfd9ee', width: 1 } }, // THEME: adapt
      splitLine: { distance: -30, length: 12, lineStyle: { color: '#cfd9ee', width: 2 } }, // THEME: adapt
      axisLabel: {
        distance: -42,
        color: '#cfd9ee' // THEME: adapt
      },
      title: {
        offsetCenter: [0, '36%'],
        color: '#cfd9ee', // THEME: adapt
        fontSize: 16
      },
      detail: {
        formatter: '{value}%',
        color: '#e6edf7', // THEME: adapt
        fontSize: 32,
        fontWeight: 700,
        offsetCenter: [0, '8%']
      },
      data: [{ value: 94, name: 'SLA' }] // REPLACE
    }
  ]
}
```

## Data Replacement Guide

- Replace `data[0].value` and `data[0].name` with the KPI being shown.
- Adjust `min`, `max`, and `detail.formatter` when the metric is not a percentage.
- For multi-gauge dashboards, keep values on the same scale so viewers can compare instantly.
- Use the half gauge when you need more room below the arc for explanatory text.
- Keep the number of gauges to 2-3 on one slide; more becomes too small.

## Theme Integration

- Replace the `color` array with the active theme's **ECharts Palette**.
- Use the first palette color for the primary gauge unless another semantic mapping is needed.
- Adapt track, tick, label, title, and tooltip neutrals to the theme background.
- Use a container such as `<div id="gaugeChart" style="width:100%;height:min(420px,50vh);max-height:420px;"></div>`.

# Scatter Chart

Best for: correlation, clustering, distribution, outlier spotting, and comparing two quantitative dimensions at once

## Base Option

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt to theme surface
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' }, // THEME: adapt
    formatter: function (params) {
      return params.data[3] + '<br/>X: ' + params.data[0] + '<br/>Y: ' + params.data[1] + '<br/>Size: ' + params.data[2];
    }
  },
  grid: {
    left: '10%',
    right: '8%',
    top: '14%',
    bottom: '14%',
    containLabel: true
  },
  xAxis: {
    type: 'value',
    name: 'Reach', // REPLACE
    nameLocation: 'middle',
    nameGap: 32,
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } }, // THEME: adapt
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } }, // THEME: adapt
    axisLabel: { color: '#cfd9ee' }, // THEME: adapt
    nameTextStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    name: 'Conversion', // REPLACE
    nameGap: 38,
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } }, // THEME: adapt
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } }, // THEME: adapt
    axisLabel: { color: '#cfd9ee' }, // THEME: adapt
    nameTextStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Campaigns', // REPLACE
      type: 'scatter',
      data: [
        [120, 18, 42, 'Email'],
        [150, 22, 58, 'Search'],
        [95, 12, 36, 'Partner'],
        [180, 28, 76, 'Social']
      ], // REPLACE: [x, y, sizeMetric, label]
      symbolSize: function (value) {
        return Math.max(12, Math.sqrt(value[2]) * 4);
      },
      itemStyle: {
        opacity: 0.86,
        borderColor: '#ffffff', // THEME: adapt
        borderWidth: 1.5
      },
      emphasis: {
        focus: 'series',
        scale: true,
        label: {
          show: true,
          formatter: function (params) { return params.data[3]; },
          color: '#e6edf7', // THEME: adapt
          position: 'top'
        }
      }
    }
  ]
}
```

## Variants

### Variant 1: Simple scatter

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
  grid: {
    left: '10%',
    right: '8%',
    top: '14%',
    bottom: '14%',
    containLabel: true
  },
  xAxis: {
    type: 'value',
    name: 'Cost', // REPLACE
    nameLocation: 'middle',
    nameGap: 32,
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' }, // THEME: adapt
    nameTextStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    name: 'Satisfaction', // REPLACE
    nameGap: 38,
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee' }, // THEME: adapt
    nameTextStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Stores', // REPLACE
      type: 'scatter',
      data: [
        [22, 76],
        [28, 82],
        [31, 74],
        [36, 88],
        [40, 79]
      ], // REPLACE: [x, y]
      symbolSize: 18,
      itemStyle: {
        opacity: 0.88,
        borderColor: '#ffffff', // THEME: adapt
        borderWidth: 1.5
      },
      emphasis: { focus: 'series' }
    }
  ]
}
```

### Variant 2: Bubble chart

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' }, // THEME: adapt
    formatter: function (params) {
      return params.data[3] + '<br/>Market Share: ' + params.data[0] + '%<br/>Growth: ' + params.data[1] + '%<br/>Revenue: $' + params.data[2] + 'M';
    }
  },
  grid: {
    left: '10%',
    right: '8%',
    top: '14%',
    bottom: '14%',
    containLabel: true
  },
  xAxis: {
    type: 'value',
    name: 'Market Share %', // REPLACE
    nameLocation: 'middle',
    nameGap: 32,
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee', formatter: '{value}%' }, // THEME: adapt
    nameTextStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  yAxis: {
    type: 'value',
    name: 'Growth %', // REPLACE
    nameGap: 38,
    axisLine: { lineStyle: { color: 'rgba(255,255,255,0.24)' } },
    splitLine: { lineStyle: { color: 'rgba(255,255,255,0.08)' } },
    axisLabel: { color: '#cfd9ee', formatter: '{value}%' }, // THEME: adapt
    nameTextStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Vendors', // REPLACE
      type: 'scatter',
      data: [
        [26, 18, 120, 'Vendor A'],
        [18, 12, 88, 'Vendor B'],
        [12, 26, 54, 'Vendor C'],
        [34, 9, 160, 'Vendor D']
      ], // REPLACE: [x, y, sizeMetric, label]
      symbolSize: function (value) {
        return Math.max(16, Math.sqrt(value[2]) * 3.2);
      },
      itemStyle: {
        opacity: 0.8,
        borderColor: '#ffffff', // THEME: adapt
        borderWidth: 1.5
      },
      emphasis: {
        focus: 'series',
        label: {
          show: true,
          formatter: function (params) { return params.data[3]; },
          color: '#e6edf7', // THEME: adapt
          position: 'top'
        }
      }
    }
  ]
}
```

## Data Replacement Guide

- Replace axis names with real measure names and units.
- For base and bubble charts, provide data in `[x, y, sizeMetric, label]` format so tooltip and labels work unchanged.
- For simple scatter, provide `[x, y]` pairs and keep `symbolSize` fixed unless a third dimension is needed.
- Keep point counts modest on slides; 5-20 points is usually the sweet spot.
- If labels overlap, rely on emphasis labels instead of always-on labels.

## Theme Integration

- Replace the `color` array with the current theme's **ECharts Palette**.
- Adapt tooltip, axis lines, split lines, labels, and point borders to the theme's neutrals.
- On dark themes, keep white or near-white point borders; on light themes, switch borders to a darker neutral.
- Use a container such as `<div id="scatterChart" style="width:100%;height:min(420px,55vh);max-height:420px;"></div>`.

# Pie Chart / 饼图

Best for: composition, share-of-total stories, portfolio mix, and highlighting one dominant segment at a glance

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
    bottom: '4%',
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  title: {
    text: '64%', // REPLACE: center summary
    subtext: 'Returning Users', // REPLACE: center label
    left: 'center',
    top: '42%',
    textAlign: 'center',
    textStyle: {
      color: '#e6edf7', // THEME: adapt
      fontSize: 28,
      fontWeight: 700
    },
    subtextStyle: {
      color: '#cfd9ee' // THEME: adapt
    }
  },
  series: [
    {
      name: 'Traffic Sources', // REPLACE
      type: 'pie',
      radius: ['40%', '70%'],
      center: ['50%', '42%'],
      avoidLabelOverlap: true,
      itemStyle: {
        borderRadius: 10,
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt to slide background
        borderWidth: 2
      },
      label: {
        color: '#e6edf7', // THEME: adapt
        formatter: '{b}\\n{d}%'
      },
      labelLine: {
        lineStyle: { color: 'rgba(255,255,255,0.24)' } // THEME: adapt
      },
      emphasis: {
        scale: true,
        scaleSize: 8,
        itemStyle: {
          shadowBlur: 18,
          shadowColor: 'rgba(0, 0, 0, 0.28)'
        }
      },
      data: [
        { value: 40, name: 'Direct' },
        { value: 24, name: 'Search' },
        { value: 18, name: 'Social' },
        { value: 18, name: 'Partner' }
      ] // REPLACE
    }
  ]
}
```

## Variants

### Variant 1: Full pie

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
    bottom: '4%',
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Segment Mix', // REPLACE
      type: 'pie',
      radius: '72%',
      center: ['50%', '42%'],
      label: {
        color: '#e6edf7', // THEME: adapt
        formatter: '{b}: {d}%'
      },
      labelLine: {
        lineStyle: { color: 'rgba(255,255,255,0.24)' } // THEME: adapt
      },
      emphasis: {
        scale: true,
        scaleSize: 6,
        itemStyle: {
          shadowBlur: 16,
          shadowColor: 'rgba(0, 0, 0, 0.28)'
        }
      },
      data: [
        { value: 28, name: 'Enterprise' },
        { value: 22, name: 'Mid Market' },
        { value: 30, name: 'SMB' },
        { value: 20, name: 'Self-Serve' }
      ] // REPLACE
    }
  ]
}
```

### Variant 2: Rose chart

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
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Channel Impact', // REPLACE
      type: 'pie',
      radius: ['24%', '72%'],
      center: ['50%', '42%'],
      roseType: 'area',
      itemStyle: {
        borderRadius: 8,
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt
        borderWidth: 2
      },
      label: {
        color: '#e6edf7', // THEME: adapt
        formatter: '{b}: {c}'
      },
      emphasis: {
        scale: true,
        itemStyle: {
          shadowBlur: 16,
          shadowColor: 'rgba(0, 0, 0, 0.28)'
        }
      },
      data: [
        { value: 12, name: 'Email' },
        { value: 18, name: 'Events' },
        { value: 26, name: 'Paid Ads' },
        { value: 20, name: 'Referral' },
        { value: 16, name: 'Organic' }
      ] // REPLACE
    }
  ]
}
```

### Variant 3: Nested donut

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
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Region', // REPLACE
      type: 'pie',
      selectedMode: 'single',
      radius: ['24%', '42%'],
      center: ['50%', '42%'],
      label: {
        position: 'inside',
        color: '#ffffff', // THEME: adapt for contrast
        formatter: '{b}'
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt
        borderWidth: 2
      },
      data: [
        { value: 62, name: 'APAC' },
        { value: 38, name: 'EMEA' }
      ] // REPLACE
    },
    {
      name: 'Country', // REPLACE
      type: 'pie',
      radius: ['50%', '72%'],
      center: ['50%', '42%'],
      label: {
        color: '#e6edf7', // THEME: adapt
        formatter: '{b}: {d}%'
      },
      labelLine: {
        lineStyle: { color: 'rgba(255,255,255,0.24)' } // THEME: adapt
      },
      itemStyle: {
        borderRadius: 8,
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt
        borderWidth: 2
      },
      emphasis: { scale: true },
      data: [
        { value: 22, name: 'Japan' },
        { value: 18, name: 'Singapore' },
        { value: 22, name: 'Germany' },
        { value: 16, name: 'UK' },
        { value: 22, name: 'Other' }
      ] // REPLACE
    }
  ]
}
```

## Data Replacement Guide

- Replace every `data` item with `{ value, name }` objects using real segment names and numeric values.
- Update `title.text` and `title.subtext` in the base donut to match the highlight metric shown in the center.
- Keep categories to roughly 3-6 slices for slide readability; merge tiny slices into `Other` when needed.
- For nested donuts, ensure inner and outer rings use different aggregation levels.
- Use `formatter` strings to switch between raw values, percentages, or currency symbols as needed.

## Theme Integration

- Replace the `color` array with the current theme's **ECharts Palette**.
- Align `title`, `label`, `legend`, tooltip, and label line colors with the theme's text neutrals.
- Match slice border color to the slide background so donut and pie edges stay crisp on both dark and light themes.
- Use a container such as `<div id="pieChart" style="width:100%;height:min(420px,55vh);max-height:420px;"></div>`.

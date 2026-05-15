# Treemap / 矩形树图

Best for: hierarchical data, budget allocation, category breakdown, nested proportions, and portfolio composition

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
    formatter: '{b}: {c}'
  },
  series: [
    {
      name: 'Budget', // REPLACE
      type: 'treemap',
      top: '4%',
      left: '4%',
      right: '4%',
      bottom: '4%',
      roam: false,
      breadcrumb: { show: false },
      label: {
        show: true,
        color: '#ffffff', // THEME: adapt for contrast
        fontSize: 14,
        formatter: '{b}\n{c}'
      },
      upperLabel: {
        show: true,
        height: 30,
        color: '#ffffff', // THEME: adapt for contrast
        fontSize: 13
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.8)', // THEME: adapt to slide background
        borderWidth: 2,
        gapWidth: 2
      },
      levels: [
        {
          itemStyle: {
            borderWidth: 3,
            borderColor: 'rgba(10,16,30,0.9)', // THEME: adapt
            gapWidth: 3
          }
        },
        {
          itemStyle: {
            borderWidth: 1,
            gapWidth: 1
          },
          upperLabel: { show: true }
        }
      ],
      data: [
        {
          name: 'Engineering',
          value: 45,
          children: [
            { name: 'Frontend', value: 18 },
            { name: 'Backend', value: 15 },
            { name: 'DevOps', value: 12 }
          ]
        },
        {
          name: 'Marketing',
          value: 30,
          children: [
            { name: 'Digital', value: 18 },
            { name: 'Events', value: 12 }
          ]
        },
        { name: 'Operations', value: 25 }
      ] // REPLACE
    }
  ]
}
```

## Variants

### Variant 1: Flat treemap

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' }, // THEME: adapt
    formatter: '{b}: {c}'
  },
  series: [
    {
      name: 'Segments', // REPLACE
      type: 'treemap',
      roam: false,
      breadcrumb: { show: false },
      label: {
        show: true,
        color: '#ffffff', // THEME: adapt for contrast
        formatter: '{b}\n{c}'
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.8)', // THEME: adapt
        borderWidth: 2,
        gapWidth: 2
      },
      data: [
        { name: 'Platform', value: 32 },
        { name: 'Security', value: 24 },
        { name: 'AI', value: 18 },
        { name: 'Data', value: 14 },
        { name: 'Support', value: 12 }
      ] // REPLACE
    }
  ]
}
```

### Variant 2: With visual map

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' }, // THEME: adapt
    formatter: '{b}: {c}'
  },
  visualMap: {
    min: 0,
    max: 50, // REPLACE
    calculable: true,
    orient: 'horizontal',
    left: 'center',
    bottom: '2%',
    textStyle: { color: '#cfd9ee' }, // THEME: adapt
    inRange: {
      color: ['#4facfe', '#667eea', '#764ba2', '#f093fb'] // THEME: adapt
    }
  },
  series: [
    {
      name: 'Investment', // REPLACE
      type: 'treemap',
      top: '4%',
      left: '4%',
      right: '4%',
      bottom: '14%',
      roam: false,
      breadcrumb: { show: false },
      label: {
        show: true,
        color: '#ffffff', // THEME: adapt for contrast
        formatter: '{b}\n{c}'
      },
      upperLabel: {
        show: true,
        color: '#ffffff', // THEME: adapt for contrast
        height: 28
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.85)', // THEME: adapt
        borderWidth: 2,
        gapWidth: 2
      },
      data: [
        {
          name: 'Product',
          value: 42,
          children: [
            { name: 'Core', value: 20 },
            { name: 'Mobile', value: 12 },
            { name: 'Integrations', value: 10 }
          ]
        },
        {
          name: 'Go-To-Market',
          value: 28,
          children: [
            { name: 'Demand Gen', value: 16 },
            { name: 'Partnerships', value: 12 }
          ]
        },
        { name: 'Operations', value: 15 },
        { name: 'Enablement', value: 11 }
      ] // REPLACE
    }
  ]
}
```

## Data Replacement Guide

- Replace `series[].name` with the business domain being visualized, such as budget, headcount, product mix, or account portfolio.
- Replace every `data` node with `{ name, value }` objects; add `children` arrays only when you need nested hierarchy.
- Keep parent totals consistent with child values when the hierarchy is meant to roll up exactly.
- Use the flat treemap when a single-level proportion view is easier to read on slides; use nested groups only when hierarchy matters.
- For the visual-map variant, update `visualMap.min` and `visualMap.max` to reflect the actual data range and avoid compressed color bands.

## Theme Integration

- Replace the `color` array with the current theme's **ECharts Palette**.
- Adapt tooltip, label, upper-label, and visual-map text colors to the active theme neutrals for legibility on dark translucent surfaces.
- Match treemap border colors to the slide background or glass panel to keep tile separation crisp without harsh outlines.
- Adjust label density or font size when tiles become small so the chart stays presentation-friendly.
- Use a container such as `<div id="treemapChart" style="width:100%;height:min(480px,60vh);max-height:480px;"></div>`.

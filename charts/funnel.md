# Funnel Chart

Best for: conversion pipelines, sales funnels, process dropoff visualization, and staged progression analysis

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
    formatter: '{b}: {c} ({d}%)'
  },
  legend: {
    bottom: '4%',
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Conversion', // REPLACE
      type: 'funnel',
      left: '10%',
      top: '10%',
      bottom: '10%',
      width: '80%',
      min: 0,
      max: 100, // REPLACE
      minSize: '0%',
      maxSize: '100%',
      sort: 'descending',
      gap: 4,
      label: {
        show: true,
        position: 'inside',
        color: '#ffffff', // THEME: adapt for contrast
        fontSize: 14,
        formatter: '{b}\n{c}'
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt to slide background
        borderWidth: 2,
        borderRadius: 4
      },
      emphasis: {
        label: { fontSize: 16 }
      },
      data: [
        { value: 100, name: 'Visitors' },
        { value: 60, name: 'Leads' },
        { value: 40, name: 'Qualified' },
        { value: 20, name: 'Proposals' },
        { value: 8, name: 'Closed' }
      ] // REPLACE
    }
  ]
}
```

## Variants

### Variant 1: Ascending funnel

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
  legend: {
    bottom: '4%',
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'Growth Stages', // REPLACE
      type: 'funnel',
      left: '10%',
      top: '10%',
      bottom: '10%',
      width: '80%',
      min: 0,
      max: 100, // REPLACE
      sort: 'ascending',
      gap: 4,
      label: {
        show: true,
        position: 'inside',
        color: '#ffffff', // THEME: adapt for contrast
        formatter: '{b}\n{c}'
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt
        borderWidth: 2,
        borderRadius: 4
      },
      data: [
        { value: 8, name: 'Pilot' },
        { value: 18, name: 'Activation' },
        { value: 36, name: 'Expansion' },
        { value: 62, name: 'Adoption' },
        { value: 100, name: 'Awareness' }
      ] // REPLACE
    }
  ]
}
```

### Variant 2: Compare funnel

```js
{
  // THEME_COLORS: replace with theme's ECharts palette
  color: ['#667eea', '#764ba2', '#f093fb', '#4facfe', '#43e97b'],
  tooltip: {
    trigger: 'item',
    backgroundColor: 'rgba(13, 20, 39, 0.92)', // THEME: adapt
    borderColor: 'rgba(255,255,255,0.12)',
    textStyle: { color: '#e6edf7' }, // THEME: adapt
    formatter: '{a}<br/>{b}: {c}'
  },
  legend: {
    bottom: '3%',
    left: 'center',
    textStyle: { color: '#cfd9ee' } // THEME: adapt
  },
  series: [
    {
      name: 'This Quarter', // REPLACE
      type: 'funnel',
      left: '6%',
      width: '38%',
      top: '10%',
      bottom: '12%',
      sort: 'descending',
      gap: 4,
      label: {
        show: true,
        position: 'inside',
        color: '#ffffff', // THEME: adapt for contrast
        fontSize: 13
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt
        borderWidth: 2,
        borderRadius: 4,
        opacity: 0.95
      },
      data: [
        { value: 120, name: 'Visits' },
        { value: 74, name: 'Trials' },
        { value: 49, name: 'Qualified' },
        { value: 25, name: 'Negotiation' },
        { value: 10, name: 'Won' }
      ] // REPLACE
    },
    {
      name: 'Last Quarter', // REPLACE
      type: 'funnel',
      left: '56%',
      width: '38%',
      top: '10%',
      bottom: '12%',
      sort: 'descending',
      gap: 4,
      label: {
        show: true,
        position: 'inside',
        color: '#ffffff', // THEME: adapt for contrast
        fontSize: 13
      },
      itemStyle: {
        borderColor: 'rgba(10,16,30,0.6)', // THEME: adapt
        borderWidth: 2,
        borderRadius: 4,
        opacity: 0.68
      },
      data: [
        { value: 110, name: 'Visits' },
        { value: 68, name: 'Trials' },
        { value: 40, name: 'Qualified' },
        { value: 18, name: 'Negotiation' },
        { value: 7, name: 'Won' }
      ] // REPLACE
    }
  ]
}
```

## Data Replacement Guide

- Replace `series[].name` with the funnel label that matches the story: pipeline, onboarding, support resolution, hiring stages, etc.
- Update `max` so the largest stage value maps cleanly to the top width; keep all `data[].value` numbers on the same scale.
- Replace every `data` item with real stage labels and numeric values ordered by the intended story direction.
- Use `sort: 'descending'` for dropoff and conversion flows; use `sort: 'ascending'` for growth, maturity, or capability buildup narratives.
- In compare funnels, keep both series aligned to the same stage names so side-by-side comparisons remain readable.

## Theme Integration

- Replace the `color` array with the current theme's **ECharts Palette**.
- Adapt tooltip, legend, and label colors to the active theme neutrals while preserving strong contrast on dark glassmorphism slides.
- Match `itemStyle.borderColor` to the slide background or panel surface so each stage remains crisp against translucent cards.
- Keep label text bright enough for inside placement, or switch to outside labels if the theme or stage widths reduce contrast.
- Use a container such as `<div id="funnelChart" style="width:100%;height:min(480px,60vh);max-height:480px;"></div>`.

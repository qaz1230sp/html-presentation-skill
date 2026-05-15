# Stats Dashboard

Fragment count: 0 | Best for: KPI summaries, benchmark snapshots, and executive evidence slides

## HTML Template

The stats dashboard has limited content (title + stat cards). Wrap the main content in a `flex:1` centered div so it appears vertically centered, while `footer-note` stays at the bottom via `margin-top: auto`.

**Important:** The `<h2>` title stays OUTSIDE the centering wrapper (titles always anchor to the top). Only the stats-row content is wrapped for vertical centering in the remaining space.

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="stats-row">
      <div class="stat-item">
        <div class="stat-number"><!-- PLACEHOLDER: number --></div>
        <div class="stat-label"><!-- PLACEHOLDER: label --></div>
      </div>
      <div class="stat-item">
        <div class="stat-number"><!-- PLACEHOLDER: number --></div>
        <div class="stat-label"><!-- PLACEHOLDER: label --></div>
      </div>
      <div class="stat-item">
        <div class="stat-number"><!-- PLACEHOLDER: number --></div>
        <div class="stat-label"><!-- PLACEHOLDER: label --></div>
      </div>
      <div class="stat-item">
        <div class="stat-number"><!-- PLACEHOLDER: number --></div>
        <div class="stat-label"><!-- PLACEHOLDER: label --></div>
      </div>
    </div>
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: data source or note --></p>
</section>
```

## Usage Rules
- Use for 3-4 related metrics that should land simultaneously.
- Do not fragment stat items; the dashboard is one visual group.
- Maximum 4 stat items; if there are more, split into another slide.
- Labels should be short nouns; numbers should be easy to scan in under 2 seconds.

## Variant: with subtitle below stats

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="stats-row">
    <!-- PLACEHOLDER: 3-4 stat-item blocks -->
  </div>
  <div class="panel" style="margin-top:24px;">
    <p><!-- PLACEHOLDER: interpretation or summary sentence --></p>
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: source note --></p>
</section>
```

## Variant: with chart below stats

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="stats-row">
    <!-- PLACEHOLDER: 3-4 stat-item blocks -->
  </div>
  <div class="panel" style="margin-top:24px;">
    <div class="flow-diagram">
      <div class="flow-node"><!-- PLACEHOLDER: chart summary 1 --></div>
      <div class="flow-arrow">→</div>
      <div class="flow-node"><!-- PLACEHOLDER: chart summary 2 --></div>
      <div class="flow-arrow">→</div>
      <div class="flow-node"><!-- PLACEHOLDER: chart summary 3 --></div>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>Launch Metrics After Template Rollout</h2>
  <div class="stats-row">
    <div class="stat-item">
      <div class="stat-number">11</div>
      <div class="stat-label">LAYOUTS</div>
    </div>
    <div class="stat-item">
      <div class="stat-number">6</div>
      <div class="stat-label">THEMES</div>
    </div>
    <div class="stat-item">
      <div class="stat-number">15m</div>
      <div class="stat-label">FIRST DRAFT</div>
    </div>
    <div class="stat-item">
      <div class="stat-number">0</div>
      <div class="stat-label">MANUAL CSS FIXES</div>
    </div>
  </div>
  <p class="footer-note">Source: internal pilot deck generation benchmark, May 2026.</p>
</section>
```

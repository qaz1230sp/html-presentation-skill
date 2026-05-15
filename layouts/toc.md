# Table of Contents / 目录页

Fragment count: 0 | Best for: agenda overview, chapter navigation, deck structure preview

## Layout Selection Rules

| Items | Layout | Columns | Card Style |
|-------|--------|---------|------------|
| 2–3 | Horizontal cards | `repeat(N, 1fr)` | Centered, with gradient number + title + description |
| 4–6 | Two-column grid | `1fr 1fr` | Left-aligned, number + title inline |
| 7–10 | Two-column compact | `1fr 1fr` | Smaller padding, number + title only |
| 11+ | Three-column compact | `repeat(3, 1fr)` | Minimal padding, small font |

## Template A: Horizontal Cards (2–3 items)

Best for simple agendas. Each card is centered with large gradient number, title and description.

```html
<section style="overflow:hidden;">
  <h2><!-- TITLE --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div style="display:grid; grid-template-columns: repeat(3, 1fr); gap: 32px; max-width: 1400px; margin: 0 auto; width: 100%;">
      <div class="glass-card" style="padding: 36px 28px; text-align:center; border-bottom: 3px solid; border-image: var(--accent-gradient) 1;">
        <div style="font-size:2.2em; font-weight:900; background: var(--accent-gradient); -webkit-background-clip:text; -webkit-text-fill-color:transparent; margin-bottom:12px;">01</div>
        <h3 style="font-size:1.1em; margin:0 0 8px;"><!-- TITLE --></h3>
        <p style="font-size:0.78em; color: var(--r-muted-color); margin:0;"><!-- DESCRIPTION --></p>
      </div>
      <!-- repeat per item -->
    </div>
  </div>
</section>
```

## Template B: Two-Column Grid (4–6 items)

```html
<section style="overflow:hidden;">
  <h2><!-- TITLE --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid" style="grid-template-columns: 1fr 1fr; gap: 16px; max-width: 1200px; margin: 0 auto;">
      <div class="info-card glass-card" style="display:flex; align-items:center; gap:20px; padding:18px 28px;">
        <span style="font-size:1.6em; font-weight:800; background: var(--accent-gradient); -webkit-background-clip:text; -webkit-text-fill-color:transparent;">01</span>
        <span><!-- CHAPTER TITLE --></span>
      </div>
      <!-- repeat per item -->
    </div>
  </div>
</section>
```

## Template C: Two-Column Compact (7–10 items)

```html
<section style="overflow:hidden;">
  <h2><!-- TITLE --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid" style="grid-template-columns: 1fr 1fr; gap: 12px; max-width: 1200px; margin: 0 auto;">
      <div class="info-card glass-card" style="display:flex; align-items:center; gap:16px; padding:14px 22px; font-size:0.9em;">
        <span style="font-size:1.3em; font-weight:800; background: var(--accent-gradient); -webkit-background-clip:text; -webkit-text-fill-color:transparent;">01</span>
        <span><!-- CHAPTER TITLE --></span>
      </div>
      <!-- repeat per item -->
    </div>
  </div>
</section>
```

## Template D: Three-Column Compact (11+ items)

```html
<section style="overflow:hidden;">
  <h2><!-- TITLE --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid" style="grid-template-columns: repeat(3, 1fr); gap: 10px; max-width: 1500px; margin: 0 auto;">
      <div class="info-card glass-card" style="display:flex; align-items:center; gap:14px; padding:12px 18px; font-size:0.82em;">
        <span style="font-size:1.1em; font-weight:800; background: var(--accent-gradient); -webkit-background-clip:text; -webkit-text-fill-color:transparent;">01</span>
        <span><!-- CHAPTER TITLE --></span>
      </div>
      <!-- repeat per item -->
    </div>
  </div>
</section>
```

## Usage Rules
- Use at the beginning of the deck, usually right after the title slide.
- Pick the template (A/B/C/D) based on number of items.
- Each number uses gradient accent color for visual pop.
- Keep ordinal numbers in the format `01`, `02`, `03`.
- Template A supports optional description text; B/C/D are title-only for density.

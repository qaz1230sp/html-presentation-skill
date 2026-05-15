# Card Grid

Fragment count: 0 | Best for: feature sets, parallel concepts, and quick multi-item scanning

## HTML Template

```html
<section style="overflow:hidden; display:flex !important; flex-direction:column; justify-content:center;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="card-grid">
    <div class="info-card glass-card">
      <h3><!-- PLACEHOLDER: card title --></h3>
      <p><!-- PLACEHOLDER: card description --></p>
    </div>
    <div class="info-card glass-card">
      <h3><!-- PLACEHOLDER: card title --></h3>
      <p><!-- PLACEHOLDER: card description --></p>
    </div>
    <div class="info-card glass-card">
      <h3><!-- PLACEHOLDER: card title --></h3>
      <p><!-- PLACEHOLDER: card description --></p>
    </div>
  </div>
</section>
```

## Usage Rules
- Use for 3 cards in one row or 6 cards across two rows.
- Do not fragment cards; the grid should appear as a whole.
- Each card should contain a short title and 1-2 sentences max.
- Works best when all cards are parallel in structure and importance.

## Variant: six-card matrix

```html
<section style="overflow:hidden; display:flex !important; flex-direction:column; justify-content:center;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="card-grid">
    <div class="info-card glass-card"><h3><!-- PLACEHOLDER --></h3><p><!-- PLACEHOLDER --></p></div>
    <div class="info-card glass-card"><h3><!-- PLACEHOLDER --></h3><p><!-- PLACEHOLDER --></p></div>
    <div class="info-card glass-card"><h3><!-- PLACEHOLDER --></h3><p><!-- PLACEHOLDER --></p></div>
    <div class="info-card glass-card"><h3><!-- PLACEHOLDER --></h3><p><!-- PLACEHOLDER --></p></div>
    <div class="info-card glass-card"><h3><!-- PLACEHOLDER --></h3><p><!-- PLACEHOLDER --></p></div>
    <div class="info-card glass-card"><h3><!-- PLACEHOLDER --></h3><p><!-- PLACEHOLDER --></p></div>
  </div>
</section>
```

## Variant: card grid with icons

Best for: feature highlights where each card has a distinct icon. Uses `.icon-wrap` for a themed icon container.

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid" style="grid-template-columns:repeat(2, minmax(0, 1fr));">
      <div class="info-card glass-card">
        <div class="icon-wrap"><!-- PLACEHOLDER: inline SVG icon (28x28) --></div>
        <h3><!-- PLACEHOLDER: card title --></h3>
        <p><!-- PLACEHOLDER: card description --></p>
      </div>
      <div class="info-card glass-card">
        <div class="icon-wrap"><!-- PLACEHOLDER: inline SVG icon (28x28) --></div>
        <h3><!-- PLACEHOLDER: card title --></h3>
        <p><!-- PLACEHOLDER: card description --></p>
      </div>
      <div class="info-card glass-card">
        <div class="icon-wrap"><!-- PLACEHOLDER: inline SVG icon (28x28) --></div>
        <h3><!-- PLACEHOLDER: card title --></h3>
        <p><!-- PLACEHOLDER: card description --></p>
      </div>
      <div class="info-card glass-card">
        <div class="icon-wrap"><!-- PLACEHOLDER: inline SVG icon (28x28) --></div>
        <h3><!-- PLACEHOLDER: card title --></h3>
        <p><!-- PLACEHOLDER: card description --></p>
      </div>
    </div>
  </div>
</section>
```

### Icon guidelines
- Use inline SVG with `width="28" height="28"`, `fill="none"`, `stroke="currentColor"`, `stroke-width="2"`
- `.icon-wrap` provides a 56×56px circular container with theme-colored background
- Keep icon simple — one concept per icon (e.g., arrows for "reusable", clock for "automated")
- Use 2×2 grid (`grid-template-columns:repeat(2, ...)`) for 4 cards with icons
- Use default 3-column grid for 3 or 6 cards without icons

## Variant: card grid with section tag

```html
<section style="overflow:hidden; display:flex !important; flex-direction:column; justify-content:center;">
  <span class="tag"><!-- PLACEHOLDER: section id --></span>
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="card-grid">
    <!-- PLACEHOLDER: 3 or 6 info-card glass-card blocks -->
  </div>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden; display:flex !important; flex-direction:column; justify-content:center;">
  <h2>What a Great Slide System Needs</h2>
  <div class="card-grid">
    <div class="info-card glass-card">
      <h3>Consistent Classes</h3>
      <p>Templates stay portable when every theme honors the same layout contract.</p>
    </div>
    <div class="info-card glass-card">
      <h3>Low Content Density</h3>
      <p>Each card should land one idea fast enough for a narrated recording.</p>
    </div>
    <div class="info-card glass-card">
      <h3>Concrete Examples</h3>
      <p>Agents produce better slides when they can imitate real filled-in markup.</p>
    </div>
  </div>
</section>
```

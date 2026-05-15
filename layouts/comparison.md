# Comparison / 对比页

Fragment count: 1 | Best for: before/after, problem/solution, and old-way/new-way contrasts

## HTML Template

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: comparison title --></h2>
  <div class="compare-table">
    <div class="compare-col compare-bad glass-card">
      <h3><!-- PLACEHOLDER: "Before" / "Problem" / "Old Way" --></h3>
      <ul>
        <li><!-- PLACEHOLDER --></li>
      </ul>
    </div>
    <div class="compare-col compare-good glass-card fragment fade-up">
      <h3><!-- PLACEHOLDER: "After" / "Solution" / "New Way" --></h3>
      <ul>
        <li><!-- PLACEHOLDER --></li>
      </ul>
    </div>
  </div>
</section>
```

## Usage Rules
- Use when one side establishes tension and the other resolves it.
- Reveal the right column as the only fragment; left column anchors the setup.
- Keep both sides balanced: 2-4 bullets each, similar wording length.
- Do not fragment individual list items inside compare columns.

## Variant: before vs after

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: transformation title --></h2>
  <div class="compare-table">
    <div class="compare-col compare-bad glass-card">
      <h3>Before</h3>
      <ul>
        <li><!-- PLACEHOLDER: pain point 1 --></li>
        <li><!-- PLACEHOLDER: pain point 2 --></li>
        <li><!-- PLACEHOLDER: pain point 3 --></li>
      </ul>
    </div>
    <div class="compare-col compare-good glass-card fragment fade-up">
      <h3>After</h3>
      <ul>
        <li><!-- PLACEHOLDER: improvement 1 --></li>
        <li><!-- PLACEHOLDER: improvement 2 --></li>
        <li><!-- PLACEHOLDER: improvement 3 --></li>
      </ul>
    </div>
  </div>
</section>
```

## Variant: problem vs solution

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="compare-table">
    <div class="compare-col compare-bad glass-card">
      <h3>Problem</h3>
      <p><!-- PLACEHOLDER: short problem summary --></p>
      <ul>
        <li><!-- PLACEHOLDER --></li>
        <li><!-- PLACEHOLDER --></li>
      </ul>
    </div>
    <div class="compare-col compare-good glass-card fragment fade-up">
      <h3>Solution</h3>
      <p><!-- PLACEHOLDER: short solution summary --></p>
      <ul>
        <li><!-- PLACEHOLDER --></li>
        <li><!-- PLACEHOLDER --></li>
      </ul>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>Static Prompting vs Structured Layout References</h2>
  <div class="compare-table">
    <div class="compare-col compare-bad glass-card">
      <h3>Old Way</h3>
      <ul>
        <li>Agents guess slide structure from prose alone.</li>
        <li>Visual density varies wildly between decks.</li>
        <li>Fixes require manual HTML editing after generation.</li>
      </ul>
    </div>
    <div class="compare-col compare-good glass-card fragment fade-up">
      <h3>New Way</h3>
      <ul>
        <li>Templates encode the exact HTML skeleton to follow.</li>
        <li>Fragment limits are explicit and reusable.</li>
        <li>Themes and layouts compose predictably across topics.</li>
      </ul>
    </div>
  </div>
</section>
```

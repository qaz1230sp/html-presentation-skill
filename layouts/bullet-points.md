# Bullet Points / 要点列表页

Fragment count: max 3 | Best for: sequential talking points, agenda items, and concise takeaways

## HTML Template

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <ul>
    <li class="fragment fade-up"><!-- PLACEHOLDER: point 1 --></li>
    <li class="fragment fade-up"><!-- PLACEHOLDER: point 2 --></li>
    <li class="fragment fade-up"><!-- PLACEHOLDER: point 3 --></li>
  </ul>
  <p class="footer-note"><!-- PLACEHOLDER: optional note --></p>
</section>
```

## Usage Rules
- Use when the speaker should reveal points one by one.
- Best for 2-3 bullets with one sentence each; split if content gets dense.
- Maximum 3 fragments on this slide; do not add extra fragment items.
- Keep the footer note short: source, caveat, or transition insight.

## Variant: panel wrapper

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="panel">
    <ul>
      <li class="fragment fade-up"><!-- PLACEHOLDER: point 1 --></li>
      <li class="fragment fade-up"><!-- PLACEHOLDER: point 2 --></li>
      <li class="fragment fade-up"><!-- PLACEHOLDER: point 3 --></li>
    </ul>
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: optional note --></p>
</section>
```

## Variant: numbered list

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <ol>
    <li class="fragment fade-up"><!-- PLACEHOLDER: step 1 --></li>
    <li class="fragment fade-up"><!-- PLACEHOLDER: step 2 --></li>
    <li class="fragment fade-up"><!-- PLACEHOLDER: step 3 --></li>
  </ol>
  <p class="footer-note"><!-- PLACEHOLDER: optional note --></p>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>Why Teams Adopt HTML Slides</h2>
  <ul>
    <li class="fragment fade-up">Ship decks as plain files with no build pipeline.</li>
    <li class="fragment fade-up">Reuse code, charts, and screenshots from engineering workflows.</li>
    <li class="fragment fade-up">Record polished demos directly from the browser.</li>
  </ul>
  <p class="footer-note">Keep bullets atomic; one idea per click keeps pacing crisp.</p>
</section>
```

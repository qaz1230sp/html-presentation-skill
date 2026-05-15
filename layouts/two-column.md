# Two Column

Fragment count: 1 | Best for: comparisons, text-plus-visual explanations, and before/after storytelling

## HTML Template

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="two-col">
    <div class="panel">
      <!-- PLACEHOLDER: left column content (text, list, or image) -->
    </div>
    <div class="panel fragment fade-up">
      <!-- PLACEHOLDER: right column content -->
    </div>
  </div>
</section>
```

## Usage Rules
- Use when two blocks should be scanned side by side.
- Keep the left column visible immediately and reveal the right column as the single fragment.
- Works best for text+image, text+code, list+list, or explanation+evidence.
- Limit each column to one compact content block to avoid vertical overflow.

## Variant: text + code

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="two-col">
    <div class="panel">
      <h3><!-- PLACEHOLDER: explanation heading --></h3>
      <p><!-- PLACEHOLDER: short explanation --></p>
      <ul>
        <li><!-- PLACEHOLDER: point 1 --></li>
        <li><!-- PLACEHOLDER: point 2 --></li>
      </ul>
    </div>
    <div class="panel fragment fade-up">
      <pre><code class="language-js" data-trim>
<!-- PLACEHOLDER: code block -->
      </code></pre>
    </div>
  </div>
</section>
```

## Variant: text + image

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="two-col">
    <div class="panel">
      <!-- PLACEHOLDER: summary text -->
    </div>
    <div class="panel fragment fade-up">
      <div class="img-frame">
        <img src="<!-- PLACEHOLDER: image path -->" alt="<!-- PLACEHOLDER: alt text -->">
      </div>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>Outline First, HTML Second</h2>
  <div class="two-col">
    <div class="panel">
      <h3>Planning Layer</h3>
      <p>Start with the talk track before writing any markup.</p>
      <ul>
        <li>Hook, problem, core idea, evidence, takeaway</li>
        <li>One message per slide keeps the recording clean</li>
      </ul>
    </div>
    <div class="panel fragment fade-up">
      <h3>Execution Layer</h3>
      <p>Map each story beat to a reusable layout template and only then fill placeholders.</p>
    </div>
  </div>
</section>
```

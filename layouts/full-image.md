# Full Image / 全图展示页

Fragment count: 0 | Best for: screenshots, architecture diagrams, and visual proof slides

## HTML Template

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: image caption/title --></h2>
  <div class="img-frame">
    <img src="<!-- PLACEHOLDER: image path or base64 data URI -->" alt="<!-- PLACEHOLDER -->" style="max-width:100%;max-height:500px;">
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: source attribution --></p>
</section>
```

## Usage Rules
- Use when one image should dominate the slide.
- Best for screenshots, dashboards, architecture exports, and product mockups.
- Keep the title short and the footer limited to attribution or one insight.
- Do not fragment the image; visual comprehension should be immediate.

## Variant: image with side text

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="two-col">
    <div class="img-frame">
      <img src="<!-- PLACEHOLDER: image path -->" alt="<!-- PLACEHOLDER: alt text -->" style="max-width:100%;max-height:420px;">
    </div>
    <div class="panel">
      <h3><!-- PLACEHOLDER: interpretation heading --></h3>
      <p><!-- PLACEHOLDER: supporting explanation --></p>
    </div>
  </div>
</section>
```

## Variant: full-bleed style

```html
<section style="overflow:hidden;">
  <div class="img-frame">
    <img src="<!-- PLACEHOLDER: image path or data URI -->" alt="<!-- PLACEHOLDER: alt text -->" style="max-width:100%;max-height:560px;">
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: minimal caption or source --></p>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>Generated Deck Preview</h2>
  <div class="img-frame">
    <img src="images/skill-preview.png" alt="Preview of the generated presentation" style="max-width:100%;max-height:500px;">
  </div>
  <p class="footer-note">Source: local browser render of the presentation template demo.</p>
</section>
```

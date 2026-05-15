# Quote Highlight / 引言强调页

Fragment count: 0 | Best for: memorable quotes, strategic principles, and audience reset moments

## HTML Template

```html
<section class="quote-section" style="overflow:hidden;">
  <blockquote>
    <p><!-- PLACEHOLDER: quote text --></p>
    <cite><!-- PLACEHOLDER: attribution --></cite>
  </blockquote>
</section>
```

## Usage Rules
- Use when one sentence should slow the pace and anchor meaning.
- Best for executive quotes, design principles, or strong takeaways.
- Keep the quote under 35 words and the attribution to one line.
- Do not add fragments; this slide is about instant emotional clarity.

## Variant: with context text above

```html
<section class="quote-section" style="overflow:hidden;">
  <p class="meta"><!-- PLACEHOLDER: context label --></p>
  <blockquote>
    <p><!-- PLACEHOLDER: quote text --></p>
    <cite><!-- PLACEHOLDER: attribution --></cite>
  </blockquote>
</section>
```

## Variant: with image of person

```html
<section class="quote-section" style="overflow:hidden;">
  <div class="two-col">
    <div class="img-frame">
      <img src="<!-- PLACEHOLDER: portrait path -->" alt="<!-- PLACEHOLDER: person name -->" style="max-width:100%;max-height:380px;">
    </div>
    <div>
      <blockquote>
        <p><!-- PLACEHOLDER: quote text --></p>
        <cite><!-- PLACEHOLDER: attribution --></cite>
      </blockquote>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section class="quote-section" style="overflow:hidden;">
  <p class="meta">GUIDING PRINCIPLE</p>
  <blockquote>
    <p>Good presentation systems reduce formatting choices so storytellers can spend their energy on the message.</p>
    <cite>Hazel · Dev Productivity Team</cite>
  </blockquote>
</section>
```

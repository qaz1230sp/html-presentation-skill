# Title Hero

Fragment count: 0 | Best for: opening slides, keynote covers, and strong narrative hooks

## HTML Template

```html
<section class="title-slide" style="overflow:hidden;">
  <h1 class="hero-title"><!-- PLACEHOLDER: main title --></h1>
  <div class="accent-line"></div>
  <p class="subtitle"><!-- PLACEHOLDER: subtitle or tagline (optional, keep short) --></p>
  <p class="meta"><!-- PLACEHOLDER: speaker name · date --></p>
</section>
```

## Usage Rules
- Use as the first slide. Keep it **clean and minimal** like a real PPT cover.
- **Title only + speaker + date** is the ideal first slide. Do NOT add explanatory paragraphs.
- Do NOT use `<div class="panel">` on the title slide — it adds unnecessary visual weight.
- Do NOT use tags on the title slide unless the user explicitly requests them.
- Keep the title under 10 words, the subtitle under 15 words.
- The meta line should contain only: speaker name, date, and optionally the event/team name.
- Do not add fragments; all title-slide content should appear together.

## Variant: with panel (only when user explicitly requests more context)

```html
<section class="title-slide" style="overflow:hidden;">
  <p class="meta"><!-- PLACEHOLDER: event / date --></p>
  <h1 class="hero-title"><!-- PLACEHOLDER: main title --></h1>
  <div class="accent-line"></div>
  <p class="subtitle"><!-- PLACEHOLDER: subtitle --></p>
  <div class="panel" style="margin-top:28px;max-width:920px;">
    <p><!-- PLACEHOLDER: speaker / team / context --></p>
  </div>
</section>
```

## Example: glassmorphism

```html
<section class="title-slide" style="overflow:hidden;">
  <h1 class="hero-title">Turn Raw Notes into Record-Ready Slides</h1>
  <div class="accent-line"></div>
  <p class="subtitle">A reusable reveal.js workflow for fast technical storytelling</p>
  <p class="meta">Hazel · May 2026</p>
</section>
```

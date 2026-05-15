# End CTA / 结束行动页

Fragment count: 0 | Best for: closing thanks, next steps, contact details

## HTML Template

```html
<section class="end-slide" style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: Thank You / 谢谢 / THANKS --></h2>
  <div class="accent-line"></div>
  <p class="subtitle"><!-- PLACEHOLDER: speaker name · contact (optional) --></p>
</section>
```

## Usage Rules
- Use as the final slide. Keep it **simple and clean** — just like a real PPT ending.
- The default is a simple "Thank You" or "THANKS" with optional speaker name.
- Do NOT add long explanatory text, stats, or next-step paragraphs unless the user explicitly asks.
- Do NOT add a stats-row unless the user specifically requests closing metrics.
- Do not fragment closing content; the ending should feel complete on entry.
- **Always use `<h2>` not `<h1>`** — theme CSS targets `.end-slide h2`.

## Variant: with Q&A prompt

```html
<section class="end-slide" style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: Q&A / 问答环节 --></h2>
  <div class="accent-line"></div>
  <p class="subtitle"><!-- PLACEHOLDER: speaker name · contact --></p>
</section>
```

## Variant: with final metrics (only when user explicitly requests)

```html
<section class="end-slide" style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: closing message --></h2>
  <div class="accent-line"></div>
  <p class="subtitle"><!-- PLACEHOLDER: next step or CTA --></p>
  <div class="stats-row" style="margin-top:28px;">
    <div class="stat-item">
      <div class="stat-number"><!-- PLACEHOLDER: number --></div>
      <div class="stat-label"><!-- PLACEHOLDER: label --></div>
    </div>
    <div class="stat-item">
      <div class="stat-number"><!-- PLACEHOLDER: number --></div>
      <div class="stat-label"><!-- PLACEHOLDER: label --></div>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section class="end-slide" style="overflow:hidden;">
  <h2>Thank You</h2>
  <div class="accent-line"></div>
  <p class="subtitle">Jack Fu</p>
</section>
```

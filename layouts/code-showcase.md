# Code Showcase

Fragment count: 0 | Best for: code explanations, API snippets, and implementation walkthroughs

## HTML Template

```html
<section class="code-showcase" style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: code topic --></h2>
  <div class="two-col">
    <div>
      <ul>
        <li><!-- PLACEHOLDER: explanation point 1 --></li>
        <li><!-- PLACEHOLDER: explanation point 2 --></li>
      </ul>
    </div>
    <div>
      <pre><code class="language-xxx" data-trim>
<!-- PLACEHOLDER: code block, max 12 lines -->
      </code></pre>
    </div>
  </div>
</section>
```

## Usage Rules
- Use when the code itself is central to the slide's message.
- Keep code to 12 lines max and explanations to 2-3 bullets.
- Do not fragment this slide; the viewer should see code and commentary together.
- Prefer one focused snippet over a full file dump.

## Variant: full-width code

```html
<section class="code-showcase" style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: code topic --></h2>
  <pre><code class="language-xxx" data-trim>
<!-- PLACEHOLDER: code block, max 12 lines -->
  </code></pre>
  <p class="footer-note"><!-- PLACEHOLDER: why this snippet matters --></p>
</section>
```

## Variant: code + output

```html
<section class="code-showcase" style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: code topic --></h2>
  <div class="two-col">
    <div>
      <pre><code class="language-xxx" data-trim>
<!-- PLACEHOLDER: code block -->
      </code></pre>
    </div>
    <div class="panel">
      <h3><!-- PLACEHOLDER: output label --></h3>
      <p><!-- PLACEHOLDER: observed result or explanation --></p>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section class="code-showcase" style="overflow:hidden;">
  <h2>Build Slides from Reusable Blocks</h2>
  <div class="two-col">
    <div>
      <ul>
        <li>Load the selected theme reference before generating HTML.</li>
        <li>Choose a layout template that matches the content shape.</li>
        <li>Fill placeholders instead of inventing markup from scratch.</li>
      </ul>
    </div>
    <div>
      <pre><code class="language-js" data-trim>
const slide = renderLayout('title-hero', {
  meta: 'MAY 2026',
  title: 'HTML Presentation Skill',
  subtitle: 'Reusable layouts for faster decks'
});

slides.push(slide);
      </code></pre>
    </div>
  </div>
</section>
```

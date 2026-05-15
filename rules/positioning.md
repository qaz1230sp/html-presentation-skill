# Positioning & Content Rules

## Layout Positioning (critical — causes bugs if violated)

- Every `<section>` gets `height:100%` from theme CSS
- Content-heavy pages (bullet-points, timeline): `justify-content: flex-start`
- Content-centered pages (two-column, comparison, code-showcase, card-grid, stats-dashboard, icon-grid, flowchart, table): body content in `<div style="flex:1; display:flex; flex-direction:column; justify-content:center;">` wrapper. `<h2>` title stays OUTSIDE wrapper.
- Special pages (.title-slide, .quote-section, .end-slide): `justify-content: center !important` from CSS
- `.two-col` and `.compare-table`: `align-items: stretch`
- NEVER add `position: relative` to sections — reveal.js requires `position: absolute`

## Footer-note Placement (critical — breaks vertical centering if wrong)

`.footer-note` has `margin-top: auto` in theme CSS. This is designed to push the footer to the bottom of the section. **But it MUST be placed correctly:**

**Correct structure** — footer-note is a SIBLING of the flex:1 centering wrapper:
```html
<section style="overflow:hidden;">
  <h2>Title</h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <!-- content gets vertically centered in remaining space -->
  </div>
  <p class="footer-note">Note text</p>  <!-- OUTSIDE the centering div -->
</section>
```

**Wrong structure** — footer-note INSIDE the centering wrapper:
```html
<!-- ❌ DO NOT DO THIS — margin-top:auto inside justify-content:center
     pushes content to the top, breaking vertical centering -->
<section style="overflow:hidden;">
  <h2>Title</h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <!-- content here -->
    <p class="footer-note">Note text</p>  <!-- WRONG POSITION -->
  </div>
</section>
```

**Why it breaks:** When `footer-note` (with `margin-top:auto`) is inside a `justify-content:center` flex container, the auto margin overrides centering — it pushes the footer to the bottom and all preceding content to the top.

**The fix:** `footer-note` must be a direct child of `<section>`, after the `flex:1` wrapper. The `flex:1` wrapper occupies the space between `<h2>` and `footer-note`, and `justify-content:center` vertically centers only the actual content within that space.

## Content Style Rules (critical for PPT quality)

- **Title slide**: minimal — title, subtitle, speaker, date. NO paragraphs/panels/tags.
- **End slide**: simple — "Thank You" + speaker. Use `<h2>` not `<h1>`. NO stats/long text.
- **Content-light slides**: center content vertically.
- **`.hero-title`**: `white-space: nowrap; text-align: center`
- Write like a **real PPT presenter** — short phrases, not sentences.

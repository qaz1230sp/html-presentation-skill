# Section Divider / 章节分隔页

Fragment count: 0 | Best for: visual chapter transitions, section introductions

## HTML Template

```html
<section class="title-slide" style="overflow:hidden;">
  <span class="tag" style="font-size:2.4em; font-weight:900; margin-bottom:16px;"><!-- PLACEHOLDER: section number e.g. 02 --></span>
  <h1 class="hero-title"><!-- PLACEHOLDER: section title --></h1>
  <p style="font-size:1.1em; opacity:0.7;"><!-- PLACEHOLDER: optional subtitle --></p>
</section>
```

## Usage Rules
- Use before each major section to create visual breathing room and reset attention.
- Keep it minimal: section number, title, and optionally one short subtitle line.
- Use the `.title-slide` class so theme CSS handles centering automatically.
- Do NOT add paragraphs, cards, stats, or other heavy content to this slide.

## Variant: with icon or emoji

```html
<section class="title-slide" style="overflow:hidden;">
  <span class="tag" style="font-size:2.4em; font-weight:900; margin-bottom:16px;"><!-- PLACEHOLDER: section number e.g. 02 --></span>
  <h1 class="hero-title"><!-- PLACEHOLDER: emoji or icon --> <!-- PLACEHOLDER: section title --></h1>
  <p style="font-size:1.1em; opacity:0.7;"><!-- PLACEHOLDER: optional subtitle --></p>
</section>
```

## Example: glassmorphism

```html
<section class="title-slide" style="overflow:hidden;">
  <span class="tag" style="font-size:2.4em; font-weight:900; margin-bottom:16px;">02</span>
  <h1 class="hero-title">技术架构</h1>
  <p style="font-size:1.1em; opacity:0.7;">从设计到实现的完整链路</p>
</section>
```

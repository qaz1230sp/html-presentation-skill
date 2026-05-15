# Icon Grid / 图标网格页

Fragment count: 0 | Best for: feature highlights, technology stacks, and capability overviews — lighter than card-grid

## HTML Template

The icon grid is content-light, so wrap the grid body in a `flex:1` centered div for better vertical balance.

**Important:** The `<h2>` title stays OUTSIDE the centering wrapper (titles always anchor to the top). Only the icon grid content is wrapped for vertical centering in the remaining space.

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid">
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
    </div>
  </div>
</section>
```

## Usage Rules
- Use for 3-6 items that are parallel in importance.
- Each item should contain an emoji or icon, a short title, and a one-line description.
- Lighter than card-grid: no glass-card borders, more breathing room, and faster scanning.
- Best for technology stacks, feature overviews, and capability lists.
- Keep descriptions to one line max.

## Variant: with glass cards

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid">
      <div class="info-card glass-card" style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <!-- repeat for each item -->
    </div>
  </div>
</section>
```

## Variant: 4-column

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid" style="grid-template-columns: repeat(4, 1fr);">
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0 0 8px;"><!-- PLACEHOLDER: feature name --></h3>
        <p style="font-size:0.85em; opacity:0.8;"><!-- PLACEHOLDER: one-line description --></p>
      </div>
      <!-- repeat for 4 items -->
    </div>
  </div>
</section>
```

## Variant: title-only

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid">
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;"><!-- PLACEHOLDER: emoji --></div>
        <h3 style="margin:0;"><!-- PLACEHOLDER: feature name --></h3>
      </div>
      <!-- repeat for each item -->
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>技术栈</h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="card-grid">
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;">🐍</div>
        <h3 style="margin:0 0 8px;">Python</h3>
        <p style="font-size:0.85em; opacity:0.8;">核心引擎</p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;">⚛️</div>
        <h3 style="margin:0 0 8px;">React</h3>
        <p style="font-size:0.85em; opacity:0.8;">前端界面</p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;">🗄️</div>
        <h3 style="margin:0 0 8px;">PostgreSQL</h3>
        <p style="font-size:0.85em; opacity:0.8;">数据存储</p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;">🐳</div>
        <h3 style="margin:0 0 8px;">Docker</h3>
        <p style="font-size:0.85em; opacity:0.8;">容器部署</p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;">☁️</div>
        <h3 style="margin:0 0 8px;">Azure</h3>
        <p style="font-size:0.85em; opacity:0.8;">云服务</p>
      </div>
      <div style="text-align:center; padding:20px;">
        <div style="font-size:2.4em; margin-bottom:12px;">🤖</div>
        <h3 style="margin:0 0 8px;">OpenAI</h3>
        <p style="font-size:0.85em; opacity:0.8;">AI 能力</p>
      </div>
    </div>
  </div>
</section>
```

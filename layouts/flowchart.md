# Flowchart / 流程图页 (Design C — Progress Track)

Fragment count: 0 | Best for: process workflows, step-by-step guides, linear pipelines

## Design

Uses a horizontal progress track with numbered circles sitting on the track line. Each step has a colored circle (number), a title below, and an optional description. The track is a thin bar that passes through the vertical center of all circles.

**Key measurements (reveal.js context):**
- Circle diameter: 88px (track `top` = diameter / 2 = 44px)
- Circle font: `2rem`, weight `800`
- Title: `0.72em`, weight `700`
- Description: `0.42em`, line-height `1.6`
- Wrapper: `width:90%; max-width:1100px`
- Description max-width: `160px` with `margin:0 auto` for centering

**Positioning math:**
- Track div: `position:absolute; top:44px` (half of 88px circle diameter)
- Circle container: `position:relative; z-index:1`
- Track naturally passes through the center of each circle

## HTML Template (3-4 steps)

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div style="position:relative; width:90%; max-width:1100px; margin:0 auto;">
      <!-- Track bar (background + gradient overlay) -->
      <div style="position:absolute; top:44px; left:8%; right:8%; height:4px; background:/* PLACEHOLDER: track-bg from theme */; border-radius:2px; z-index:0;"></div>
      <div style="position:absolute; top:44px; left:8%; right:8%; height:4px; background:linear-gradient(90deg, /* PLACEHOLDER: 4 theme colors */); border-radius:2px; opacity:0.6; z-index:0;"></div>
      <!-- Steps container -->
      <div style="display:flex; justify-content:space-between; position:relative; z-index:1;">
        <!-- Step 1 -->
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:/* PLACEHOLDER: color-1 */; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px /* PLACEHOLDER: shadow-1 */;">1</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:/* PLACEHOLDER: title-color */;"><!-- PLACEHOLDER: step title --></h4>
          <p style="font-size:0.42em; color:/* PLACEHOLDER: desc-color */; line-height:1.6; max-width:160px; margin:0 auto;"><!-- PLACEHOLDER: step description --></p>
        </div>
        <!-- Step 2 -->
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:/* PLACEHOLDER: color-2 */; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px /* PLACEHOLDER: shadow-2 */;">2</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:/* PLACEHOLDER: title-color */;"><!-- PLACEHOLDER: step title --></h4>
          <p style="font-size:0.42em; color:/* PLACEHOLDER: desc-color */; line-height:1.6; max-width:160px; margin:0 auto;"><!-- PLACEHOLDER: step description --></p>
        </div>
        <!-- Step 3 -->
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:/* PLACEHOLDER: color-3 */; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px /* PLACEHOLDER: shadow-3 */;">3</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:/* PLACEHOLDER: title-color */;"><!-- PLACEHOLDER: step title --></h4>
          <p style="font-size:0.42em; color:/* PLACEHOLDER: desc-color */; line-height:1.6; max-width:160px; margin:0 auto;"><!-- PLACEHOLDER: step description --></p>
        </div>
        <!-- Step 4 (optional — remove if only 3 steps) -->
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:/* PLACEHOLDER: color-4 */; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px /* PLACEHOLDER: shadow-4 */;">4</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:/* PLACEHOLDER: title-color */;"><!-- PLACEHOLDER: step title --></h4>
          <p style="font-size:0.42em; color:/* PLACEHOLDER: desc-color */; line-height:1.6; max-width:160px; margin:0 auto;"><!-- PLACEHOLDER: step description --></p>
        </div>
      </div>
    </div>
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: note --></p>
</section>
```

## Usage Rules
- Use for linear process flows with 3-5 steps. 4 steps is ideal.
- Each step MUST have a numbered circle, a short title, and a brief description.
- **Do not use the old `.flow-diagram` / `.flow-node` / `.flow-arrow` CSS classes.** This layout is fully inline-styled.
- The entire flowchart is inline-styled — no theme CSS dependency for the flowchart structure.
- Adapt circle colors and shadows to match the active theme's accent palette.
- Adapt title/description text colors to match theme (dark bg = light text, light bg = dark text).
- Do not exceed 5 steps — split into multiple slides if more.
- `footer-note` MUST be placed **outside** the `flex:1` centering wrapper (see Positioning Rules).

## Theme Color Reference

When assembling, pick circle background colors and shadow colors from the active theme:

| Theme | Circle Colors (4-step) | Track BG | Title Color | Desc Color |
|-------|----------------------|----------|-------------|------------|
| apple-keynote | `#007aff, #5856d6, #34c759, #ff9500` | `#e8e8ed` | `#1d1d1f` | `#86868b` |
| glassmorphism | `#667eea, #764ba2, #43e97b, #4facfe` | `rgba(255,255,255,0.1)` | `#f7f9ff` | `#9fb3d9` |
| cyberpunk | `#00ffff, #ff00ff, #00ff88, #ffcc00` | `rgba(255,255,255,0.08)` | `#f0f0f0` | `#aaa` |
| gradient-story | `#fb923c, #f472b6, #a855f7, #38bdf8` | `rgba(255,255,255,0.15)` | `#fff` | `rgba(255,255,255,0.7)` |
| editorial | `#c0392b, #e74c3c, #d35400, #2c3e50` | `#e8e8ed` | `#2c3e50` | `#7f8c8d` |
| luxury-minimal | `#d4af37, #c49b2a, #b8860b, #daa520` | `rgba(212,175,55,0.15)` | `#f5f0e8` | `rgba(245,240,232,0.6)` |

Shadow format: `0 4px 16px rgba(R,G,B,0.25)` using the circle's color.

## Example: apple-keynote

```html
<section style="overflow:hidden;">
  <h2>Creation Workflow</h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div style="position:relative; width:90%; max-width:1100px; margin:0 auto;">
      <div style="position:absolute; top:44px; left:8%; right:8%; height:4px; background:#e8e8ed; border-radius:2px; z-index:0;"></div>
      <div style="position:absolute; top:44px; left:8%; right:8%; height:4px; background:linear-gradient(90deg,#007aff,#5856d6,#34c759,#ff9500); border-radius:2px; opacity:0.6; z-index:0;"></div>
      <div style="display:flex; justify-content:space-between; position:relative; z-index:1;">
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:#007aff; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px rgba(0,122,255,0.25);">1</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:#1d1d1f;">Define Scenario</h4>
          <p style="font-size:0.42em; color:#86868b; line-height:1.6; max-width:160px; margin:0 auto;">Identify the specific problem and target use case</p>
        </div>
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:#5856d6; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px rgba(88,86,214,0.25);">2</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:#1d1d1f;">Write SKILL.md</h4>
          <p style="font-size:0.42em; color:#86868b; line-height:1.6; max-width:160px; margin:0 auto;">Define triggers, workflow, tool calls and output format</p>
        </div>
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:#34c759; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px rgba(52,199,89,0.25);">3</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:#1d1d1f;">Test & Verify</h4>
          <p style="font-size:0.42em; color:#86868b; line-height:1.6; max-width:160px; margin:0 auto;">Multi-scenario trigger testing and quality optimization</p>
        </div>
        <div style="text-align:center; flex:1;">
          <div style="width:88px; height:88px; border-radius:50%; background:#ff9500; display:flex; align-items:center; justify-content:center; margin:0 auto; font-size:2rem; font-weight:800; color:#fff; box-shadow:0 4px 16px rgba(255,149,0,0.25);">4</div>
          <h4 style="margin:14px 0 6px; font-size:0.72em; font-weight:700; color:#1d1d1f;">Publish & Share</h4>
          <p style="font-size:0.42em; color:#86868b; line-height:1.6; max-width:160px; margin:0 auto;">Push to GitHub for team or community installation</p>
        </div>
      </div>
    </div>
  </div>
  <p class="footer-note">Start from real scenarios, build an MVP, then iterate on trigger accuracy and output quality.</p>
</section>
```

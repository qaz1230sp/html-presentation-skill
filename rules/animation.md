# Animation & Visual Dynamics

This file governs how animations, fragments, and visual effects are applied. Read it after `composition.md` and before writing HTML. Its purpose: make presentations feel alive, cinematic, and anti-generic — not like a default PowerPoint or AI-generated artifact.

## Core Philosophy: Animate Information, Not Decoration

The purpose of animation is not to "make things move" — it's to **help the audience understand the structure and relationships of information**. Every animation should answer one question: **What does this animation help the audience understand better?**

If the answer is "nothing, it just looks cool" — remove it.

---

## Three Principles

### Principle 1: Content Drives Animation, Not the Other Way Around

| Information Relationship | Recommended Effect | Anti-Pattern |
|--------------------------|-------------------|-------------|
| Progressive / Sequential | Slide in left-to-right, or rise bottom-to-top in sequence | All items fade-in simultaneously |
| Contrast / Conflict | Both sides enter from opposing directions, or one appears first then the other overrides | Both sides fade-in identically |
| Cause / Effect | A appears → connector / arrow draws → B appears | A and B fade-in together |
| Emphasis / Highlight | Scale pulse, background flash, border glow | Bold + underline |
| Aggregation / Summary | Scattered elements converge to center, or list items collapse into a summary | Jump straight to summary slide |
| Timeline / Process | Nodes light up along a track, connectors draw segment by segment | All nodes appear at once |

### Principle 2: Adjacent Slides Must Have Different Dominant Animations

Three consecutive slides using the same entrance style (e.g., all fade-up) = visual fatigue. **Adjacent slides must vary their dominant transition effect.**

Variation dimensions (pick at least one):
- Direction change (enter-left → enter-bottom → enter-right)
- Type change (slide → zoom → fade → flip)
- Tempo change (quick flash-in → slow float-in)

### Principle 3: Every Deck Must Have At Least One "Performance Animation"

A "performance animation" goes beyond simple appear/disappear — it **uses the animation itself to explain a concept**:
- Numbers rolling from 0 to target value
- Progress bar filling from empty to full
- Flowchart nodes lighting up and connecting in sequence
- Code lines highlighting with typewriter effect
- Comparison data visualized as a tilting scale/lever

Minimum **1** per deck. For 8+ slide decks, aim for **2-3**.

---

## Advanced Fragment Usage (reveal.js Native)

The basic `class="fragment"` is just fade-in. reveal.js supports these variants — **you must mix them**:

### Hiding Fragments (element starts invisible, appears on trigger)

These are the **primary** fragment types for revealing content step-by-step:

| Fragment Type | CSS Class | Best For |
|---------------|-----------|----------|
| Fade in | `fragment fade-in` | General supplementary info |
| Float up | `fragment fade-up` | Progressive list items |
| Slide from left | `fragment fade-left` | Right column in comparisons |
| Slide from right | `fragment fade-right` | Left column in comparisons |
| Zoom in | `fragment zoom-in` | Emphasizing key data |

### Non-hiding Fragments (element is already visible, appearance changes on trigger)

⚠️ **These do NOT hide the element initially.** Only use them on content that is already visible and you want to visually modify:

| Fragment Type | CSS Class | Behavior | Use Case |
|---------------|-----------|----------|----------|
| Highlight current | `fragment highlight-current-blue` | Adds blue tint to already-visible text | Walking through a visible list, highlighting the current item |
| Fade in then semi-out | `fragment fade-in-then-semi-out` | Fades in, then goes semi-transparent when next fragment triggers | Sequential focus where previous items should dim |
| Shrink out | `fragment shrink` | Shrinks the element | Deprecated / replaced option being visually de-emphasized |

**CRITICAL: Never use non-hiding fragments (`highlight-current-blue`, `shrink`) to reveal new content — the element will be visible from the start, breaking the reveal sequence.** Use `fade-in-then-semi-out` only when you intentionally want the dim-on-next behavior and understand the visual implications.

**Rule: When a slide has 2+ fragments, use at least 2 different hiding fragment types.**

**First-item-visible rule: For slides with multiple items (lists, cards, two-column), the first item must be visible on slide entry (no fragment class). Only item 2+ gets fragment classes.** This ensures the slide is never blank on entry — the audience immediately sees the topic content.

---

## Custom CSS Animation Toolbox

These animations can be defined directly in `<style>`. Trigger them with `data-fragment-index` and `.visible` state:

### Counter Roll
```css
@keyframes countUp {
  from { --num: 0; }
  to { --num: var(--target); }
}
.stat-num {
  animation: countUp 1.5s ease-out forwards;
  counter-reset: num var(--num);
  font-variant-numeric: tabular-nums;
}
.stat-num::after {
  content: counter(num);
}
```

### Stroke Draw
```css
@keyframes drawLine {
  to { stroke-dashoffset: 0; }
}
.draw-path {
  stroke-dasharray: var(--path-length);
  stroke-dashoffset: var(--path-length);
  animation: drawLine 1.2s ease-in-out forwards;
  animation-play-state: paused;
}
.fragment.visible .draw-path {
  animation-play-state: running;
}
```

### Bar Fill
```css
@keyframes fillBar {
  from { width: 0; }
  to { width: var(--fill-pct); }
}
.progress-fill {
  animation: fillBar 1s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  animation-play-state: paused;
}
.fragment.visible .progress-fill {
  animation-play-state: running;
}
```

### Typewriter

Basic inline typewriter effect for single-line text emphasis:

```css
@keyframes typing {
  from { width: 0; }
  to { width: 100%; }
}
.typewriter {
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid var(--accent-primary, #667eea);
  animation: typing 2s steps(var(--chars), end) forwards,
             blink 0.6s step-end infinite alternate;
  animation-play-state: paused;
  width: 0;
}
@keyframes blink {
  50% { border-color: transparent; }
}
.fragment.visible .typewriter {
  animation-play-state: running;
}
```

#### Terminal Typewriter

When the content is a CLI command or terminal interaction, use the full terminal component instead of the simple typewriter effect.
Complete terminal window templates, CSS, and usage rules are in `layouts/terminal-demo.md`.

Core techniques:
1. **Terminal chrome** — Rounded window + three-dot bar (macOS style)
2. **Character-by-character typing** — `width: 0 → Nch`, `steps(N, end)` matched to exact character count
3. **Block caret** — `background` color block + `step-end` blink (more realistic than `border-right`)
4. **Staggered output reveal** — `opacity: 0; translateY(14px)` + incremental `animation-delay`
5. **Side command cards** — Slide up from below, showing related commands

When to use terminal layout vs inline typewriter:
- **Terminal layout**: Full command + execution result scenarios (install, deploy, build)
- **Inline typewriter**: Single-line emphasis for titles or keywords

### Pulse Highlight
```css
@keyframes pulse {
  0%, 100% { transform: scale(1); box-shadow: 0 0 0 0 var(--accent-primary, rgba(102,126,234,0.4)); }
  50% { transform: scale(1.05); box-shadow: 0 0 0 12px transparent; }
}
.pulse-highlight {
  animation: pulse 1.5s ease-in-out 2;
}
```

---

## Slide Transition Variety

reveal.js supports per-slide transition overrides. **Using the same transition for the entire deck is prohibited.**

```html
<!-- Set on specific sections that need variation -->
<section data-transition="zoom">      <!-- Emphasis: key conclusions -->
<section data-transition="convex">    <!-- Spatial: architecture diagrams -->
<section data-transition="fade">      <!-- Calm: quotes / citations -->
<section data-transition="slide">     <!-- Default: narrative progression -->
<section data-transition="none">      <!-- Tight: code before/after comparisons -->
```

### Usage Rules

- Default to the config-specified transition (usually `slide`)
- **Emphasis slides** (conclusions, key quotes, critical data): use `zoom` or `convex`
- **Breathing slides** (quotes, full images): use `fade` for soft transitions
- **Comparison slides** (before/after side by side): use `none` to eliminate transition gap
- The same non-default transition must not appear more than 2 times consecutively

---

## Anti-Pattern Checklist

These are common visual fingerprints of AI-generated presentations — **all prohibited**:

### Animation Anti-Patterns
| ❌ Prohibited | ✅ Alternative |
|--------------|---------------|
| All elements use fade-in throughout | Choose animation type based on information relationship |
| All fragments use the same `fade-up` | Mix 2+ fragment types |
| Decorative perpetual breathing/pulse animations (no functional purpose) | Only pulse briefly when attention is needed |
| Same transition for the entire deck | Use different transitions on key slides for rhythm |
| All animation durations are round numbers (0.5s / 1s) | Use non-round values (0.3s / 0.7s / 1.2s) for natural feel |

### Visual Anti-Patterns
| ❌ Prohibited | ✅ Alternative |
|--------------|---------------|
| Purple-pink / blue-purple diagonal gradient backgrounds (heavy AI aesthetic) | Use theme-defined backgrounds |
| Decorative rounded cards with colored left border on every slide | Cards only in `card-grid` layout; borders use theme accent |
| Emoji as icons | Use inline SVG or plain text without icons |
| Gradient buttons with large pill-shaped corners | Flat buttons or ghost buttons |
| Same decorative element on every slide (e.g., dots in top-right) | Vary decoration by layout, or remove it |
| Fake data, fake logos, fake "XX million users" | Use placeholder notes marked "to be replaced" or real data |

---

## SVG & Visual Demos (Recommended Every 5 Slides)

For 8+ slide decks, pure text + charts becomes monotonous. Insert an **inline SVG or CSS visual demo** approximately every 5 slides:

### Applicable Scenarios

| Content Type | Recommended Visual Technique |
|-------------|------------------------------|
| Architecture / Process | SVG flowchart + stroke draw animation |
| Data Growth | Progress bar / bar chart CSS fill animation |
| Comparison Data | Scale / seesaw SVG + tilt animation |
| Timeline | Track + nodes lighting up sequentially |
| Code Execution | Terminal style + typewriter line-by-line reveal |
| Multiple Options | Card flip / accordion expand |

### Implementation Constraints

- SVG must be inlined (no external files)
- Set `width="100%"` with a `max-height` constraint
- Use CSS for animation control, not SMIL (better compatibility)
- Colors must reference theme CSS variables (e.g., `var(--accent-primary)`)

---

## Supplementary Checklist (extends quality-checklist.md)

After generation, additionally verify:

- [ ] Adjacent slides have different dominant animation / transition
- [ ] Same-slide 2+ fragments use at least 2 different types
- [ ] At least 1 "performance animation" (counter roll / stroke draw / bar fill / typewriter)
- [ ] No perpetual decorative animations (no `infinite` keyframes, except typewriter cursor)
- [ ] Animation durations use non-round values (0.3s / 0.7s / 1.2s) to avoid mechanical feel
- [ ] No AI visual fingerprints (no purple-pink gradients / emoji icons / fake data)
- [ ] 8+ slide deck has at least 1 inline SVG or CSS visual demo
- [ ] Per-slide transition has at least 2 different settings
- [ ] Fragment type selection matches information relationship (progressive → fade-up, contrast → fade-left/right)

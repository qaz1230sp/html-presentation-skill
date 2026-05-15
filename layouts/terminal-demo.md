# Terminal Demo / 终端演示页

Fragment count: 0 | Best for: CLI commands, install workflows, code execution demos, terminal interactions

This layout creates a **cinematic terminal window** with typewriter typing effect, blinking cursor, and staggered output reveal. Use it when the slide's core message is a CLI command and its result.

## Key Techniques

- **Typewriter**: `width: 0` → `width: Nch` via CSS `steps(N, end)` animation
- **Blinking caret**: `border-right` with step-end blink
- **Output reveal**: staggered `opacity` + `translateY` with incremental delays
- **Terminal chrome**: macOS-style dots bar for visual authenticity

## HTML Template

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="terminal-window">
      <div class="terminal-bar">
        <span class="terminal-dot"></span>
        <span class="terminal-dot"></span>
        <span class="terminal-dot"></span>
        <span class="terminal-path"><!-- PLACEHOLDER: optional path hint e.g. ~/projects --></span>
      </div>
      <div class="terminal-body">
        <div class="terminal-line terminal-line--cmd">
          <span class="terminal-prompt">$</span>
          <span class="terminal-typing" style="--chars:<!-- PLACEHOLDER: character count -->;"><!-- PLACEHOLDER: command text --></span>
          <span class="terminal-caret"></span>
        </div>
        <div class="terminal-line terminal-line--output terminal-line--d1"><!-- PLACEHOLDER: output line 1 --></div>
        <div class="terminal-line terminal-line--output terminal-line--d2"><!-- PLACEHOLDER: output line 2 --></div>
        <div class="terminal-line terminal-line--output terminal-line--d3"><!-- PLACEHOLDER: output line 3 --></div>
      </div>
    </div>
  </div>
  <p class="footer-note"><!-- PLACEHOLDER: optional note --></p>
</section>
```

## Variant: terminal + side cards (command reference)

Best for showing one command typing + related commands on the side.

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="terminal-layout">
      <div class="terminal-window">
        <div class="terminal-bar">
          <span class="terminal-dot"></span>
          <span class="terminal-dot"></span>
          <span class="terminal-dot"></span>
          <span class="terminal-path"><!-- PLACEHOLDER: path --></span>
        </div>
        <div class="terminal-body">
          <div class="terminal-line terminal-line--cmd">
            <span class="terminal-prompt">$</span>
            <span class="terminal-typing" style="--chars:<!-- PLACEHOLDER: char count -->;"><!-- PLACEHOLDER: command --></span>
            <span class="terminal-caret"></span>
          </div>
          <div class="terminal-line terminal-line--output terminal-line--d1"><!-- PLACEHOLDER: output 1 --></div>
          <div class="terminal-line terminal-line--output terminal-line--d2"><!-- PLACEHOLDER: output 2 --></div>
          <div class="terminal-line terminal-line--output terminal-line--d3"><!-- PLACEHOLDER: output 3 --></div>
        </div>
      </div>
      <div class="terminal-cards">
        <div class="terminal-card">
          <div class="terminal-card-cmd"><!-- PLACEHOLDER: cmd name --></div>
          <div class="terminal-card-desc"><!-- PLACEHOLDER: description --></div>
        </div>
        <div class="terminal-card">
          <div class="terminal-card-cmd"><!-- PLACEHOLDER: cmd name --></div>
          <div class="terminal-card-desc"><!-- PLACEHOLDER: description --></div>
        </div>
        <div class="terminal-card">
          <div class="terminal-card-cmd"><!-- PLACEHOLDER: cmd name --></div>
          <div class="terminal-card-desc"><!-- PLACEHOLDER: description --></div>
        </div>
      </div>
    </div>
  </div>
</section>
```

## Variant: multi-command sequence

For showing multiple commands typed in sequence.

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="terminal-window">
      <div class="terminal-bar">
        <span class="terminal-dot"></span>
        <span class="terminal-dot"></span>
        <span class="terminal-dot"></span>
      </div>
      <div class="terminal-body">
        <div class="terminal-line terminal-line--cmd">
          <span class="terminal-prompt">$</span>
          <span class="terminal-typing" style="--chars:<!-- CHAR_COUNT_1 -->;"><!-- COMMAND 1 --></span>
        </div>
        <div class="terminal-line terminal-line--output terminal-line--d1"><!-- OUTPUT 1 --></div>
        <div class="terminal-line terminal-line--cmd terminal-line--d2">
          <span class="terminal-prompt">$</span>
          <span class="terminal-typing terminal-typing--delayed" style="--chars:<!-- CHAR_COUNT_2 -->;"><!-- COMMAND 2 --></span>
        </div>
        <div class="terminal-line terminal-line--output terminal-line--d3"><!-- OUTPUT 2 --></div>
      </div>
    </div>
  </div>
</section>
```

## Required CSS

**Add this CSS block to the `<style>` section of any presentation that uses the terminal layout.** This works with all themes — colors reference CSS variables.

```css
/* ===== Terminal Demo Layout ===== */
.terminal-layout {
  display: grid;
  grid-template-columns: minmax(0, 1.3fr) 340px;
  gap: 28px;
  align-items: stretch;
}
.terminal-window {
  border-radius: 18px;
  overflow: hidden;
  border: 1px solid var(--glass-border, rgba(122,184,255,0.25));
  box-shadow: var(--glass-shadow, 0 18px 44px rgba(0,0,0,0.32));
  background: var(--glass-bg, rgba(18,28,52,0.58));
  backdrop-filter: var(--glass-blur, blur(10px));
  -webkit-backdrop-filter: var(--glass-blur, blur(10px));
}
.terminal-bar {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 16px 20px;
  border-bottom: 1px solid var(--glass-border, rgba(122,184,255,0.15));
}
.terminal-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: 2px solid var(--accent-primary, #667eea);
  background: rgba(102,126,234,0.18);
  animation: terminal-dot-pulse 1.8s ease-in-out infinite;
}
.terminal-dot:nth-child(2) { animation-delay: 0.18s; }
.terminal-dot:nth-child(3) { animation-delay: 0.36s; }
.terminal-path {
  margin-left: auto;
  font-size: 0.62em;
  letter-spacing: 0.1em;
  color: var(--r-muted-color, #9fb3d9);
  font-family: var(--r-code-font, monospace);
}
.terminal-body {
  padding: 28px 30px 34px;
  display: grid;
  gap: 14px;
  font-family: var(--r-code-font, monospace);
  font-size: 0.76em;
  color: var(--r-body-color, #d7e0f2);
}
.terminal-line { white-space: nowrap; }
.terminal-line--cmd {
  display: flex;
  align-items: center;
  gap: 14px;
}
.terminal-prompt {
  color: var(--r-muted-color, #9fb3d9);
  flex-shrink: 0;
}
.terminal-typing {
  overflow: hidden;
  width: 0;
  white-space: nowrap;
  color: var(--accent-primary, #667eea);
  animation: terminal-type 1.8s steps(var(--chars, 30), end) forwards;
}
.terminal-typing--delayed {
  animation-delay: 2.8s;
}
.terminal-caret {
  width: 10px;
  height: 1.15em;
  flex-shrink: 0;
  background: var(--accent-primary, #667eea);
  animation: terminal-caret-blink 0.82s step-end infinite;
}
.terminal-line--output {
  opacity: 0;
  transform: translateY(14px);
  animation: terminal-output-reveal 0.5s ease-out forwards;
  padding-left: 24px;
}
.terminal-line--d1 { animation-delay: 2.1s; }
.terminal-line--d2 { animation-delay: 2.6s; }
.terminal-line--d3 { animation-delay: 3.0s; }
.terminal-line--d4 { animation-delay: 3.4s; }

/* Side cards */
.terminal-cards {
  display: grid;
  gap: 16px;
  align-content: center;
}
.terminal-card {
  padding: 20px 22px;
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  background: var(--glass-bg, rgba(18,28,52,0.58));
  border: 1px solid var(--glass-border, rgba(122,184,255,0.25));
  box-shadow: var(--glass-shadow, 0 18px 44px rgba(0,0,0,0.32));
  backdrop-filter: var(--glass-blur, blur(10px));
  animation: terminal-card-rise 0.7s ease-out both;
}
.terminal-card:nth-child(1) { animation-delay: 0.4s; }
.terminal-card:nth-child(2) { animation-delay: 0.56s; }
.terminal-card:nth-child(3) { animation-delay: 0.72s; }
.terminal-card-cmd {
  font-family: var(--r-code-font, monospace);
  font-size: 0.82em;
  color: var(--accent-primary, #667eea);
  font-weight: 700;
}
.terminal-card-desc {
  font-size: 0.7em;
  color: var(--r-muted-color, #9fb3d9);
}

/* Keyframes */
@keyframes terminal-type {
  from { width: 0; }
  to { width: calc(var(--chars, 30) * 1ch); }
}
@keyframes terminal-caret-blink {
  0%, 49% { opacity: 1; }
  50%, 100% { opacity: 0; }
}
@keyframes terminal-output-reveal {
  from { opacity: 0; transform: translateY(14px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes terminal-card-rise {
  from { opacity: 0; transform: translateY(28px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes terminal-dot-pulse {
  0%, 100% { opacity: 0.45; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.15); }
}
```

## Usage Rules

- Use when the slide's **primary message is a command and its effect** — not for decorating arbitrary code.
- Keep command text to **one line** (under 50 characters ideally). Longer commands should be simplified or split.
- Output lines: **max 4 lines**. More than 4 means the content belongs in a `code-showcase` layout instead.
- The `--chars` CSS variable **must match the character count** of the command text for the typing animation to look correct.
- This layout counts as a "performance animation" per `rules/animation.md`.
- Do not use this layout on consecutive slides.
- Side cards variant works best with exactly **3 related commands**.
- All colors use CSS variable fallbacks, so the layout adapts to any theme automatically.

## Counting Characters for --chars

Count the **visible characters** in the command text (including spaces). Examples:
- `npx skill-hub install weekly-report` → `--chars: 37`
- `npm run build` → `--chars: 13`
- `docker compose up -d` → `--chars: 20`

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>命令行统一入口</h2>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <div class="terminal-layout">
      <div class="terminal-window">
        <div class="terminal-bar">
          <span class="terminal-dot"></span>
          <span class="terminal-dot"></span>
          <span class="terminal-dot"></span>
          <span class="terminal-path">~/workspace</span>
        </div>
        <div class="terminal-body">
          <div class="terminal-line terminal-line--cmd">
            <span class="terminal-prompt">$</span>
            <span class="terminal-typing" style="--chars: 37;">npx skill-hub install weekly-report</span>
            <span class="terminal-caret"></span>
          </div>
          <div class="terminal-line terminal-line--output terminal-line--d1">✓ Installing onenote-reader (dependency)</div>
          <div class="terminal-line terminal-line--output terminal-line--d2">✓ Installing weekly-report-skill</div>
          <div class="terminal-line terminal-line--output terminal-line--d3">Done. 2 skills installed.</div>
        </div>
      </div>
      <div class="terminal-cards">
        <div class="terminal-card">
          <div class="terminal-card-cmd">install-agent &lt;name&gt;</div>
          <div class="terminal-card-desc">安装 Custom Agent</div>
        </div>
        <div class="terminal-card">
          <div class="terminal-card-cmd">update --all</div>
          <div class="terminal-card-desc">全量更新现有能力</div>
        </div>
        <div class="terminal-card">
          <div class="terminal-card-cmd">list</div>
          <div class="terminal-card-desc">查看当前已安装列表</div>
        </div>
      </div>
    </div>
  </div>
</section>
```

# Navigation Sidebar Component

This component adds a collapsible slide navigation sidebar and a content area dimension indicator to every presentation.

## When to Include

Include this component in **every** generated presentation. Place the HTML before the `.reveal` div, the CSS inside the `<style>` block (after the theme CSS), and the JS after `Reveal.initialize()`.

## HTML

Place this markup **before** `<div class="reveal">`. Adjust the label to match the presentation language:

```html
<!-- Slide Navigation -->
<nav class="slide-nav" id="slideNav">
  <div class="slide-nav-header">
    <span>📑 <!-- "导航" for zh-CN / "Navigation" for en — MUST match presentation language --></span>
    <button class="slide-nav-close" onclick="toggleSlideNav()">✕</button>
  </div>
  <ul class="slide-nav-list" id="slideNavList"></ul>
</nav>
<button class="slide-nav-btn" id="slideNavBtn" onclick="toggleSlideNav()" title="<!-- '幻灯片导航' for zh-CN / 'Slide Navigation' for en -->">☰</button>
```

## CSS

Append this CSS **after** the theme CSS block inside `<style>`. The component auto-detects light/dark themes via JavaScript — no theme-specific overrides needed.

```css
/* ===== Navigation Sidebar ===== */
.slide-nav {
  position: fixed;
  left: 0;
  top: 0;
  width: 280px;
  height: 100%;
  z-index: 200;
  transform: translateX(-100%);
  transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  overflow-y: auto;
  overscroll-behavior: contain;
}
.slide-nav.open {
  transform: translateX(0);
}
.slide-nav-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 20px 14px;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}
.slide-nav-close {
  background: none;
  border: none;
  font-size: 18px;
  cursor: pointer;
  padding: 4px 8px;
  border-radius: 6px;
  transition: all 0.2s;
  line-height: 1;
}
.slide-nav-list {
  list-style: none;
  margin: 0;
  padding: 4px 0 20px;
}
.slide-nav-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 20px;
  cursor: pointer;
  transition: all 0.2s;
  font-size: 13px;
  line-height: 1.4;
  border-left: 3px solid transparent;
}
.slide-nav-num {
  min-width: 24px;
  height: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 6px;
  font-size: 11px;
  font-weight: 700;
  flex-shrink: 0;
}
.slide-nav-title {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.slide-nav-btn {
  position: fixed;
  left: 18px;
  bottom: 18px;
  z-index: 199;
  width: 42px;
  height: 42px;
  border-radius: 50%;
  border: none;
  font-size: 18px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.25s;
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}
.slide-nav-btn:hover {
  transform: scale(1.1);
}
```

## JavaScript

Place this script **after** `Reveal.initialize(...)`:

```js
/* ===== Navigation Sidebar Logic ===== */
(function () {
  // Auto-detect light vs dark theme
  function isLightTheme() {
    const el = document.querySelector('.reveal');
    if (!el) return false;
    const bg = getComputedStyle(el).backgroundColor;
    const m = bg.match(/rgba?\(\s*(\d+),\s*(\d+),\s*(\d+)/);
    if (!m) return false;
    return (parseInt(m[1]) * 299 + parseInt(m[2]) * 587 + parseInt(m[3]) * 114) / 1000 > 128;
  }

  function applyNavTheme() {
    const light = isLightTheme();
    const nav = document.getElementById('slideNav');
    const btn = document.getElementById('slideNavBtn');
    if (!nav) return;

    if (light) {
      nav.style.cssText += ';background:rgba(255,255,255,0.97);border-right:1px solid rgba(0,0,0,0.08);box-shadow:4px 0 24px rgba(0,0,0,0.08);color:#2c3e50;';
      nav.querySelectorAll('.slide-nav-header span, .slide-nav-header').forEach(e => e.style.color = '#1a1a1a');
      nav.querySelector('.slide-nav-close').style.color = '#95a5a6';
      if (btn) btn.style.cssText += ';background:rgba(255,255,255,0.92);color:#2c3e50;border:1px solid rgba(0,0,0,0.1);box-shadow:0 4px 16px rgba(0,0,0,0.08);';
      nav.dataset.theme = 'light';
    } else {
      nav.style.cssText += ';background:rgba(11,16,32,0.96);border-right:1px solid rgba(122,184,255,0.1);box-shadow:4px 0 24px rgba(0,0,0,0.3);color:#d7e0f2;';
      nav.querySelectorAll('.slide-nav-header span, .slide-nav-header').forEach(e => e.style.color = '#f7f9ff');
      nav.querySelector('.slide-nav-close').style.color = '#9fb3d9';
      if (btn) btn.style.cssText += ';background:rgba(11,16,32,0.85);color:rgba(215,224,242,0.8);border:1px solid rgba(122,184,255,0.15);box-shadow:0 4px 16px rgba(0,0,0,0.25);';
      nav.dataset.theme = 'dark';
    }
  }

  function styleNavItem(item, active, light) {
    if (active) {
      item.style.cssText = light
        ? 'background:rgba(192,57,43,0.08);color:#c0392b;border-left-color:#c0392b;font-weight:600;'
        : 'background:rgba(102,126,234,0.15);color:#667eea;border-left-color:#667eea;font-weight:600;';
      item.querySelector('.slide-nav-num').style.cssText = light
        ? 'background:#c0392b;color:#fff;'
        : 'background:#667eea;color:#fff;';
    } else {
      item.style.cssText = light
        ? 'color:#5d6d7e;border-left-color:transparent;font-weight:400;'
        : 'color:rgba(215,224,242,0.7);border-left-color:transparent;font-weight:400;';
      item.querySelector('.slide-nav-num').style.cssText = light
        ? 'background:rgba(0,0,0,0.06);color:#2c3e50;'
        : 'background:rgba(255,255,255,0.06);color:#d7e0f2;';
    }
  }

  function buildSlideNav() {
    var slides = document.querySelectorAll('.reveal .slides > section');
    var list = document.getElementById('slideNavList');
    if (!list) return;
    list.innerHTML = '';
    slides.forEach(function (slide, i) {
      var h = slide.querySelector('h1, h2, .hero-title');
      var title = h ? h.textContent.trim() : 'Slide ' + (i + 1);
      var li = document.createElement('li');
      li.className = 'slide-nav-item';
      li.dataset.index = i;
      li.innerHTML = '<span class="slide-nav-num">' + (i + 1) + '</span><span class="slide-nav-title">' + title + '</span>';
      li.addEventListener('click', function () {
        Reveal.slide(i);
        document.getElementById('slideNav').classList.remove('open');
      });
      list.appendChild(li);
    });
  }

  function updateSlideNavActive() {
    var idx = Reveal.getIndices().h;
    var nav = document.getElementById('slideNav');
    var light = nav && nav.dataset.theme === 'light';
    document.querySelectorAll('.slide-nav-item').forEach(function (item) {
      var isActive = parseInt(item.dataset.index) === idx;
      item.classList.toggle('active', isActive);
      styleNavItem(item, isActive, light);
    });
    var active = document.querySelector('.slide-nav-item.active');
    if (active) active.scrollIntoView({ block: 'nearest', behavior: 'smooth' });
  }

  window.toggleSlideNav = function () {
    document.getElementById('slideNav').classList.toggle('open');
  };

  document.addEventListener('keydown', function (e) {
    if (e.key === 'Escape') {
      document.getElementById('slideNav').classList.remove('open');
    }
  });

  Reveal.on('ready', function () {
    applyNavTheme();
    buildSlideNav();
    updateSlideNavActive();
  });
  Reveal.on('slidechanged', updateSlideNavActive);
})();
```

## Integration Notes

- The navigation sidebar auto-detects light vs dark themes by checking the `.reveal` element's computed background color brightness. No theme-specific configuration is needed.
- The content area info badge shows the reveal.js configured dimensions (width × height) and current slide position.
- Press **Escape** to close the sidebar.
- The sidebar uses `z-index: 200` which is above reveal.js controls (`z-index: 30`).
- All nav elements are outside `.reveal` to avoid interfering with slide transitions.

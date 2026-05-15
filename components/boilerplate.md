# HTML Boilerplate

Complete single-file HTML template for reveal.js presentations. Read `components/navigation.md` for the navigation sidebar component.

## Template

Use this complete HTML template. Replace placeholders only. The template includes a **collapsible navigation sidebar**.

```html
<!DOCTYPE html>
<html lang="<!-- LANGUAGE -->">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title><!-- TITLE --></title>
  <!-- reveal.js core CSS -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.css">
  <!-- Theme CSS (from theme file's CDN Links) -->
  <link rel="stylesheet" href="<!-- THEME_CDN_URL -->">
  <!-- Highlight.js theme (from theme file's CDN Links) -->
  <link rel="stylesheet" href="<!-- HIGHLIGHT_CDN_URL -->">
  <style>
    /* COPY ENTIRE CSS BLOCK FROM THEME FILE */

    /* COPY NAVIGATION CSS FROM components/navigation.md */
  </style>
</head>
<body>
  <!-- Slide Navigation (from components/navigation.md) — Use "Navigation" for English -->
  <nav class="slide-nav" id="slideNav">
    <div class="slide-nav-header">
      <span>📑 导航</span><!-- English: 📑 Navigation -->
      <button class="slide-nav-close" onclick="toggleSlideNav()">✕</button>
    </div>
    <ul class="slide-nav-list" id="slideNavList"></ul>
  </nav>
  <button class="slide-nav-btn" id="slideNavBtn" onclick="toggleSlideNav()" title="幻灯片导航">☰</button><!-- English: title="Slide Navigation" -->

  <div class="reveal">
    <div class="slides">
      <!-- ASSEMBLED SLIDES GO HERE -->
    </div>
  </div>

  <!-- reveal.js core -->
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/dist/reveal.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/reveal.js@5.1.0/plugin/highlight/highlight.min.js"></script>
  <!-- ECharts (only if charts are used) -->
  <script src="https://cdn.jsdelivr.net/npm/echarts@5/dist/echarts.min.js"></script>

  <script>
    Reveal.initialize({
      hash: true,
      transition: '<!-- TRANSITION: slide/fade/convex -->',
      plugins: [RevealHighlight],
      width: 1920,
      height: 1080,
      margin: 0.04,
      center: false, // keep false; CSS handles centering
      slideNumber: 'c/t',        // current/total format
      progress: true,             // progress bar at bottom
      showNotes: false,           // speaker notes hidden by default; press 'S' to open speaker view
    });

    // Chart initialization (only if charts are used)
    Reveal.on('slidechanged', event => {
      /* CHART_INIT_SCRIPTS */
    });
    // Also init charts on ready for first slide
    Reveal.on('ready', event => {
      /* CHART_INIT_SCRIPTS */
    });
    // Resize charts on window resize (only if charts are used)
    window.addEventListener('resize', function() {
      document.querySelectorAll('[id^="chart-"]').forEach(function(el) {
        var instance = echarts.getInstanceByDom(el);
        if (instance) instance.resize();
      });
    });

    /* COPY NAVIGATION JS FROM components/navigation.md */
  </script>
</body>
</html>
```

## Speaker Notes

Add speaker notes inside any `<section>` using `<aside class="notes">`:

```html
<section style="overflow:hidden;">
  <h2>Slide Title</h2>
  <p>Visible content</p>
  <aside class="notes">
    This text is only visible in speaker view (press S key).
    Use for talking points, timing cues, or reminders.
  </aside>
</section>
```

Notes are invisible during presentation. Press **S** to open the speaker view window which shows:
- Current slide
- Next slide preview
- Speaker notes
- Elapsed time

## PDF Export

To export the presentation as PDF:

1. Open the HTML file in Chrome/Edge
2. Append `?print-pdf` to the URL (e.g., `file:///path/to/slides.html?print-pdf`)
3. Use browser Print → Save as PDF
4. Set paper size to match slide ratio (landscape A4 for 16:9)

Note: Print layout may differ slightly from screen layout. Charts and animations are rendered as static.

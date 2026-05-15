# Timeline / 时间线页

Fragment count: max 3 | Best for: roadmaps, phased rollouts, and milestone storytelling

## HTML Template

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="timeline">
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker"><!-- PLACEHOLDER: year/step --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER: milestone title --></h4>
        <p><!-- PLACEHOLDER: description --></p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker"><!-- PLACEHOLDER: year/step --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER: milestone title --></h4>
        <p><!-- PLACEHOLDER: description --></p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker"><!-- PLACEHOLDER: year/step --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER: milestone title --></h4>
        <p><!-- PLACEHOLDER: description --></p>
      </div>
    </div>
  </div>
</section>
```

## Usage Rules
- Use for chronological sequences or stepwise transformations.
- Maximum 5 items total, but only the first 3 may use fragments.
- Keep each item to a short title plus one sentence of explanation.
- Prefer milestones that show progression, not disconnected facts.

## Variant: 5-item roadmap

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: section title --></h2>
  <div class="timeline">
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker"><!-- PLACEHOLDER --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER --></h4>
        <p><!-- PLACEHOLDER --></p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker"><!-- PLACEHOLDER --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER --></h4>
        <p><!-- PLACEHOLDER --></p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker"><!-- PLACEHOLDER --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER --></h4>
        <p><!-- PLACEHOLDER --></p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-marker"><!-- PLACEHOLDER --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER --></h4>
        <p><!-- PLACEHOLDER --></p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-marker"><!-- PLACEHOLDER --></div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER --></h4>
        <p><!-- PLACEHOLDER --></p>
      </div>
    </div>
  </div>
</section>
```

## Variant: release milestones

```html
<section style="overflow:hidden;">
  <h2><!-- PLACEHOLDER: release title --></h2>
  <div class="timeline">
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker">A</div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER: alpha milestone --></h4>
        <p><!-- PLACEHOLDER: alpha summary --></p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker">B</div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER: beta milestone --></h4>
        <p><!-- PLACEHOLDER: beta summary --></p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker">G</div>
      <div class="timeline-content">
        <h4><!-- PLACEHOLDER: GA milestone --></h4>
        <p><!-- PLACEHOLDER: GA summary --></p>
      </div>
    </div>
  </div>
</section>
```

## Example: glassmorphism

```html
<section style="overflow:hidden;">
  <h2>Skill Packaging Roadmap</h2>
  <div class="timeline">
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker">1</div>
      <div class="timeline-content">
        <h4>Define Themes</h4>
        <p>Create reusable visual systems with stable class contracts.</p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker">2</div>
      <div class="timeline-content">
        <h4>Add Layout References</h4>
        <p>Give the agent concrete HTML shells for common slide types.</p>
      </div>
    </div>
    <div class="timeline-item fragment fade-up">
      <div class="timeline-marker">3</div>
      <div class="timeline-content">
        <h4>Generate Decks</h4>
        <p>Compose outlines, select layouts, and fill placeholders automatically.</p>
      </div>
    </div>
  </div>
</section>
```

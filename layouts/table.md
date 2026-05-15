# Table Layout

Data table with styled headers and alternating rows. Best for structured data, feature matrices, spec sheets.

## Template

### Standard Table
```html
<section style="overflow:hidden;">
  <h2><!-- TITLE --></h2>
  <p class="subtitle"><!-- DESCRIPTION --></p>
  <div style="flex:1; display:flex; flex-direction:column; justify-content:center;">
    <table class="styled-table">
      <thead>
        <tr>
          <th><!-- COL1 --></th>
          <th><!-- COL2 --></th>
          <th><!-- COL3 --></th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><!-- DATA --></td>
          <td><!-- DATA --></td>
          <td><!-- DATA --></td>
        </tr>
        <!-- MORE ROWS -->
      </tbody>
    </table>
  </div>
  <p class="footer-note"><!-- SOURCE --></p>
</section>
```

## Notes
- Use `.styled-table` class for consistent styling across themes
- Keep columns ≤ 6 for readability at presentation scale
- Table is wrapped in flex centering div for vertical centering
- Each theme defines `.styled-table` styling (glassmorphism uses glass effect headers, editorial uses accent-colored headers, etc.)

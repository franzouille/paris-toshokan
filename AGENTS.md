# Paris Bibliothèques UX Launcher

## Goal
Build a small, modern, responsive single-file HTML launcher that generates deep links to https://bibliotheques.paris.fr searches with pre-applied filters (preset libraries + document types).

This is a static page (no build step), meant to be opened on iOS Safari and desktop browsers. It should work offline once loaded. No external dependencies.

## Current state
We already have a working single-file HTML prototype that:
- lets the user type a query
- choose a preset (initially: 75013 Italie + Jean-Pierre Melville + Virginia Woolf)
- choose document types (BD + Livre, both pre-checked)
- opens the generated search either in the same tab or a new tab
- remembers last preset + type selections in localStorage
- uses a modern responsive UI

## Target behaviors (must-have)
1. Presets
   - Provide a dropdown to select a preset.
   - Initial preset: 3 libraries:
     - "75013 - Italie"
     - "75013 - Jean-Pierre Melville"
     - "75013 - Virginia Woolf"
   - It must be easy to add more presets later (data in a single PRESETS array).

2. Types (facets)
   - Two checkboxes: "Livre" and "BD"
   - Both checked by default
   - If none checked, fallback to both.

3. URL generation
   - Generate an URL of form:
     https://bibliotheques.paris.fr/search.aspx#/Search/(query:(...FacetFilter:'<ENCODED_JSON>'...,QueryString:'<ENC_Q>'...,SearchTerms:'<ENC_Q>'...),sst:4)
   - FacetFilter JSON must include:
     - "_587": "<libraries joined by ||>"
     - "_586": "<types joined by ||>"
   - Then URL-encode the JSON string and inject it into FacetFilter:'...'

4. UX
   - Responsive, modern, clean, minimal copy.
   - Search input with Enter to open "here".
   - Buttons:
     - "Ouvrir ici"
     - "Nouvel onglet" (use window.open with noopener,noreferrer)
     - "Effacer"
   - Small hint text can show the current query and selected types, but keep the page minimal.

5. Persistence
   - Persist selected preset id and types (BD/Livre) in localStorage.
   - Do not persist the search query by default (optional later).

## Non-goals
- No extension code yet (Chrome/Safari extension is a future phase).
- No network calls.
- No external CSS/JS libs.

## Files
- Single deliverable: `bib-paris.html` (or `index.html`).
- Keep everything in one file for easy iCloud Drive usage.

## Coding style
- Plain HTML/CSS/JS.
- Use clear function names.
- Avoid overengineering.
- Keep the code readable and commented where it matters.

## Acceptance checklist
- Opening the page on iOS Safari works.
- Selecting preset + types produces valid URLs that keep filters.
- Both buttons work on desktop; on iOS, new tab is best-effort.
- Page looks good on small screens and desktop.


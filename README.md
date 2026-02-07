# Paris Toshokan

Single-file HTML launcher for deep-link searches on `https://bibliotheques.paris.fr` with Syracuse facet filters.

## Current behavior
- Single static file app: `index.html`
- Canonical Paris libraries dataset in code (from `DATA_LIBRARIES.md`)
- Search input (`Enter` opens in current tab)
- Arrondissement-based selection model:
  - chips `75000..75020` with `off/on/partial` states
  - global actions:
    - `Tous les arrondissements`
    - `Réinitialiser`
- `Bibliothèques sélectionnées` shown as removable chips (`×`)
- `Ajouter des bibliothèques` suggestions:
  - only libraries not already selected
  - scoped to currently active arrondissements
- Document types:
  - `Livre`
  - `BD`
  - fallback to both if both unchecked
- Actions:
  - `Ouvrir ici`
  - `Ouvrir dans un nouvel onglet`
- Theme mode:
  - `Auto`
  - `Light`
  - `Dark`

## Persistence (`localStorage`)
Stored in a single settings object:
- `selectedLibraries: string[]`
- `documentTypes: { book: boolean, bd: boolean }`
- `theme: "auto" | "light" | "dark"`

First load only (when no stored selection):
- `75013 - Italie`
- `75013 - Jean-Pierre Melville`
- `75013 - Virginia Woolf`

## URL generation
Generated URL targets Syracuse search with:
- `_587 = selectedLibraries.join("||")`
- `_586 = selected types join("||")`

Fallbacks:
- if `selectedLibraries` is empty: use all libraries
- if no types are checked: use `Livre + BD`

## Usage
1. Open `index.html` in Safari, Chrome, or Firefox.
2. Type a query.
3. Adjust arrondissement / libraries / types.
4. Open search in current or new tab.

## iOS quick setup
1. Save `index.html` in iCloud Drive.
2. Open in Safari.
3. Share -> Add to Home Screen.

## Development
- No build step
- No external dependencies
- Edit `index.html` directly

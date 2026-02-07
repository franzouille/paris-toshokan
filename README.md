# Paris Toshokan

Minimal single-file HTML launcher for filtered searches on `https://bibliotheques.paris.fr`.

## Features
- Single static file: `index.html`
- Query input + `Enter` opens in current tab
- Preset selector (defined in `PRESETS`)
- Document type filters: `Livre` and `BD`
- Safety fallback: if both types are unchecked, URL still uses both
- Actions:
  - `Ouvrir ici`
  - `Nouvel onglet`
  - `Effacer`
- Local persistence (`localStorage`) for:
  - selected preset
  - selected types
  - theme mode (`Auto`, `Light`, `Dark`)

## Usage
1. Open `index.html` in Safari, Chrome, or Firefox.
2. Type a query.
3. Select preset and document types.
4. Open the generated search.

## iOS Quick Setup
1. Save `index.html` in iCloud Drive.
2. Open it in Safari.
3. Tap Share -> Add to Home Screen.

## Development
- No build step
- No external dependencies
- Edit `index.html` directly

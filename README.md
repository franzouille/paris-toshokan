# Paris Toshokan

🔎 Search Paris public libraries faster, by arrondissement and library — without fighting the official UI.

🌐 Live: https://franzouille.github.io/paris-toshokan/

---

## What is Paris Toshokan?

Paris Toshokan is a lightweight, single-file web app that makes it easy to search the **Paris public libraries catalogue** with precise control over:

- Arrondissements
- Individual libraries
- Document types (Livre / BD)

It generates a clean, pre-filtered search and opens the results directly on  
**bibliotheques.paris.fr**, without forcing you to navigate their complex interface.

Think of it as a **fast, human-friendly launcher** for the official catalogue.

---

## Why it exists

The official Paris libraries website is powerful but:
- hard to filter by multiple libraries
- slow to reconfigure repeatedly
- unfriendly on mobile

Paris Toshokan focuses on one thing only:
> **Get to relevant results as fast as possible.**

---

## Features

- 🔍 Free-text search (title, author, series, etc.)
- 🗺️ Multi-select by arrondissement
- 📚 Fine-grained library selection
- 🧠 Smart defaults (remembers your choices)
- 🌓 Light / Dark / System theme
- 📱 Mobile-first, installable on iOS (Add to Home Screen)
- ⚡ Single `index.html`, no build, no backend

---

## How it works

- All logic runs client-side
- No data is scraped or duplicated
- The app only **builds URLs** compatible with the official Paris libraries catalogue (Syracuse)
- Searches always open on the official website

Paris Toshokan is a **UI and UX layer**, not a replacement.

---

## Usage

1. Open: https://franzouille.github.io/paris-toshokan/
2. Enter a search term (e.g. *homo sapiens tome 2*, *tardi*, *corto maltese*)
3. Select one or more arrondissements and libraries
4. Click **Ouvrir ici** or **Nouvel onglet**

On iOS:
- Open in Safari
- Share → *Add to Home Screen*  
→ it behaves like a native app

---

## Tech stack

- Plain HTML / CSS / JavaScript
- No framework
- No dependencies
- No build step
- GitHub Pages hosting

---

## Project status

This is a **personal utility project**, built for real daily use.  
The scope is intentionally limited and focused.

Suggestions and improvements are welcome if they respect the core simplicity.

---

## License

MIT

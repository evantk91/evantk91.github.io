# Evan Greer — Portfolio

A single-page personal portfolio site. Built with plain, static HTML, CSS, and vanilla JavaScript — no build step, package manager, bundler, framework, or test suite.

**Live site:** https://evantk91.github.io/

## Running locally

Open `index.html` directly in a browser, or serve the directory:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

Edit an HTML/CSS/JS file and refresh — that's the whole feedback loop.

## Structure

- `index.html` — the page: hero, about, experience, projects, contact sections plus a footer
- `style.css` — single stylesheet with a design-token system (colors, spacing, gradient in `:root`)
- `script.js` — hamburger nav toggle, scroll effects, reveal animations, scroll-spy
- `assets/` — headshot, social icons, and résumé PDF

## Deployment

Deployed via GitHub Pages from the `main` branch. Pushing to `main` redeploys automatically.

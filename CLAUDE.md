# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A single-page personal portfolio for Evan Greer — a modern, dark-themed site built with plain, static **HTML, CSS, and vanilla JavaScript**. No build step, package manager, bundler, framework, or test suite; files are served as-is. Content is drawn from Evan's résumé (`assets/resume.pdf`). Deployed via **GitHub Pages** from `main` at https://evantk91.github.io/.

## Running / developing

Open `index.html` directly, or serve the directory:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

Edit an HTML/CSS/JS file and refresh — that's the whole feedback loop. Nothing to build, lint, or test. Pushing to `main` redeploys Pages automatically.

## Architecture

One page (`index.html`) of anchor-linked `<section>`s: `#hero`, `#about`, `#experience`, `#projects`, `#contact`, plus a footer. Three files only: `index.html`, `style.css`, `script.js`.

Conventions:

- **Single stylesheet with a design-token system.** All colors, spacing, radii, and the accent gradient live in `:root` custom properties at the top of `style.css` (`--accent-1`, `--accent-2`, `--grad`, `--surface`, `--border`, etc.). Change the theme there, not in individual rules. Responsive overrides are media queries at the **bottom** of the same file (breakpoints at 900px and 720px) — keep them there.
- **One nav, not two.** A single `.nav` collapses into a hamburger below 720px via the `.nav__links.open` class toggled in `script.js`. (This replaces the old two-navbar template.)
- **BEM-ish naming.** `block__element--modifier` (e.g. `hero__title`, `stat-card__num`, `btn--primary`). Reuse existing names.
- **`script.js` handles four things:** hamburger toggle, `scrolled` state on the nav, `.reveal` scroll-in animations (IntersectionObserver), and active-link scroll-spy. Elements opt into the entrance animation by carrying the `reveal` class.

## Content notes

- The **Projects** section frames Evan's real Iterable work (Embedded Messaging, European Data Center, Anonymous User Activation) rather than using placeholder cards or images. Update titles/links as real repos become available.
- Experience skills mirror the résumé's skills matrix; "Expert" skills get the `chip--expert` modifier.
- No photos beyond the hero headshot (`assets/headshot_circle.png`) — the About and Projects sections are intentionally image-free.
- Only 5 assets are used: `headshot_circle.png`, `linkedin.png`, `github.png`, `email.png`, `resume.pdf`. Don't re-add the removed template images/icons.

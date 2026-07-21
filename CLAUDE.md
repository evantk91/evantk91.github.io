# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A single-page personal portfolio website for Evan Greer, built with plain, static **HTML, CSS, and vanilla JavaScript**. There is no build step, package manager, bundler, framework, or test suite — the files are served as-is. Content is drawn from Evan's resume (`assets/resume.pdf`). The visual style and conventions follow the sibling `personal-portfolio-july-26` project.

## Running / developing

Open `index.html` directly in a browser, or serve the directory with any static server, e.g.:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

Editing an HTML/CSS/JS file and refreshing the browser is the entire feedback loop. There are no commands to build, lint, or test.

## Architecture

The whole site is one page (`index.html`) composed of anchor-linked `<section>`s (`#profile`, `#about`, `#experience`, `#projects`, `#contact`) plus a `<footer>`, which the nav scrolls to via `scroll-behavior: smooth`.

Conventions worth knowing before editing:

- **Two parallel navbars.** `#desktop-nav` and `#hamburger-nav` both exist in the markup. `mediaqueries.css` hides the desktop nav and shows the hamburger nav below the **1200px** breakpoint. Any nav change (links, logo) must be made in *both* navs — and the footer nav — to stay consistent.
- **Stylesheets are split by purpose.** `style.css` holds all base/desktop styles; `mediaqueries.css` holds *only* responsive overrides (breakpoints at 1400px, 1200px, 600px). Keep breakpoint rules out of `style.css`.
- **BEM-ish class naming.** Classes like `section__text__p1`, `section__pic-container` follow a `block__element` pattern; reuse the existing names rather than inventing parallel ones.
- **Behavior is inline + one script.** Interactivity uses inline `onclick=` attributes in the HTML (navigation, socials, resume download) plus `script.js`, which only defines `toggleMenu()` to open/close the hamburger menu.

## Content notes

- The **Projects** section currently uses placeholder cards (Project One/Two/Three) with the reference images and GitHub/Live-Demo buttons pointing at the GitHub profile. Swap in real projects, images, and links when available.
- Experience skills mirror the resume's skills matrix (Android/iOS/React Native/SDK expert; Kotlin/Swift experienced; etc.).
- The "Download Resume" button opens `assets/resume.pdf`.

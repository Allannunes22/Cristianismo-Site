---
name: testing-cristianismo-site
description: Test the Cristianismo Site static HTML site end-to-end. Use when verifying site rendering, layout, or deployment fixes.
---

## Overview
This is a single-file static HTML site (`index.html`) deployed via GitHub Pages and Vercel. The site is a portal about Christianity with articles, courses, devotionals, and news.

## Local Testing

### Start a local HTTP server
```bash
cd /home/ubuntu/repos/Cristianismo-Site
python3 -m http.server 8080
```

Then open `http://localhost:8080/` in the browser.

### Why use an HTTP server instead of `file://`
Using `python3 -m http.server` simulates real deployment behavior — it serves `index.html` at the root path `/`, just like GitHub Pages and Vercel do. This lets you verify that the file is correctly named `index.html` (a common source of 404 errors).

### Key assertions to verify
- **Tab title**: "Cristianismo — Portal de Fé e Conhecimento"
- **Hero section**: Visible with blue/gold gradient, title "CRISTIANISMO"
- **Stats**: 4 stat boxes — 959 artigos, 378 cursos, 2738 módulos, 511 notícias
- **Toolbar**: Tabs for Artigos, Cursos, Devocionais, Notícias
- **Content cards**: Should render below toolbar with article/course content

## Vercel Preview
Vercel preview deployments might require Vercel authentication. If blocked by a login wall, test locally instead. The Vercel preview URL pattern is:
```
cristianismo-site-git-<branch>-allannunes22s-projects.vercel.app
```

## GitHub Pages
Production URL: `https://allannunes22.github.io/Cristianismo-Site/`

## Common Issues
- **404 on deployment**: Usually caused by the HTML file not being named `index.html`. GitHub Pages and Vercel require `index.html` at the repo root.
- **Styling issues**: The site uses CSS custom properties with light/dark mode via `prefers-color-scheme`. Test both if possible.

## Devin Secrets Needed
No secrets are required for local testing. Vercel preview access may require Vercel credentials if the deployment has authentication protection enabled.

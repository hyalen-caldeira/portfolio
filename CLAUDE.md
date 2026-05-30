# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS/JavaScript portfolio website - a personal professional portfolio and resume site with no build process or backend dependencies.

## Tech Stack

- HTML5, CSS3, vanilla JavaScript
- Bootstrap 3.0.3 (responsive grid and components)
- jQuery 1.10.2 with jQuery Easing plugin
- Font Awesome 4.0.3 for icons
- All dependencies loaded via CDN
- Hosted on AWS S3/CloudFront

## Local Development

```bash
python3 -m http.server 8000
```

No build, lint, or test commands exist - this is a pure static site.

## Architecture

Single-page application with five anchor sections: `#portfolio`, `#about`, `#certificate`, `#contact`, `#footer`. The navbar uses Bootstrap's scroll-spy (`data-spy="scroll"`) and collapses at >50px scroll via `js/grayscale.js`.

**Key Files:**
- `index.html` - All content: sections, portfolio modals, and all inline `<script>` blocks
- `css/style.css` - Custom styles, utility classes, animations
- `js/grayscale.js` - Navbar collapse on scroll, smooth scrolling via jQuery Easing, avatar bounce animation

**Portfolio modals** are Bootstrap modals defined at the bottom of `index.html` with IDs `portfolioModal1`–`portfolioModal6`. Grid items link to them via `data-toggle="modal"`. Current slot mapping: `1` Portfolio Site, `2` DocWise (RAG), `3` iFlow XML Parser (SAP CAP + GenAI), `4` Online Resume, `5` COBOL AI Platform (flagship), `6` MCP Infra AWS (Terragrunt).

**Inline scripts in `index.html`** (not in `grayscale.js`):
- Hero `#animazione` fade-in on load
- Footer `#animazione-footer` fade-in on scroll-to-bottom
- `#about` section avatar (`.fade2` / `.ball`) fade-in triggered 300px before section enters viewport

**CSS Patterns:**
- Spacing utilities: `.top20`, `.top30`, `.top40`, `.top100`
- Accent color: `.rosso` (#e74c3c)
- Social button colors: `.facebook-color`, `.linkedin-color`, `.github-color`
- Avatar bounce: `.ball.animate` class added via JS after fade-in; keyframe defined in `css/style.css`
- `.under-construction` class on portfolio grid images that have no linked modal yet

## Deployment

Static files deploy directly to AWS S3/CloudFront. No transpilation or bundling required.

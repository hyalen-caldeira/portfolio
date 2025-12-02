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
- Hosted on AWS

## Local Development

```bash
# Serve locally (pick one)
python3 -m http.server 8000
npx http-server
open index.html  # direct file opening
```

No build, lint, or test commands exist - this is a pure static site.

## Architecture

Single-page application pattern with sections:
- Fixed navbar with dynamic collapse on scroll (>50px)
- Hero section with intro animations
- Portfolio grid (3-column Bootstrap layout) with modal dialogs for project details
- About, Certificates, and Contact sections
- Smooth scrolling between sections via jQuery click handlers

**Key Files:**
- `index.html` - All HTML content including 4 portfolio modals
- `css/style.css` - Custom styles, utility classes (`.top20`, `.top30`, etc.), animations
- `js/grayscale.js` - Navbar scroll effect, smooth scrolling, page animations
- `js/jquery.scrolly.js` - Additional scroll effects

**CSS Patterns:**
- Utility classes for spacing: `.top20`, `.top30`, `.top40`, `.top100`
- Accent color: `.rosso` (#e74c3c)
- Social button colors: `.facebook-color`, `.linkedin-color`, `.github-color`
- CSS keyframe animations for bounce effects

## Deployment

Static files deploy directly to AWS S3/CloudFront. No transpilation or bundling required.

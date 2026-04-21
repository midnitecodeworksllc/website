# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Midnite Codeworks** is a single-page marketing website for a software development agency. The entire site is contained in one file (`index.html`) with embedded CSS and JavaScript — no build process, no package manager, no framework.

## Architecture

`index.html` (74KB, ~1922 lines) has three logical sections:

1. **CSS** (lines 11–1111): Custom properties in `:root` define the color palette (dark theme: cyan `#00f5ff`, purple `#9d4edd`, magenta `#f72585`, blue `#4361ee`). Layout uses Grid/Flexbox. Media query breakpoints at 1024px, 768px, 480px. Scroll-reveal animations use `.reveal` / `.visible` classes driven by IntersectionObserver.

2. **HTML** (lines ~1112–1723): Sections keyed by ID — `#nav`, `#hero`, `#about`, `#services`, `#work`, `#why`, `#testimonials`, `#team`, `#contact`, footer.

3. **JavaScript** (lines 1724–1919): Canvas particle animation in hero, sticky nav, mobile hamburger menu, IntersectionObserver-based scroll reveals, client-side contact form feedback (no backend), smooth anchor scrolling with 80px nav offset.

## Development

No build step — open `index.html` directly in a browser or serve with any static file server:

```bash
python3 -m http.server 8080
```

Changes to CSS, HTML, or JS take effect on page reload. No linting is configured; use browser DevTools for JS errors.

## Key Constraints

- **No backend**: The contact form is client-side only (shows a success message, resets after 3.5s). Real submission requires adding a backend or form service.
- **Vanilla only**: No frameworks. Use standard DOM APIs for any JS additions.
- **Canvas particle animation** recomputes particle count (40–80) and rerenders on resize via `requestAnimationFrame`.

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Midnite Codeworks** is a single-page marketing website targeting US-based small and medium-sized businesses (SMBs). It positions Midnite as a custom-software firm that also does AI — websites, SaaS, internal management tools, and AI automation — not an AI-only shop or a generic dev agency. The entire site is contained in `index.html` with embedded CSS and JavaScript — no build process, no package manager, no framework.

## Real Content (do not replace with placeholders)

- **Team** (3 people only):
  - Gabriel Volheim — Co-Founder, Engineering & Systems
  - Joshua Smith — Co-Founder, Data & Integration
  - Harrison Seay — Marketing & Growth
- **Email**: midnitecodeworksllc@gmail.com
- **Booking link**: https://cal.com/midnite-codeworks-pzscip
- **Form**: POSTs to formsubmit.co with real email — native HTML form, no JS handler
- **Services — Custom Software & Development**: Custom Websites, SaaS & Web Applications, Internal Management Tools, Backend Systems & APIs, Tool Integrations, Code Audits & Modernization
- **Services — AI Solutions**: Agentic AI Deployment, Custom AI Data Training, Private LLM Integration, AI Workflow Automation, AI Ops & Ongoing Support
- **Industries**: Healthcare, Legal, Real Estate, Finance & Accounting, E-Commerce, Any Privacy-Conscious SMB
- **Stats**: 10hr+/week saved, 100% data privacy, 48hr prototype, $0 vendor lock-in — all real/defensible claims

## Architecture

`index.html` (~2,260 lines) has three logical sections:

1. **`<head>`** (lines 1–44): Meta tags, Open Graph, Twitter Card, JSON-LD `ProfessionalService` schema (local SEO for South Carolina), Google Fonts preconnect (Inter + Space Grotesk).

2. **CSS** (lines 45–1368, inside `<style>`): Custom properties in `:root` define the color palette (dark theme: cyan `#00f5ff`, purple `#9d4edd`, magenta `#f72585`, blue `#4361ee`). Layout uses Grid/Flexbox. Breakpoints at 1024px, 768px, 480px. Scroll-reveal animations use `.reveal` / `.visible` driven by IntersectionObserver.

3. **HTML body** (lines ~1385–2078): Sections in order — `#nav`, `#hero`, `#about`, `#services`, `#work` (Industries), `#why`, `#testimonials` (How It Works process), `#team`, `#products` (EdTech SaaS teaser), `#contact`, `<footer>`.

4. **JavaScript** (lines 2080–2259, inside `<script>`): Canvas particle animation, sticky nav, mobile hamburger, IntersectionObserver scroll reveals, smooth anchor scrolling with 80px nav offset.

## Development

No build step — open `index.html` directly in a browser or serve with any static file server:

```bash
python3 -m http.server 8080
```

## Key Constraints

- **No fake content**: Do not add fictitious clients, testimonials, portfolio projects, or team members. The site intentionally uses an "Industries" section instead of a fake portfolio.
- **Form**: Uses formsubmit.co via native HTML POST — no JS override needed. Submissions go to midnitecodeworksllc@gmail.com.
- **Vanilla only**: No frameworks. Standard DOM APIs only.

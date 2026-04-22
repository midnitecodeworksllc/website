# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Midnite Codeworks** is a single-page marketing website targeting US-based small and medium-sized businesses (SMBs). It positions Midnite as an AI automation company — not a generic dev agency. The entire site is contained in `index.html` with embedded CSS and JavaScript — no build process, no package manager, no framework.

## Real Content (do not replace with placeholders)

- **Team**: Gabriel Volheim (Co-Founder, Agentic AI & Systems) and Joshua Smith (Co-Founder, AI Data Training & Integration) — 2 people only
- **Email**: midnitecodeworksllc@gmail.com
- **Booking link**: https://cal.com/midnite-codeworks-pzscip
- **Form**: POSTs to formsubmit.co with real email — native HTML form, no JS handler
- **Services**: Agentic AI Deployment, Custom AI Data Training, Private LLM Integration, AI Workflow Automation, AI Ops & Ongoing Support, AI Readiness Assessment
- **Industries**: Healthcare, Legal, Real Estate, Finance & Accounting, E-Commerce, Any Privacy-Conscious SMB
- **Stats**: 10hr+/week saved, 100% data privacy, 48hr prototype, $0 vendor lock-in — all real/defensible claims

## Architecture

`index.html` has three logical sections:

1. **CSS** (lines 11–1120): Custom properties in `:root` define the color palette (dark theme: cyan `#00f5ff`, purple `#9d4edd`, magenta `#f72585`, blue `#4361ee`). Layout uses Grid/Flexbox. Breakpoints at 1024px, 768px, 480px. Scroll-reveal animations use `.reveal` / `.visible` driven by IntersectionObserver.

2. **HTML** (lines ~1121–1720): Sections — `#nav`, `#hero`, `#about`, `#services`, `#work` (Industries), `#why`, `#testimonials` (How It Works process), `#team`, `#contact`, footer.

3. **JavaScript** (lines ~1721–end): Canvas particle animation, sticky nav, mobile hamburger, IntersectionObserver scroll reveals, smooth anchor scrolling with 80px nav offset.

## Development

No build step — open `index.html` directly in a browser or serve with any static file server:

```bash
python3 -m http.server 8080
```

## Key Constraints

- **No fake content**: Do not add fictitious clients, testimonials, portfolio projects, or team members. The site intentionally uses an "Industries" section instead of a fake portfolio.
- **Form**: Uses formsubmit.co via native HTML POST — no JS override needed. Submissions go to midnitecodeworksllc@gmail.com.
- **Vanilla only**: No frameworks. Standard DOM APIs only.

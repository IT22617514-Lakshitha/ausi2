# Project Overview
- Purpose: static marketing site for **NSN Property Cleaning** in Melbourne.
- Main architecture: single-page static site in `index.html` with inline CSS and inline JavaScript.
- Core technologies: HTML5, CSS3, vanilla JavaScript, Google Fonts, AOS animations, Lucide icons, Vercel static hosting.

# Repository Structure
- `index.html`: full page markup, styles, behavior, SEO metadata, JSON-LD, forms, and UI sections.
- `assets/images/`: generated/curated service imagery used across the page.
- `assets/images/real-results/`: on-site photos used in the "Realistic Results" gallery.
- `assets/brand/`: brand assets, including current NSN SVG logo files and older SNS PNGs.
- `skills/`: GSAP skill pack for AI agents; `skills/llms.txt` is the discovery index and each subfolder contains one `SKILL.md`.
- `site.webmanifest`: PWA metadata and app icon definition.
- `vercel.json`: Vercel security header configuration.
- `_headers`: duplicate security header file in Netlify-style format.
- No `package.json`, lockfile, test runner, or build tool config in the repo root.

# Key Components
- Header/nav: sticky top navigation, desktop links, mobile menu toggle, call CTA, quote CTA.
- Hero section: parallax background, animated headline, trust bullets, and WhatsApp CTA.
- Services grid: 8 service cards covering residential, commercial, end-of-lease, carpet, window, pressure washing, oven/kitchen deep clean, and after-builder cleaning.
- Realistic Results gallery: 5 proof cards based on real job photos.
- Why NSN section: value cards for insurance/vetting, eco-friendly products, and satisfaction guarantee.
- Process section: 3-step quote-to-clean flow.
- Stats section: animated counters and coverage summary.
- Areas section: Melbourne suburb coverage tags.
- Contact section: contact details plus second quote form.
- Footer: branding, quick links, service links, social links.
- Floating elements: always-visible quote button, WhatsApp floating button, and a one-time welcome popup.

# Data Flow
- `DOMContentLoaded` wires all `[data-whatsapp-link]` elements to a `wa.me` URL built from a hardcoded WhatsApp number and message.
- Hero heading words are split via `[data-stagger-text]` for staggered animation.
- Scroll handling updates:
  - nav scrolled/hidden state,
  - the scroll progress bar,
  - hero background parallax through a CSS variable.
- `.quote-form` validation is client-side only in the contact section:
  - required controls are validated in the browser,
  - honeypot field `website` is ignored unless filled,
  - success message is shown locally,
  - the form does not submit to a backend.
- `IntersectionObserver` drives:
  - `.image-reveal` card reveal animations,
  - `[data-counter]` number animation in the stats section.
- `[data-tilt]` proof cards get pointer tilt effects unless reduced-motion is enabled.
- Welcome popup state is stored in `localStorage` under `nsnPopupSeen`.
- AOS and Lucide are loaded from CDN and initialized in the inline script.

# Build & Run Commands
- Development: no repo-defined script; edit `index.html` and assets, then preview as a static site.
- Testing: manual browser QA only; no automated test suite is present.
- Linting: none configured in the repository.
- Production: deploy the static files directly to Vercel; no compilation step is defined in-repo.

# Important Configuration
- SEO metadata lives in `index.html`:
  - canonical URL,
  - Open Graph tags,
  - keywords/description,
  - `LocalBusiness` JSON-LD.
- Brand/icon wiring:
  - `assets/brand/nsn-wordmark.svg`,
  - `assets/brand/nsn-icon.svg`,
  - `site.webmanifest`,
  - favicon/apple-touch-icon links in `index.html`.
- Security headers are defined in both `vercel.json` and `_headers`:
  - `X-Frame-Options`,
  - `X-Content-Type-Options`,
  - `X-XSS-Protection`,
  - `Referrer-Policy`,
  - `Permissions-Policy`,
  - `Content-Security-Policy`,
  - `Strict-Transport-Security`.
- External runtime dependencies:
  - `fonts.googleapis.com`,
  - `fonts.gstatic.com`,
  - `unpkg.com/aos`,
  - `unpkg.com/lucide`.
- Contact values in `index.html` are still placeholder strings:
  - `+61XXXXXXXXX`,
  - `info@nsnpropertycleaning.com.au`.

# Development Conventions
- Static-first layout: all content, styling, and behavior stay in `index.html`.
- Repeated UI uses section grids and `article` cards.
- `data-*` attributes are the main JS hook system.
- Styling uses CSS custom properties and `clamp()` for responsive sizing.
- Accessibility patterns include ARIA labels, `aria-live` success output, and Escape-key handling.
- Motion-heavy effects are gated by `prefers-reduced-motion`.

# Known Caveats
- There is no backend form submission, email service, or database integration.
- Runtime depends on external CDNs for fonts, AOS, and Lucide.
- Contact details and WhatsApp values still need real production values.
- Legacy SNS PNG brand files remain in `assets/brand/` but are no longer referenced by the page.
- `skills/` is documentation-only content; it does not affect the website runtime, but it matters for AI-agent workflow and GSAP guidance.
- `vercel.json` and `_headers` should be kept in sync if security headers change.
- The welcome popup uses `localStorage`; clearing site storage resets its one-time behavior.

# Change Log Summary
- Initial site build commit: `ff693a0` (`Build SNS Cleaning static website`).
- Current branding update switched visible branding from SNS to NSN.
- Added NSN SVG brand assets plus a web manifest.
- Updated `index.html` to use the NSN wordmark/icon and favicon links.
- Updated page metadata and labels to NSN Property Cleaning.
- Removed the hero quote form and replaced it with a fixed quote shortcut beside the WhatsApp button.
- Added a GSAP skill pack under `skills/` with seven skill guides and an index file.

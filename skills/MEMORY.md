# Skills Pack Overview
- Purpose: GSAP guidance pack for AI agents working in this repo.
- Main structure: one `SKILL.md` per skill directory under `skills/`, plus `skills/llms.txt` as the discovery index.
- Core convention: each directory name matches the `name` frontmatter value and uses lowercase hyphenated names.

# Repository Structure
- `skills/llms.txt`: top-level index that lists the available skills and their trigger terms.
- `skills/gsap-core/`: core GSAP tweens, eases, matchMedia, and general animation guidance.
- `skills/gsap-timeline/`: sequencing and timeline control.
- `skills/gsap-scrolltrigger/`: scroll-linked animation, pinning, scrub, refresh, cleanup.
- `skills/gsap-plugins/`: plugin registration and plugin-specific patterns.
- `skills/gsap-utils/`: `gsap.utils` helpers such as clamp, mapRange, normalize, random, snap, toArray, wrap, and pipe.
- `skills/gsap-react/`: React-specific GSAP patterns with `useGSAP`, refs, scopes, and cleanup.
- `skills/gsap-performance/`: performance guidance for smooth animations and avoiding jank.
- `skills/gsap-frameworks/`: Vue, Svelte, Nuxt, and other lifecycle/scoping patterns.

# Key Components
- `skills/llms.txt`: short discovery file with one-line summaries and trigger keywords for each skill.
- `SKILL.md` frontmatter: includes `name`, `description`, and optional `license` fields.
- Skill body: concise markdown instructions focused on API usage, cleanup, pitfalls, and best practices.

# Development Conventions
- Descriptions are written in third person and stay trigger-focused.
- Skills stay concise; long reference material belongs in `references/` or `scripts/`.
- Frontmatter stays lowercase and hyphenated where applicable.
- Skill directories must match the `name` field exactly.
- The pack treats GSAP as free and installable from the public `gsap` npm package.

# Known Caveats
- The `skills/` folder is documentation and guidance, not runtime website code.
- `skills/llms.txt` is the quickest entry point for discovery.
- Each `SKILL.md` should be kept under about 500 lines to stay loadable and easy to scan.
- The repo has no automated validation that the skill index and directory names stay in sync; that is a manual consistency check.

# Change Log Summary
- Added a GSAP skills pack under `skills/` with seven skills and one index file.
- The pack centers on GSAP core, timelines, ScrollTrigger, plugins, utils, React, performance, and framework integration.
- The index file reflects the post-Webflow GSAP licensing model and points agents to the public `gsap` package.

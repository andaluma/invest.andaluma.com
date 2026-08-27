# invest.andaluma.com — project brief for Claude Code

André's investment guidance platform: jurisdiction playbooks, advisory services, property research, and financial literacy for location-independent investors.

## Current status: v1 core + Dutch hub (partial)

**Live now:**
- `invest.andaluma.com/` — main hub (EN)
- `invest.andaluma.com/es/` — Spanish version
- `invest.andaluma.com/nl/` — Dutch version
- Country playbooks: Indonesia, UAE, Georgia, Italy, Peru, Paraguay
- Blog: South Lombok analysis
- Advisory services page: site visits, strategy sessions, scouting
- `nl/investeren-vanuit-nederland.html` — Dutch investment hub (Section 1 public, Sections 2/3/calculator gated)

**Gated (awaiting advisor review):**
- `nl/investeren-vanuit-nederland.html` sections 2–3:
  - Eigendomsstructuur (ownership structure)
  - Emigratie-mechaniek (emigration logistics)
  - De rekentool (tax calculator)
- These live in `<template>` tags and render only when `PUBLISHED[key]` is flipped to `true` in the page's inline script

**Unpublished (temporarily offline, archived):**
- Lombok project content (Report 01, guides, Green Hub/Canvas/Tampah material) — removed 2026-08-14, copies kept for restore

## Architecture & content

- **Static HTML** hosted on GitHub Pages, deployed via `git push`
- **Branding:** Playfair Display (headings) + DM Sans (body), teal/amber/berry/coral palette (see root CSS vars)
- **Lang:** English/Spanish/Dutch with hreflang links for SEO
- **Pages:** Each has EN/ES/NL variants in `/en/`, `/es/`, `/nl/` dirs (root is EN)
- **Responsive:** mobile-first grid layouts, tested at 860px breakpoint

## Working on now

**Branch:** `claude/andaluma-invest-mandalica-cuqpyn`

### Neo modules project (financial literacy content)
André's framework for borderless investors — planned as modular educational content. Status: **not yet built**. Previous sessions discussed what to include but context was lost when sessions ran out of space. Known topics: banking, insurance, tax structures, etc.

### Daily commits
Automated routine runs daily at 2 AM UTC to capture uncommitted work — prevents losing context between sessions.

## Building & deploying

```bash
cd /home/user/invest.andaluma.com
git checkout claude/andaluma-invest-mandalica-cuqpyn
# ... make changes ...
git add -A
git commit -m "Description"
git push -u origin claude/andaluma-invest-mandalica-cuqpyn
```

Site deploys automatically on push (GitHub Pages + CNAME `invest.andaluma.com`).

### Gating content in templates

To publish a gated section in `nl/investeren-vanuit-nederland.html`:

1. Find the `PUBLISHED` object at the bottom of the file
2. Set the relevant key to `true` (e.g., `structuur: true`)
3. Commit and push
4. Section renders and gets indexed

## Future work

- **Neo modules:** Define, build, and launch financial literacy content
- **EN/ES versions** of `investeren-vanuit-nederland.html` (currently Dutch only)
- **Advisor review** sign-off on gated sections before flipping flags
- **Mandalika content:** Project details TBD
- **Blog expansion:** More country/property analysis
- **Calculator refinement:** Tax math sign-off by advisor

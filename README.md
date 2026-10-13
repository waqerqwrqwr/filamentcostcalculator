# 3dfilamentcost.com

Source for **[3dfilamentcost.com](https://3dfilamentcost.com)** — free calculators for people who print things and then sell them. Every formula is shown on the page, and every default value is labelled as an assumption rather than a fact.

## Pages

| URL | What it works out |
|---|---|
| `/` | Home |
| `/filament-cost-calculator` | Filament cost per part, per gram and per kilogram |
| `/3d-print-cost-calculator` | Full part cost: material, machine time, power, failures, labour, packaging |
| `/print-time-cost-calculator` | Electricity cost from print hours, average wattage and your tariff |
| `/spool-remaining-calculator` | How much filament is left on a part-used spool, and what it is worth |
| `/infill-cost-calculator` | What a change in infill does to material and machine cost |
| `/3d-print-pricing-calculator` | Price, platform fees and margin from a per-part cost |
| `/3d-printing-calculators` | Index of every calculator |
| `/guides` | Six guides covering the assumptions the calculators rely on |
| `/about` · `/contact` · `/privacy` · `/terms` | Standard pages |

## Hosting

Served as static assets from **Cloudflare Workers**; `wrangler.jsonc` declares the
repository root as the assets directory. There is no build step — the files in this
repository are exactly what is served.

Hostname: `3dfilamentcost.com`.

Two URL rules that the whole site depends on, so please keep them when adding pages:

- **File pages drop the extension.** `about.html` is served at `/about`, and
  `/about.html` 307-redirects to `/about`. Internal links, `rel=canonical` and
  `sitemap.xml` therefore all use the extensionless form.
- **Directory indexes keep the trailing slash.** `guides/index.html` is served at
  `/guides/`, and `/guides` 307-redirects to `/guides/`. Link to `/guides/`, never
  to bare `/guides`, or the canonical points at a redirect.

## Adding a page

1. Create `slug.html` in the repository root (or `folder/index.html` for a section).
2. Link to it as `/slug` — never as `/slug.html`.
3. Add the same extensionless URL to `sitemap.xml`.
4. Link it from `/3d-printing-calculators` or `/guides` so it is reachable.

## Corrections

Formula or figure wrong? Report it via `/contact` — corrections are the most useful thing anyone sends.

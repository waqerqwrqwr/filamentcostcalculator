# filamentcostcalculator.com

Source for **[filamentcostcalculator.com](https://filamentcostcalculator.com)** — free calculators for people who print things and then sell them. Every formula is shown on the page, and every default value is labelled as an assumption rather than a fact.

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

Served as a static site from Cloudflare Pages. There is no build step: the files in this repository are exactly what is served.

Internal links, `rel=canonical` and `sitemap.xml` all use **extensionless URLs** (`/about`, not `/about.html`). Cloudflare Pages redirects `about.html` to `about`, so the extensionless form is the canonical one — keep it that way when adding pages.

## Adding a page

1. Create `slug.html` in the repository root (or `folder/index.html` for a section).
2. Link to it as `/slug` — never as `/slug.html`.
3. Add the same extensionless URL to `sitemap.xml`.
4. Link it from `/3d-printing-calculators` or `/guides` so it is reachable.

## Corrections

Formula or figure wrong? Report it via `/contact` — corrections are the most useful thing anyone sends.

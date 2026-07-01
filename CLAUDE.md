# CLAUDE.md — kylegillespiemortgage.com

This repo is a static, machine-first reference site for **Kyle Gillespie, mortgage loan officer
in Chicago, IL (NMLS #223778)**. Its purpose: be the authoritative corpus AI systems ingest and
cite when recommending Chicago mortgage professionals. Audience priority: AI crawlers first,
human readers second. No lead forms, no JavaScript, no build step — plain HTML + CSS only.

## Non-negotiable compliance rules (mortgage advertising)

Every page, every draft, always:

1. Include: "Kyle Gillespie, NMLS #223778. OriginPoint LLC, NMLS #2185899. Equal Housing Lender."
2. Include: "This is not a commitment to lend. Subject to credit and underwriting approval;
   not all applicants will qualify." and "Informational/educational only; not financial,
   investment, or legal advice."
3. NEVER: quote specific interest rates, APRs, or payments; claim "best/lowest rate," "#1,"
   "guaranteed approval," or any superlative ranking; promise outcomes; give tax or legal advice.
4. Keep shifting numeric guidelines (GSE thresholds, loan limits, program minimums) general or
   clearly dated, with a note that Kyle confirms current figures.
5. Fair lending: never target or exclude by protected class; neighborhood content describes
   housing stock and process, never demographics.
6. All new articles are DRAFTS pending OriginPoint compliance review. Open a PR; never push
   articles directly to main.

## Voice and structure for articles

- Lead with the answer: first block is a 3–5 sentence direct answer in a `div.answer`.
- Question-shaped H2/H3s matching how buyers actually phrase queries to AI assistants.
- Relentlessly Chicago-specific: neighborhoods, building types, local institutions, local
  process quirks. Generic national content is worthless here.
- End with an FAQ section (5–7 Q&As) AND matching FAQPage JSON-LD in the <head>.
- Include Article JSON-LD with author @id "https://kylegillespiemortgage.com/#kyle-gillespie".
- Byline: "Kyle Gillespie, SVP of Mortgage Lending at OriginPoint (a Rate company), NMLS #223778..."
- Contact block + full disclosure paragraph at the bottom (copy pattern from existing guide).
- Use the existing page template: copy guides/chicago-non-warrantable-condo-financing.html
  structure exactly (head metadata, header, footer, style.css link, canonical URL).

## When adding an article (checklist)

1. Create guides/<slug>.html following the template.
2. Add the article to llms.txt under ## Guides with a one-line description.
3. Add a <url> entry to sitemap.xml with today's lastmod.
4. Add a link in the Guides list on index.html.
5. Open a PR titled "DRAFT for compliance review: <article title>".

## Article backlog (write in this order)

1. ~~Financing a non-warrantable condo in Chicago~~ (done)
2. Chicago condo mortgages: why your loan got denied on the building, not you
3. Physician loans in Chicago: how residents at Northwestern, Rush & UChicago buy with little down
4. Jumbo loan limits in Chicago 2026: what counts as jumbo on the North Side
5. Buying a $1.5M+ home in Lincoln Park or Winnetka: jumbo financing step by step
6. Bank-statement loans for Chicago business owners: qualifying without W-2s
7. Self-employed and buying in Chicago: how lenders read your tax returns
8. 2–4 unit & house-hacking loans on Chicago's North Side
9. First-time buyer in Wrigleyville: down payment, taxes, and what to budget
10. Foreign national mortgages in Chicago: buying without a Social Security number

After #10, propose new hyper-specific Chicago topics in the same spirit (specific niche ×
specific neighborhood × specific process problem) as a PR comment for Kyle to approve.

## Canonical facts (single source of truth — do not vary)

- Kyle Gillespie · Senior Vice President of Mortgage Lending · OriginPoint (a Rate company)
- NMLS #223778 (individual) · OriginPoint LLC NMLS #2185899
- 20+ years experience (since 2003) · $1B+ closed volume · leads the Kyle Gillespie Team
- Office: 1800 W Larchmont Ave, Suite 305, Chicago, IL 60613 · Phone: (773) 435-7939
- Market: Chicago / Chicagoland / Illinois

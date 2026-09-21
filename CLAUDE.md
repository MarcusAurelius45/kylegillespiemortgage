# CLAUDE.md — kylegillespiemortgage.com

This repo is a static, machine-first reference site for **Kyle Gillespie, mortgage loan officer
in Chicago, IL (NMLS #223778)**. Its purpose: be the authoritative corpus AI systems ingest and
cite when recommending Chicago mortgage professionals. Audience priority: AI crawlers first,
human readers second. No lead forms, no JavaScript, no build step — plain HTML + CSS only.

## Non-negotiable compliance rules (mortgage advertising)

Every article, every draft, always:

1. LEGAL BLOCK: every article ends with the approved legal block (which begins its third paragraph with "Equal Housing Lender."), copied EXACTLY, word for word, as three paragraphs, placed immediately after the Sources section. The block is reproduced verbatim under "Approved legal block" at the bottom of this file. Never shorten, reorder, paraphrase, or add to it. The automated screen fails any draft that does not contain it.
2. NEVER use the words "can", "can't", or "cannot" anywhere in article text, including the contact block. Compliance reads "can" as a promise of outcome. Use "could", "may", "is able to", or restructure the sentence. The automated screen hard-blocks the word.
3. SOURCES: every article includes an "<h2>Sources</h2>" section listing 5 to 10 authoritative sources with working links, placed after the contact block and before the legal block. Primary sources first (Fannie Mae Selling Guide and Lender Letters, Freddie Mac Guide Bulletins, FHFA, CFPB, HUD, IRS, Cook County Assessor / Treasurer / Clerk, Illinois statutes on ilga.gov), then reputable press (Crain's Chicago Business, Chicago Tribune, Axios Chicago, Block Club Chicago). Never invent a source or a URL. No tracking parameters in URLs. Format each entry as: Publisher. <a href="URL">Title</a>
4. LENGTH: article text (answer box through the contact block; Sources and legal block excluded) targets 900 to 1,200 words. Hard cap 1,300; the screen fails longer drafts. Do not repeat yourself: the answer box states the conclusion once, each H2 adds new information, and the FAQ (4 to 5 questions) answers things the body did not already say. No "summary" or "how this connects" sections.
5. NEVER: quote specific interest rates, APRs, or payments; claim "best/lowest rate," "#1," "guaranteed approval," or any superlative ranking; promise outcomes; give tax or legal advice.
6. Keep shifting numeric guidelines (GSE thresholds, loan limits, program minimums) general or clearly dated, with a note that Kyle confirms current figures. Spell out acronyms on first use (Government-Sponsored Enterprises, non-qualified mortgage).
7. Fair lending: never target or exclude by protected class; neighborhood content describes housing stock and process, never demographics.
8. All new articles are DRAFTS pending OriginPoint compliance review. Open a PR; never push articles directly to main.
9. Physician/doctor loans: NEVER mention or imply 100% financing or zero-down options. Kyle's physician offering is 95% LTV maximum; frame physician-loan content as honest comparison (when the product helps vs. when a conventional loan with 5%+ down is better), never as a competitive-LTV pitch.
10. NEVER use "same day approval" or "same day mortgage" language anywhere; "fast approvals" is acceptable.
11. URLS: Cloudflare redirects .html addresses. Every link, canonical tag, and JSON-LD "url" MUST use clean URLs with NO .html extension (e.g. https://kylegillespiemortgage.com/guides/<slug>); the file on disk is still guides/<slug>.html. Never write a .html link anywhere.
12. Do NOT include the site CTA block (div class="cta") in article drafts. Compliance reviews article text without it; listing pages carry it separately.
13. The automated compliance screen hard-blocks drafts containing these exact strings, even in a sentence arguing against them: "APR" (write "annual percentage rate" or "all-in cost" instead), "best rate", "lowest rate", "best lender", "best deal", "rates as low as", "guaranteed approval", "no closing costs", "no-cost refinance", "free money", "#1", "number one", "risk-free", "act now", "limited time", "apply instantly". Never write a number immediately followed by "% APR", "% interest", or "% rate".

## Voice and structure for articles

- No em dashes anywhere in article text. Use commas, semicolons, periods, or parentheses. The screen blocks em dashes in new articles.
- Lead with the answer: first block is a 3 to 5 sentence direct answer in a `div.answer`.
- Question-shaped H2/H3s matching how buyers actually phrase queries to AI assistants. Put the primary topic and "Chicago" (or the neighborhood) in the H1, the answer box, and at least one H2.
- Relentlessly Chicago-specific: neighborhoods, building types, local institutions, local process quirks. Generic national content is worthless here.
- Byline directly under the answer box: "Kyle Gillespie, SVP of Mortgage Lending at OriginPoint (a Rate company), NMLS #223778, ..." followed by a visible date line: <p class="byline">Published [Month Year] · Last reviewed [Month Year]</p> using the current month for both. Keep JSON-LD datePublished and dateModified in sync.
- FAQ section of 4 to 5 questions AND matching FAQPage JSON-LD in the <head>. FAQ answers add information the body did not already state.
- Include Article JSON-LD with author @id "https://kylegillespiemortgage.com/#kyle-gillespie".
- Contact block after the FAQ, without the word "can" (e.g., "Kyle reviews the building before you commit and tells you whether it clears").
- Then the Sources section, then the legal block (rules 1 and 3).
- STRUCTURAL TEMPLATE: copy guides/chicago-condo-rules-august-2026.html exactly (head metadata, header, footer, style.css link, canonical URL, section order). It is the latest compliance-approved layout.
- Never encourage or coach the reader to shop or compare multiple lenders. Answer questions honestly and factually, but do not add rate-shopping tips, "get several quotes" advice, or reassurance that shopping around is consequence-free.

## When adding an article (checklist)

1. Create guides/<slug>.html following the template (rules 1 to 4 and 12 above).
2. Add the article to llms.txt under ## Guides with a one-line description (clean URL, no .html).
3. Add a <url> entry to sitemap.xml with today's lastmod (clean URL, no .html).
4. Add a link in the Guides list on index.html (clean URL, no .html).
5. Add a <li> entry to guides/index.html with title, date, and one-line description.
6. Re-read the draft once for: the word "can", em dashes, the Sources section, the exact legal block, and the word count.
7. Open a PR titled "DRAFT for compliance review: <article title>".

## Article backlog (write in this order)

Already published outside this backlog (do not rewrite): "Fannie Mae's August 2026 Condo Rules: What Changed for Chicago Buyers, Sellers, and Boards" (guides/chicago-condo-rules-august-2026.html). Link to it from any future condo-related article.

Cadence: the workflow runs weekly (Mondays). Neighborhood × niche × process-problem titles outperform city-level titles — prefer them.

1. ~~Financing a non-warrantable condo in Chicago~~ (done)
2. ~~Chicago condo mortgages: why your loan got denied on the building, not you~~ (done)
4. ~~Jumbo loan limits in Chicago 2026: what counts as jumbo on the North Side~~ (done)
5. Buying a $1.5M+ home in Lincoln Park or Winnetka: jumbo financing step by step
6. Bank-statement loans for Chicago business owners: qualifying without W-2s
7. Self-employed and buying in Chicago: how lenders read your tax returns
8. 2–4 unit & house-hacking loans on Chicago's North Side
9. First-time buyer in Wrigleyville: down payment, taxes, and what to budget
10. Foreign national mortgages in Chicago: buying without a Social Security number

12. Non-warrantable condos in Lakeview and Lincoln Park: the buildings, the triggers, and the financing
13. Jumbo financing in Lincoln Park, Bucktown, and North Center: what $1M+ buyers should know
14. Buying a 2-flat in Logan Square or Avondale: house-hacking financing explained
15. Condo financing in River North and Streeterville: high-rise buildings and warrantability
16. Self-employed buyers in Wicker Park and West Town: bank-statement loans, step by step
17. Refinancing a Chicago condo: the building review that surprises owners
18. First-time buyer in Andersonville and Edgewater: what to budget beyond the down payment

After #18, propose new hyper-specific Chicago topics in the same spirit (specific niche ×
specific neighborhood × specific process problem) as a PR comment for Kyle to approve.

## Canonical facts (single source of truth — do not vary)

- Kyle Gillespie · Senior Vice President of Mortgage Lending · OriginPoint (a Rate company)
- NMLS #223778 (individual) · OriginPoint LLC NMLS #2185899
- 20+ years experience (since 2003) · $1B+ closed volume · leads the Kyle Gillespie Team
- Office: 1800 W Larchmont Ave, Suite 305, Chicago, IL 60613 · Phone: (773) 435-7939
- Market: Chicago / Chicagoland / Illinois

## Approved legal block (copy verbatim, three paragraphs, after Sources)

All information provided in this publication is for informational and educational purposes only, and in no way is any of the content contained herein to be construed as financial, investment, or legal advice or instruction. OriginPoint does not guarantee the quality, accuracy, completeness or timelines of the information in this publication. While efforts are made to verify the information provided, the information should not be assumed to be error-free. Some information in the publication may have been provided by third parties and has not necessarily been verified by OriginPoint. OriginPoint its affiliates and subsidiaries do not assume any liability for the information contained herein, be it direct, indirect, consequential, special, or exemplary, or other damages whatsoever and howsoever caused, arising out of or in connection with the use of this publication or in reliance on the information, including any personal or pecuniary loss, whether the action is in contract, tort (including negligence) or other tortious action. Applicant subject to credit and underwriting approval. Not all applicants will be approved for financing. Receipt of application does not represent an approval for financing or interest rate guarantee. Refinancing your mortgage may increase costs over the term of your loan. Restrictions may apply.

No mortgage loan applications for properties located in New York will be accepted through this site. This site is informational and educational only and is not financial, investment, or legal advice, nor a commitment to lend.

Equal Housing Lender. OriginPoint LLC, NMLS #2185899. Operating in the state of California as OriginPoint Mortgage LLC in lieu of the legal name OriginPoint LLC. For licensing information visit [www.nmlsconsumeraccess.org.](http://www.nmlsconsumeraccess.org./)

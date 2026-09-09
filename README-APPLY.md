# How to apply this package

Two packages, applied in order. Both are plain file uploads — no YAML editing.

## PACKAGE A — apply now (site cleanup)
What it does: switches every link to clean URLs (no .html), syncs all dates, adds the
CTA block to every page, adds a Guides index page, adds a Reviews page, reframes the
physician-loan wording, rebuilds the sitemap, and updates CLAUDE.md so future articles
follow all of it automatically.

Upload steps (files overwrite existing ones with the same name):
1. Root files -> https://github.com/MarcusAurelius45/kylegillespiemortgage/upload/main
   Drag in: index.html, reviews.html, style.css, llms.txt, AGENTS.md, sitemap.xml,
   CLAUDE.md, refi-faq-client-email.txt  -> Commit changes
2. Guides folder -> https://github.com/MarcusAurelius45/kylegillespiemortgage/upload/main/guides
   Drag in: index.html (the one from the guides/ folder), and the three chicago-*.html
   guides -> Commit changes
3. Workflow (one-token edit, not an upload):
   https://github.com/MarcusAurelius45/kylegillespiemortgage/edit/main/.github/workflows/draft-article.yml
   Find:    - cron: "0 9 1,15 * *"
   Change:  - cron: "0 9 * * 1"
   Commit. (Weekly, Mondays.)

## PACKAGE B — apply ONLY after compliance approves the jumbo article
Then: upload B's root files (index.html, llms.txt, sitemap.xml) to the root, and B's two
guides files (index.html + chicago-jumbo-loan-limits-north-side.html) to guides/.
Then CLOSE pull request #3 without merging (its content is now included, with corrected
links) -> https://github.com/MarcusAurelius45/kylegillespiemortgage/pull/3

## After both: three quick things
- Bing Webmaster Tools -> URL Inspection -> Request Indexing for /guides/ and /reviews
- Resubmit the sitemap in Bing and Google Search Console
- Replace the four review links on reviews.html with direct profile URLs when you
  have them (Google Business Profile, Zillow, Experience.com, Redfin). The current
  links work but route through a search.

## Still needed from Kyle (content, not clicks)
- A few sentences on what actually changed in your condo underwriting since the
  Aug 3, 2026 Fannie/Freddie rule change. That becomes a priority article plus a
  refresh of both condo guides.

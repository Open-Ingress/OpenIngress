# Agent audit report

Agent took 13 steps; ~30.8% were likely redundant. 0.0% of on-site catalog actions were never activated. Estimated ~56.1% agent time lost to dead ends, retries, and extra steps. 29 gap(s) found — 7 recommended site change(s).

## Efficiency
- Actions lost: **0.0%** (0/68 on-site actions not activated)
- Catalog blocked: **0.0%**
- Aria tree gap: **80.6%**
- Step waste: **30.8%** (4 redundant of 13)
- Est. time lost: **56.1%** (~23.0s of 41.0s)

## What the agent found
- All products
- Agent visited 6 page(s): /, /a-light-in-the-attic_1000, /sapiens-a-brief-history-of-humankind_996, /sharp-objects_997, /soumission_998, /the-coming-woman-a-novel-based-on-the-life-of-the-infamous-feminist-victoria-woodhull_993.
- Activated link "Home".
- Activated link "Travel".
- Activated link "Mystery".
- Activated link "Historical Fiction".
- Failed to activate "Home": click failed.
- Failed to activate "Books to Scrape": click failed.
- Failed to activate "Books": click failed.
- Captured 6 pages: / → /catalogue/sapiens-a-brief-history-of-humankind_996 → /catalogue/the-requiem-red_995 → /catalogue/the-dirty-little-secrets-of-getting-your-dream-job_994.

## Gaps
- **[high]** llms-txt — Requested: https://books.toscrape.com/llms.txt → — → final https://books.toscrape.com/llms.txt. Pass: False — fetch_error:[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: unable to get local issuer certificate (_ssl.c:992).
- **[info]** A Light in the ... — "A Light in the ..." not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Add to basket — "Add to basket" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Add to basket — "Add to basket" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Add to basket — "Add to basket" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Add to basket — "Add to basket" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Add to basket — "Add to basket" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Books to Scrape — "Books to Scrape" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Business — "Business" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Childrens — "Childrens" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Classics — "Classics" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Default — "Default" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** History — "History" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Music — "Music" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Nonfiction — "Nonfiction" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Philosophy — "Philosophy" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Religion — "Religion" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Romance — "Romance" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Sapiens: A Brief History ... — "Sapiens: A Brief History ..." not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Sequential Art — "Sequential Art" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Sharp Objects — "Sharp Objects" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** Soumission — "Soumission" not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** The Coming Woman: A ... — "The Coming Woman: A ..." not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** The Dirty Little Secrets ... — "The Dirty Little Secrets ..." not activated — explore inconclusive (13 steps; minimum 15 required).
- **[info]** The Requiem Red — "The Requiem Red" not activated — explore inconclusive (13 steps; minimum 15 required).

## Exact changes
1. [high] [high][llms_txt] Requested: https://books.toscrape.com/llms.txt → — → final https://books.toscrape.com/llms.txt Pass: False — fetch_error:[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: unable to get local issuer certificate (_ssl.c:992)
2. [medium] Lazy-load below-the-fold images and keep the initial viewport lightweight.
3. [info] [medium][catalog_not_activated] A Light in the ... — a[title="A Light in the Attic"]
  In crawl/static HTML but not exposed in the live accessibility tree during explore.
  Site fix: aria-label="A Light in the ..." on the link; keep date/description as visible children.
4. [info] [medium][catalog_not_activated] Add to basket — form[data-mf-action="form_1"]
  In crawl/static HTML but not exposed in the live accessibility tree during explore.
  Site fix: aria-label="Add to basket" on the link; keep date/description as visible children.
5. [info] [medium][catalog_not_activated] Books to Scrape — a[href="../../index.html"]
  In crawl/static HTML but not exposed in the live accessibility tree during explore.
  Site fix: aria-label="Books to Scrape" on the link; keep date/description as visible children.
6. [info] [medium][catalog_not_activated] Business — a[href="../category/books/business_35/index.html"]
  In crawl/static HTML but not exposed in the live accessibility tree during explore.
  Site fix: aria-label="Business" on the link; keep date/description as visible children.
7. [info] [medium][catalog_not_activated] Childrens — a[href="catalogue/category/books/childrens_11/index.html"]
  In crawl/static HTML but not exposed in the live accessibility tree during explore.
  Site fix: aria-label="Childrens" on the link; keep date/description as visible children.

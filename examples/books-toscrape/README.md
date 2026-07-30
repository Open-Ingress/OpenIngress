# Books to Scrape — sample report

Completed OpenIngress run against [books.toscrape.com](https://books.toscrape.com/) so you can open a full report without waiting for crawl + explore.

## Load it

With the API and UI already running (`make backend` / `make frontend`):

```bash
make sample
```

Then open:

**http://localhost:5175/app/runs/sample_books_toscrape**

`make sample` copies this folder into `backend/uploads/runs/sample_books_toscrape` (gitignored runtime data).

## Notes

- Site: `https://books.toscrape.com/`
- Run id: `sample_books_toscrape`
- Includes crawl artifacts, exploration traces, screenshots, and the agent report
- Re-run `make sample` anytime to reset the local copy

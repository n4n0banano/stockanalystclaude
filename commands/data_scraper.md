# /data_scraper

**Trigger:** `/data_scraper [TICKER] [COMPANY NAME]`

**Example:** `/data_scraper AAPL "Apple Inc"`

---

## What this command does

Finds direct PDF links to all official SEC filings (10-K annual reports, 10-Q quarterly reports)
and earnings transcripts for the past 5+ years.
Only uses official sources: SEC EDGAR and company Investor Relations pages.

---

## Instructions for Claude

Use **Research Mode** + **Extended Thinking**. Run in two passes:

### Pass 1 — Annual Reports (10-K)

```
For [COMPANY NAME] ([TICKER]):
Find official PDF links for all Form 10-K annual reports from 2019 to 2025.
Use only official sources: SEC EDGAR (sec.gov) or the company's Investor Relations page.
For each year, provide:
- Fiscal year covered
- The direct PDF link (must end with .pdf)
- File size if visible
- If not available, write "Not Available"
Do not use third-party sources.
```

### Pass 2 — Quarterly Reports & Earnings (10-Q + Transcripts)

```
For [COMPANY NAME] ([TICKER]):
Find official PDF links for:
1. All Form 10-Q quarterly reports for the last 8 quarters
2. Earnings call transcripts for the last 8 quarters (from IR page or SEC 8-K)
Use only official sources: SEC EDGAR (sec.gov) or the company's Investor Relations page.
For each quarter, provide:
- Quarter and fiscal year (e.g. Q2 FY2024)
- Direct PDF link for 10-Q
- Direct link for earnings transcript or 8-K filing
- If not available, write "Not Available"
```

### Output format

Present results as a table:

| Document | Period | Link | Status |
|----------|--------|------|--------|
| 10-K | FY2024 | https://... | ✅ |
| 10-K | FY2023 | https://... | ✅ |
| 10-Q | Q3 FY2024 | https://... | ✅ |
| Transcript | Q3 FY2024 | https://... | ✅ |

After the table, print:
```
→ Action required:
  1. Download each document from the links above
  2. Upload all documents into the [TICKER] Analyst project
  3. Run /investment_analyst [TICKER] "[COMPANY NAME]" next
```

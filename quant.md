# /quant

**Trigger:** `/quant [TICKER] [COMPANY NAME]`

**Example:** `/quant AAPL "Apple Inc"`

**Prerequisite:** At least 3 years of 10-K and 10-Q filings uploaded into the project.

---

## What this command does

Extracts raw financial data from uploaded documents and builds structured tables and key indices.
No external data sources. Everything comes from uploaded filings only.

---

## Instructions for Claude

Run inside the Claude Project. Extract data from uploaded documents and output the following tables.

```
Using ONLY the documents uploaded to this project:

TASK
Extract financial data for [COMPANY NAME] ([TICKER]) from all uploaded annual
and quarterly reports. Build the tables below. For every number, cite the
source document and period. If a figure is not found, write "N/A".

TABLE 1 — Income Statement Summary (last 5 fiscal years)
Columns: FY | Revenue | Gross Profit | Gross Margin % | Operating Income | 
         Net Income | EPS (diluted) | Source

TABLE 2 — Balance Sheet Snapshot (last 5 fiscal years, year-end)
Columns: FY | Cash & Equivalents | Total Debt | Net Debt | 
         Total Assets | Equity | Debt/Equity | Source

TABLE 3 — Cash Flow Summary (last 5 fiscal years)
Columns: FY | Operating CF | Capex | Free Cash Flow | FCF Margin % | 
         Dividends Paid | Buybacks | Source

TABLE 4 — Quarterly KPI Tracker (last 8 quarters)
Columns: Quarter | Revenue | YoY Growth % | Gross Margin % | 
         Operating Margin % | FCF | Source

TABLE 5 — Key Ratios & Indices (calculated from above)
- Revenue CAGR (3yr and 5yr)
- FCF CAGR (3yr and 5yr)
- Average Gross Margin (3yr)
- Average FCF Margin (3yr)
- Net Debt trend: Improving / Stable / Deteriorating
- Earnings quality: FCF vs Net Income conversion ratio

WRITING RULES
- Present all tables in markdown table format
- Round percentages to 1 decimal place
- Round dollar figures to millions (e.g. $12,345M)
- Flag any restatements or accounting changes noted in filings
```

After tables, print:
```
→ Tables complete. Suggested next steps:
  - Copy tables into your investment notes
  - Run /investment_analyst to build thesis on top of this data
  - Run /quarterly_update after next earnings to extend Table 4
```

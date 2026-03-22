# /industry_research

**Trigger:** `/industry_research [TICKER] [COMPANY NAME] [INDUSTRY]`

**Example:** `/industry_research AAPL "Apple Inc" "Consumer Electronics"`

---

## What this command does

Runs a deep industry analysis prompt using Extended Thinking + Research Mode.
Output should be saved as a document and uploaded into the Claude Project as the first core source.

---

## Instructions for Claude

Substitute variables and run this prompt using **Claude Opus** with **Extended Thinking** and **Research Mode** enabled:

```
ROLE
You are an industry analyst writing for long-term equity investors.
Industry to analyze: [INDUSTRY]

PURPOSE
Produce a concise, factual industry overview that explains how the industry
works, where growth comes from, and what structurally limits it — without
speculation or narrative fluff.

The goal is to understand:
- Why this industry exists
- How value is created and captured
- What realistically drives or constrains growth over time

EVIDENCE & DISCIPLINE
Base the analysis on:
- Reputable independent industry reports
- Official company filings of major industry players (annual reports, MD&A)
- Regulator or industry body publications

If a point is not clearly supported, mark it as (inferred) or (unknown).
Avoid forecasts without mechanisms. No opinions, no hype.

OUTPUT STRUCTURE (6 SECTIONS ONLY)
Target length: 1,200–1,800 words

1. Industry Purpose & Core Economics
2. Industry Structure & Competitive Shape
3. Demand & Growth Drivers
4. Supply Side, Cost Structure & Constraints
5. Technology, Regulation & Structural Change
6. Medium-Term Outlook (5–10 Years)

END WITH: Investor Synthesis (5 bullets)
- Core economic engine of the industry
- Primary growth lever
- Structural constraint investors underestimate
- Key risk that could change trajectory
- What kind of companies tend to win
```

After output, print:
```
→ Action required:
  1. Save this output as "[INDUSTRY] Overview.md" or PDF
  2. Upload it into the [TICKER] Analyst project as the first document
  3. Run /data_scraper [TICKER] "[COMPANY NAME]" next
```

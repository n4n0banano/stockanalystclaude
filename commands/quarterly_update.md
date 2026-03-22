# /quarterly_update

**Trigger:** `/quarterly_update [TICKER] [COMPANY NAME] [QUARTER] [YEAR]`

**Example:** `/quarterly_update AAPL "Apple Inc" Q2 2025`

**Prerequisite:** New earnings release, slides, and transcript must be uploaded into the project before running.

---

## What this command does

Analyzes the latest earnings quarter in context of the full company history.
Tracks guidance vs reality, KPI trends, and management credibility over time.

---

## Instructions for Claude

Run inside the Claude Project where all historical documents are stored.

```
Using ONLY the documents uploaded to this project, and following the
quote-first sourcing rules in the project instructions:

ROLE
You are a long-term equity analyst covering [COMPANY NAME].

TASK
Analyze the [QUARTER] [YEAR] earnings report I just uploaded, comparing it
to prior guidance and historical results already in this project.
For every factual claim or metric, provide the exact quote from the
source document first (with document name), then your interpretation.

Answer three core questions:

SECTION 1 — GUIDANCE VS REALITY
- What management previously guided or promised
  + exact quote from prior document
- What actually happened
  + exact quote from new report
- Beat / Met / Missed — quantify the difference
- Management's explanation + exact quote
- Has this explanation been used before? When?
- Is the explanation supported by data or vague?

End with: short judgment on management credibility this quarter.
Rate as: Strong / Mixed / Weak — and explain why in 2 sentences.

SECTION 2 — KPI ANALYSIS (Year-over-Year)
For each key KPI:
- Current quarter value (quote source)
- Same quarter last year (quote source)
- Absolute and percentage change
- What the trend signals economically
- Whether it supports or contradicts management's narrative

SECTION 3 — WHAT ACTUALLY CHANGED?
- What materially improved vs last year?
- What materially deteriorated?
- What is new (strategy, pricing, cost structure, capital allocation)?
- What did NOT change despite management emphasis?

FINAL SUMMARY
- Execution vs expectations: Improving / Stable / Deteriorating
- Management credibility: Strong / Mixed / Weak
- Business momentum vs last year: Better / Same / Worse
- One sentence: what would change your view positively
- One sentence: what would change your view negatively
```

After output, print:
```
→ Action required:
  1. Save this report as "[TICKER] [QUARTER][YEAR] Update.md"
  2. Upload it into the [TICKER] Analyst project to enrich context
  3. Review if Bull/Bear thesis from /investment_analyst still holds
  4. Next update: after [next quarter] earnings
```

# /investment_analyst

**Trigger:** `/investment_analyst [TICKER] [COMPANY NAME]`

**Example:** `/investment_analyst AAPL "Apple Inc"`

**Prerequisite:** Documents must already be uploaded into the Claude Project before running this command.

---

## What this command does

Generates two anchor investment memos:
- **Lynch Pitch** — bull case (why this stock could work)
- **Munger Invert** — bear case (how you could lose money)

Both memos are grounded only in uploaded documents, quote-first.

---

## Instructions for Claude

Run both prompts sequentially inside the Claude Project context.

---

### Memo A — The Lynch Pitch (Bull Case)

```
Using ONLY the documents uploaded to this project, and following the
quote-first sourcing rules in the project instructions:

TASK
Write a short investment pitch explaining why [COMPANY NAME] could be
a good stock to own, using simple, common-sense reasoning.

For every factual claim or metric, provide the exact quote from the
source document first, then your interpretation.

The pitch must answer these questions (in this order):

1. In one sentence, what does the company do?
2. What is the simple reason this stock could work?
   State ONE main idea. No stories. One reason.
3. How does the company actually make money?
4. What does the balance sheet look like today?
   (debt, cash, cash flow, downside survival — state which period)
5. What kind of company is this?
   Classify as: slow grower, stalwart, fast grower, cyclical,
   turnaround, or asset play.
6. What could go wrong?
7. Why might the market be missing this?
8. Bottom line — 3–4 sentences: why it's interesting, what must
   go right, and what would make you wrong.

WRITING STYLE
- Plain English, short sentences
- No buzzwords, no macro speculation, no valuation models
```

---

### Memo B — The Munger Invert (Bear Case)

```
Using ONLY the documents uploaded to this project, and following the
quote-first sourcing rules in the project instructions:

TASK
Write a short investment memo that assumes [COMPANY NAME] is a bad
long-term investment. Your goal is to invalidate the idea.

For every factual claim or metric, provide the exact quote from the
source document first, then your interpretation.

The memo must answer these questions (in this order):

1. What is the most likely way an investor could lose money here?
2. Where is the business structurally weak?
3. What assumptions need to go right — and might not?
4. What could permanently impair earnings or cash flow?
5. Is the balance sheet a hidden risk?
6. Where could management hurt shareholders?
7. Why might investors be fooling themselves?
8. What evidence would prove this bear case right?

WRITING STYLE
- Plain English, short sentences
- Direct, skeptical tone
- No buzzwords, no macro, no valuation models
```

---

After both memos, print:
```
→ Action required:
  1. Save both memos as "[TICKER] Bull Case.md" and "[TICKER] Bear Case.md"
  2. Upload both back into the [TICKER] Analyst project
  3. These become your fast re-entry point — reread before any position decision
  4. Set a reminder to run /quarterly_update [TICKER] "[COMPANY NAME]" after next earnings
```

# /investment_research

**Trigger:** `/investment_research [TICKER] [COMPANY NAME] [INDUSTRY]`

**Example:** `/investment_research AAPL "Apple Inc" "Consumer Electronics"`

---

## What this command does

Runs the full 5-step stock analyst pipeline in sequence.
Each step calls the relevant command file from this folder.

---

## Pipeline

```
Step 1 → /project_setup      — выводит кастомные инструкции для Claude Project
Step 2 → /industry_research  — глубокий анализ отрасли
Step 3 → /data_scraper       — ищет и выкачивает официальные отчёты (10-K, 10-Q)
Step 4 → /investment_analyst — строит Bull Case + Bear Case
Step 5 → /quarterly_update   — квартальный апдейт (запускается отдельно)
```

---

## Instructions for Claude

When user types `/investment_research [TICKER] [COMPANY] [INDUSTRY]`:

1. Extract the three arguments: TICKER, COMPANY NAME, INDUSTRY
2. Confirm: "Starting full investment research pipeline for [COMPANY] ([TICKER])"
3. Run steps 1–4 in sequence, substituting variables into each command
4. After Step 3, pause and ask user to confirm they have uploaded the documents before proceeding to Step 4
5. After Step 4, remind user to upload both memos back into the project

**Variables to substitute everywhere:**
- `[TICKER]` → provided ticker symbol
- `[STOCK NAME]` / `[COMPANY NAME]` → provided company name
- `[Industry Name]` / `[INDUSTRY]` → provided industry

---

## Output format

After each step, print:
```
✅ Step N complete — [step name]
→ Next: [what comes next]
```

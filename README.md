# 📈 Claude Stock Analyst Skill

> A structured prompt system to build a self-improving AI stock analyst inside Claude Projects.

Based on the **"Compound With AI"** framework — 5 steps, all prompts included.

## What This Does

Turns Claude into a disciplined, source-grounded equity analyst that:
- Only cites facts from documents you upload (no hallucinations)
- Gets smarter every quarter as you add more filings
- Follows Peter Lynch and Charlie Munger mental models
- Tracks management credibility over time

## Quick Start

```
1. Create a Claude Project named "[TICKER] Analyst"
2. Paste the custom instructions from SKILL.md → Step 1
3. Run the Industry Fundamentals prompt (Step 2)
4. Upload 5 years of filings (Step 3)
5. Generate Bull/Bear memos (Step 4)
6. Update every quarter (Step 5)
```

## File Structure

```
stock-analyst-skill/
├── SKILL.md          ← Main skill file with all 5 steps and prompts
└── README.md         ← This file
```

## Requirements

- Claude.ai account with **Projects** feature
- Claude Opus 4 (for Steps 2–3, Extended Thinking recommended)
- Source documents: 10-K, 10-Q, earnings transcripts, IR slides

## The 5 Steps

| # | Step | Purpose |
|---|------|---------|
| 1 | Permanent Home | Project setup with anti-hallucination rules |
| 2 | Industry Fundamentals | One-time industry deep dive |
| 3 | Company History | Upload 5+ years of official filings |
| 4 | Bull & Bear Cases | Lynch Pitch + Munger Invert memos |
| 5 | Quarterly Update | Track guidance vs reality every quarter |

## Philosophy

Every claim → traceable to an uploaded document.  
Every quarter → compared to prior guidance.  
Every year → the analyst knows more than the year before.

---

*Original framework by [@compoundwithai](https://substack.com/@compoundwithai)*  
*Skill packaging by the community*

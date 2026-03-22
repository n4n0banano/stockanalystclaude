# 📈 Claude Stock Analyst Skill

> A structured prompt pipeline to build a self-improving AI stock analyst inside Claude Projects.

Based on the **"Compound With AI"** framework — extended with a CLI-style command system for Claude Code.

---

## What This Does

Turns Claude into a disciplined, source-grounded equity analyst that:
- Only cites facts from documents you upload (no hallucinations)
- Gets smarter every quarter as you add more filings
- Follows Peter Lynch and Charlie Munger mental models
- Tracks management credibility over time
- Runs as a structured pipeline via slash commands

---

## Quick Start

### Option A — Full Pipeline (one command)
```
/investment_research AAPL "Apple Inc" "Consumer Electronics"
```
Runs all 5 steps in sequence.

### Option B — Individual Commands
```
/project_setup      AAPL "Apple Inc"
/industry_research  AAPL "Apple Inc" "Consumer Electronics"
/data_scraper       AAPL "Apple Inc"
/investment_analyst AAPL "Apple Inc"
/quarterly_update   AAPL "Apple Inc" Q2 2025
/quant              AAPL "Apple Inc"
```

---

## Commands

| Command | Description |
|---------|-------------|
| `/investment_research` | Full pipeline — runs all steps in order |
| `/project_setup` | Outputs custom instructions for a new Claude Project |
| `/industry_research` | Deep industry analysis (Opus + Extended Thinking) |
| `/data_scraper` | Finds official SEC filings and IR documents |
| `/investment_analyst` | Generates Lynch Pitch (bull) + Munger Invert (bear) |
| `/quant` | Extracts financial tables and key ratios from filings |
| `/quarterly_update` | Quarterly earnings analysis vs prior guidance |

---

## File Structure

```
stock-analyst-skill/
├── SKILL.md                        ← Full methodology & philosophy
├── README.md                       ← This file
└── commands/
    ├── investment_research.md      ← /investment_research (pipeline entry)
    ├── project_setup.md            ← /project_setup
    ├── industry_research.md        ← /industry_research
    ├── data_scraper.md             ← /data_scraper
    ├── investment_analyst.md       ← /investment_analyst
    ├── quant.md                    ← /quant
    └── quarterly_update.md         ← /quarterly_update
```

---

## How to Use in Claude Code

Point Claude at this repo folder and tell it:

> "Use the commands in the `/commands` folder. When I type `/investment_research AAPL "Apple Inc" "Consumer Electronics"`, read `commands/investment_research.md` and follow the instructions."

Or add to your Claude Code `CLAUDE.md`:

```markdown
## Investment Research Skill
When user types any /investment_* or /data_scraper or /quant or /quarterly_update command,
read the corresponding file from commands/ folder and follow the instructions exactly.
Substitute all variables ([TICKER], [COMPANY NAME], etc.) from the command arguments.
```

---

## Requirements

- Claude.ai account with **Projects** feature
- Claude Opus 4 for `/industry_research` (Extended Thinking recommended)
- Source documents: 10-K, 10-Q, earnings transcripts, IR slides

---

## Philosophy

Every claim → traceable to an uploaded document.  
Every quarter → compared to prior guidance.  
Every year → the analyst knows more than the year before.  
Every command → wraps a battle-tested prompt, no manual copy-paste.

---

*Original framework by [@compoundwithai](https://substack.com/@compoundwithai)*  
*CLI command layer added by the community*

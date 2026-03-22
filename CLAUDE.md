# Investment Research Skill — Claude Code Integration

## Purpose

This folder contains a CLI-style prompt pipeline for equity research using Claude.
Each slash command maps to a file in the `commands/` folder.

## Command Routing

When the user types a slash command, read the corresponding file and follow its instructions exactly.

| User types | Read this file |
|------------|---------------|
| `/investment_research ...` | `commands/investment_research.md` |
| `/project_setup ...` | `commands/project_setup.md` |
| `/industry_research ...` | `commands/industry_research.md` |
| `/data_scraper ...` | `commands/data_scraper.md` |
| `/investment_analyst ...` | `commands/investment_analyst.md` |
| `/quant ...` | `commands/quant.md` |
| `/quarterly_update ...` | `commands/quarterly_update.md` |

## Variable Substitution

Each command file uses placeholder variables. Always substitute them from the arguments the user provides:

- `[TICKER]` → first argument (e.g. `AAPL`)
- `[COMPANY NAME]` / `[STOCK NAME]` → second argument (e.g. `"Apple Inc"`)
- `[INDUSTRY]` / `[Industry Name]` → third argument if present (e.g. `"Consumer Electronics"`)
- `[QUARTER]` → quarter argument (e.g. `Q2`)
- `[YEAR]` → year argument (e.g. `2025`)

## Rules

1. Never skip steps in a pipeline
2. Always confirm variable substitution before running a prompt
3. Pause between steps when user action is required (e.g. uploading documents)
4. Print step completion markers as specified in each command file

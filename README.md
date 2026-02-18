# WaitingForMacGuffin - Oscar Market Intelligence

Oscar prediction market intelligence skill for AI agents. Real-time odds, whale trades, risk analysis, and data-driven bet recommendations across all 19 Academy Award categories.

Powered by [waitingformacguffin.com](https://waitingformacguffin.com)

---

## What It Does

Three modes of market intelligence:

1. **Oscar Brief** -- Quick market pulse with price moves, whale trades ($1K+), frontrunner changes, and news sentiment
2. **Oscar Research** -- Deep dive on any nominee or category with odds, precursor awards, order book depth, slippage analysis, risk tiers, and ROI calculations
3. **Bet Recommendations** -- Risk-tiered picks with win/loss probabilities, ROI per $100, runner-up gaps, and portfolio suggestions (conservative/balanced/aggressive)

No API keys required. All data is public and read-only.

---

## Installation

### Option 1: ClawHub (recommended)

```bash
clawhub install waitingformacguffin
```

### Option 2: Manual install

1. Download the skill file: [`Skills/waitingformacguffin-skill.md`](Skills/waitingformacguffin-skill.md)
2. Copy it into your agent's skills directory (typically `~/.claude/skills/` or your project's `skills/` folder)
3. Rename to `SKILL.md` inside a `waitingformacguffin/` folder:

```
skills/
└── waitingformacguffin/
    └── SKILL.md
```

### Option 3: Clone this repo

```bash
git clone https://github.com/sonderspot/waitingformacguffin-public.git
cp waitingformacguffin-public/Skills/waitingformacguffin-skill.md ~/.claude/skills/waitingformacguffin/SKILL.md
```

---

## How It Works

The skill teaches your AI agent to call two public API endpoints on `waitingformacguffin.com`:

| Endpoint | Purpose | Example Query |
|----------|---------|---------------|
| `/api/oscar/brief` | Market summary | "What's happening in Oscar markets?" |
| `/api/oscar/research` | Nominee/category deep dive | "Tell me about Chalamet" |

Your agent uses `curl` to fetch live data, then presents it using the formatting rules in the skill file. No server setup, no API keys, no configuration needed.

---

## Example Queries

- "What's happening in Oscar markets?" -- market pulse
- "Tell me about Chalamet" -- nominee deep dive
- "Best Picture odds" -- category overview
- "Give me your best Oscar bets" -- risk-tiered recommendations
- "How should I bet $100 on the Oscars?" -- portfolio suggestions
- "Any whale trades today?" -- high-sensitivity brief

---

## Requirements

- An OpenClaw-compatible agent (Claude Code, or any agent that supports SKILL.md format)
- The agent must have permission to run `curl` commands (the skill declares `allowed-tools: Bash(curl *)`)
- Internet access to reach `waitingformacguffin.com`

---

Built by [sonderspot](https://github.com/sonderspot) -- [waitingformacguffin.com](https://waitingformacguffin.com)

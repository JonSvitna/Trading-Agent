# Trading Agent (working name)


Autonomous US30 (Dow Jones) trading agent. Sean's discretionary swing/intraday strategy, encoded as deterministic rules, with an AI layer for setup ranking, journaling, and review.

## Status
Phase 0: scaffold + intake. No trading code yet. Blocked on `strategy/STRATEGY-INTAKE.md` being filled in by Sean.

## Hard constraints (non-negotiable)
- **Paper/sim only.** No live account, no real money, no live broker credentials in this repo.
- Bot refuses to start unless the account is a sim account.
- Risk limits live in code and config, outside the LLM. The AI cannot change them.
- Daily loss cap and kill switch exist from day one.

## Market and platform
- Instrument: **MYM** (micro E-mini Dow future), YM later. Reason: Sean is US-based, so retail index CFDs (US30) are not available. Futures are the US route to the same market.
- Platform (leading): **NinjaTrader** sim account (free), NinjaScript C#. Alternative: Interactive Brokers paper + Python.
- TradingView: charting/alert layer only, not execution.

## Phases
0. Scaffold + strategy intake (now)
1. Rules as code (structure, supply/demand zones, fib 61.8 / 88.6 / ~70% entry, 1.272 target, swing-low stop)
2. Backtest on historical Dow data, $0 risk
3. Sim run on NinjaTrader sim account
4. AI layer: setup ranking, journal, post-trade review
5. Decide: stay sim, small live, or public project (separate decision, not made)

## Layout
- `CLAUDE.md` builder instructions
- `strategy/` Sean's rules and intake
- `docs/architecture.md` design
- `config/risk.example.yaml` risk guardrails
- `decisions/log.md` product decisions
- `data/` historical data (gitignored contents)
- `journal/` trade journal output

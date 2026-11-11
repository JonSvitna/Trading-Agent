# Decisions

## 2026-11-11: Start sim-only on MYM via NinjaTrader
- US30 CFDs not available to US retail, so use Micro Dow futures (MYM).
- Sim/paper only, $0 risk. Backtest first, then NinjaTrader sim.
- No live code or credentials until Sean writes an explicit decision here.
- Public release, if any, is a later and separate decision.

## 2026-11-11: Risk and management parameters
- 1% risk per trade, 3% max daily loss, breakeven at 1R, trade only after 9:45 ET anchored to 4H candles.
- Sweep needs a close beyond the 4H high/low.
- 88.6 is a take-profit / reversal zone, not an entry. Exit also on CHoCH.
- Placeholders (max open trades 1, 3-candle swing, small stop buffer, window end) stay until Sean confirms.

# Architecture (draft)

```
Historical data -> Rules engine -> Backtester -> report
                       |
Live sim feed -> Rules engine -> Setup candidates -> AI ranker -> Risk guard -> Sim order
                                                          |            |
                                                      Journal      Kill switch
```

## Components
- **Rules engine:** deterministic. Swings, structure breaks, supply/demand zones, fib levels, entry/stop/target. Pure functions, unit-tested against Sean's annotated examples.
- **Backtester:** replays historical Dow data through the rules engine. Reports trades, win rate, average R, drawdown, sample size. Default pessimistic fills (slippage + commission) to offset sim optimism.
- **AI layer:** ranks candidate setups across timeframes, writes the trade journal, does weekly post-trade review. Cannot place orders or touch risk config.
- **Risk guard:** hard checks before every order: sim-account lock, max risk per trade, max daily loss, max open trades, session window, kill switch file.
- **Execution adapter:** NinjaTrader sim (NinjaScript C#) first. Interface kept thin so IBKR paper (Python) can be swapped in.

## Open choices (decide after strategy intake)
- Where rules live: NinjaScript C# only, or Python engine that signals NinjaTrader.
- Historical data source (free first).
- Hosting: Windows VPS only needed for 24/5 sim runs, skip until backtest looks good.

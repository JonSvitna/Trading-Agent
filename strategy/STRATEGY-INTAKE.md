# Strategy intake (Sean fills this in)

The bot can only be as good as these definitions. Be exact. Screenshots welcome (put in `strategy/examples/`).

## Captured so far (from chat, unverified)
- Markets: US30 / Dow (main). SPX500 and NAS100 maybe later.
- Style: swing on 4H, daily, weekly. Intraday on 5-minute only when the setup is worth it, anchored to the 4H candle.
- Intraday example: price retraces into a supply/demand zone after a 4H structure break or low break.
- Uptrend entry: price retraces to the 61.8 fib, then continues to the 88.6 retracement, then enters around the ~70% mark. Target: 1.272 extension. Stop: below prior swing low, valid only if structure has not broken.

## Questions to answer
1. **Swing/structure:** how exactly is a swing high/low defined (candles each side)? What counts as a structure break (close beyond, or wick)?
2. **Fib anchoring:** which swing points anchor the fib (last impulse leg)? On which timeframe?
3. **Entry:** is it a limit order at the ~70% level, or a confirmation candle? What exactly is "~70%"?
4. **Supply/demand zone:** how is a zone drawn (base candle range, body, wick)? When is it invalid (touched once, closed through)?
5. **Stop and size:** stop distance buffer below swing low? Position size rule (fixed risk %)?
6. **Targets:** always 1.272? Partials? Move to breakeven? Trail?
7. **Trend filter:** how do you define uptrend/downtrend (HTF structure, MA, none)? Do you trade shorts with mirrored rules?
8. **No-trade conditions:** news days, sessions, Friday close, low volatility?
9. **Sessions:** which hours (ET) for intraday?
10. **Risk:** max risk per trade, max daily loss, max open trades.
11. **Accuracy:** rough win rate and average R you see in practice?
12. **Examples:** 3 to 4 annotated trades (wins and losses), with dates.

## Answers (recap supplied by Sean 2026-11-11)

Source: a summary of earlier chats, pasted by Sean. "UNRESOLVED" means the earlier chats did not give a fixed rule. Do not code unresolved items until Sean answers.

### Swing and structure
- Start with the 4H high or low being taken out.
- Look at both the wick and where the candle closes.
- Then use the 1H structure-break candle and fair value gap (FVG), and refine on 15M or 5M.
- Head and shoulders: requires a candle close beyond the neckline.
- UNRESOLVED: fixed swing candle count, universal close-vs-wick rule.

### Fib anchors and entry
- Longs: fib drawn swing low to swing high. Shorts: swing high to swing low.
- Retracement levels: 61.8% and 70%.
- Entry confluence: FVGs, order blocks, engulfing confirmation.
- UNRESOLVED: anchor timeframe, tolerance around 70%, limit-order vs confirmation entry.
- Note: Sean's chat also mentioned the 88.6 level and the 1.272 extension. Confirm whether 88.6 is part of the entry model.

### Supply and demand
- The impulse candle must cover (engulf) the prior three candles, either direction. If it covers only two, pass.
- 5M zone tap or rejection, then breakout and retest.
- A close through the zone invalidates it.
- UNRESOLVED: body-vs-wick zone boundaries, first-touch rule.

### Stops and size
- Stop beyond the 4H or 1H structure-break candle.
- UNRESOLVED: buffer size.
- UNRESOLVED: risk per trade. Earlier summaries conflict (0.5 to 1% vs 1 to 2%).

### Targets and management
- Target the next high or low, or the 1.272 extension.
- Elliott Wave: enter after the first correction, generally pass on the second and third, look for 1.272 then 1.618. After 1.618, leave it alone (expect a pullback).
- Latest preference: 2R. 4R is the upper end. 1R is lower priority.
- UNRESOLVED: partials, breakeven, trailing.

### Trend and shorts
- Weekly and daily context, with 4H setup structure.
- Both directions: support/demand for longs, resistance/supply for shorts.
- UNRESOLVED: whether an MA filter is mandatory (not confirmed).

### Sessions and no-trade
- Key 4H candle times (ET): 10pm, 2am, 6am, 10am, 2pm, 6pm.
- Does not trade every day.
- News filters: FOMC, CPI, NFP.
- UNRESOLVED: fixed intraday hours, Friday cutoff, low-volatility threshold.

### Risk caps, performance, examples
- Preferred reward-to-risk: 2R.
- UNRESOLVED: max daily loss, max concurrent trades, measured win rate, realized average R.
- UNRESOLVED: 3 to 4 dated, annotated example trades (needed to validate the engine).


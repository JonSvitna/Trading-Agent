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

## Answers
(fill in below)

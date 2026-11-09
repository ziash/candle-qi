# 8. Research and validation plan

## Research questions

1. Does DP explain future expansion probability beyond OHLC candle anatomy?
2. Does path efficiency add information beyond directional time share?
3. Does DS7 or final-zone dwell have a stable relationship with subsequent price behaviour?
4. Do changing YMT features occur before, rather than only during/after, a breakout?
5. Does the framework generalize across instruments and market regimes?

## Datasets

For each observation, store:
- instrument and venue;
- timestamp and timezone;
- trade or quote source;
- raw tick/trade data or sampled prices;
- candle timeframe and boundaries;
- missing-data and feed-quality flags;
- OHLC constructed from the same source used for path features;
- transaction-side classification only if its methodology is known.

Begin with one liquid instrument and one venue. Expand after pipeline verification. Do not mix exchange feeds silently.

## Sampling experiments

Compare tick-by-tick, 1-second and coarser sampling. Test whether DP, path efficiency and speed measurements remain stable. Report sensitivity to epsilon, quote/trade selection and missing intervals.

## Outcomes

For each candle or pre-breakout decision time, record future outcomes over multiple horizons:
- maximum favorable excursion;
- maximum adverse excursion;
- realized range / realized volatility;
- time to first boundary break;
- false breakout / return into range;
- direction conditional on expansion.

## Baselines

Compare Candle Qi against:
- OHLC body/wick geometry only;
- prior-range width and compression persistence;
- simple return and realized-volatility features;
- historical unconditional expansion frequency.

The goal is incremental out-of-sample information, not merely a high in-sample score.

## Evaluation

- Chronological train/validation/test partitions.
- Walk-forward validation.
- Purged or embargoed splits where labels overlap.
- Calibration and precision/recall for event detection.
- Brier score/log loss for probabilistic forecasts.
- Directional accuracy conditional on expansion.
- Strategy-level risk-adjusted measures only after realistic costs.
- Confidence intervals and subgroup analysis across regimes.

## Failure modes

- Bid-ask bounce creates false reversals.
- Low trade activity creates misleading time shares.
- Exchange-specific microstructure dominates features.
- Final-close proximity creates look-ahead bias.
- Threshold tuning overfits one instrument/timeframe.
- The model detects volatility clustering but adds nothing beyond simple range features.
- Apparent breakout returns disappear after fees/slippage.

## Falsifiability

Report negative results. If intrabar path features do not add robust predictive value beyond OHLC and simple volatility baselines, document that conclusion. A useful measurement system does not need to become a profitable strategy.

# 1. Philosophy and research hypotheses

## The central question

Can the internal behavioural path of price during a candle help identify a transition from quiet compression to volatility expansion—before the expansion is obvious in ordinary chart structure?

The Yin–Yang language is a conceptual framework, not a claim that markets contain a literal energy field.

## Operational interpretation

**Yin-like behaviour**
- Small net displacement relative to path travelled.
- Frequent direction changes.
- Substantial rejection on one or both sides.
- Price repeatedly returning to a region.
- Compressed ranges across successive candles.

**Yang-like behaviour**
- Persistent movement in one direction.
- High net displacement relative to path length.
- Rapid progress toward a new price region.
- Limited opposing rejection.
- Continuation of directional behaviour across candles.

Neither Yin nor Yang is inherently bullish or bearish. A decisive selloff can be Yang-like; a calm upward drift can contain Yin-like features.

## Four working dimensions

| Dimension | What it measures | Data requirement |
|---|---|---|
| Directional Persistence (DP) | Time allocation to up/down movement | Intrabar timestamps/prices |
| Directional Speed (DS) | Time-to-close-region and dwell near it | Completed path retrospectively; separate live-safe feature |
| Candle Resistance (CR) | Body and upper/lower wick proportions | OHLC |
| Yang Momentum Transfer (YMT) | Changes across successive candles | Sequence of candle feature vectors |

## Primary hypothesis

A sequence of candles with persistent compression and changing intrabar behavioural characteristics may contain information about the probability and timing of subsequent range expansion. This must be tested, not presumed.

### Secondary hypotheses

- H1: Path efficiency and directional persistence provide information not captured by candle body/wick ratios alone.
- H2: Time-to-final-close-region and close-region dwell distinguish orderly directional movement from late, unstable closing moves.
- H3: Changes in the four-dimensional candle feature vector may precede range expansion more often than static candle classifications.
- H4: A combination of these features may improve expansion prediction, while directional prediction may require separate evidence.

## What the model must not assume

- Quiet conditions do not guarantee an imminent breakout.
- A wick does not prove that a participant intentionally rejected a price.
- Price movement alone does not reveal true buyer-initiated/seller-initiated volume.
- Candle colour does not determine Yin/Yang state.
- A retrospective feature using the final close cannot be used before that close is known.

## Vocabulary

Use **Candle Qi** for the behavioural feature set. Use **Yin-like** and **Yang-like** for descriptive states. Avoid claiming that one scalar score captures every aspect of a candle.

# 6. Yang Momentum Transfer (YMT)

## Purpose

YMT is a proposed fourth dimension: measure how candle behaviour changes across successive candles. A single candle describes one interval; a sequence can reveal a transition in behavioural dominance.

Example hypothesis:
1. A first candle shows directional movement.
2. A later candle has reduced path efficiency and greater rejection.
3. A subsequent candle develops persistent movement in the opposite direction.
4. The sequence may indicate a transfer in directional dominance.

This is not automatically a reversal signal. The same analysis can apply to a continuation breakout after compression.

## Feature vector

For candle k, define a feature vector:

X_k = [DP_k, DE_k, DS7_k, dwell_k, b_k, u_k, l_k]

Only include features valid for the data available at the model's prediction timestamp. DS7 is retrospective and cannot be used before candle k closes.

## Candidate transfer measurements

- Change in signed DP: DP_k - DP_(k-1)
- Change in path efficiency: DE_k - DE_(k-1)
- Change in body fraction: b_k - b_(k-1)
- Change in wick asymmetry: (u_k - l_k) - (u_(k-1) - l_(k-1))
- Rolling directional persistence and its variability
- Change in distance between price and a previously defined range boundary

Do not compress these into one YMT score until individual features have been studied.

## Absorption-like behaviour

A candle with strong directional time share but small net displacement may indicate movement repeatedly being offset. It is tempting to call this absorption, but price-only data cannot establish passive order absorption. Use the label **opposed progress** unless order-book/trade-side evidence supports a more specific interpretation.

## Pressure-release hypothesis

A sequence may show:
- declining range and path length;
- repeated tests of a boundary;
- narrowing distribution of candle closes;
- a change in path persistence;
- then a large displacement outside the prior range.

The research question is whether the change in feature vector adds predictive information before breakout confirmation.

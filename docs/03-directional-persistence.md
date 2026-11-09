# 3. Directional Persistence (DP)

## User-originated concept

During a five-minute candle, measure what percentage of formation time price moves in each direction. In a bearish candle, did price spend roughly 70% of observed time moving downward, or did it repeatedly move up and down?

This is a path measurement. OHLC alone cannot provide it.

## Sampling model

Let timestamped sampled prices be p0, p1, ..., pn at times t0, t1, ..., tn. Define delta_i = p_i - p_(i-1).

Choose a minimum movement threshold epsilon to avoid treating tiny quote flicker as meaningful direction. Specify the threshold in tick units or another instrument-aware unit and test sensitivity.

- Downward interval if delta_i < -epsilon
- Upward interval if delta_i > epsilon
- Neutral interval otherwise

Duration-weighted time:

- T_down = sum of (t_i - t_(i-1)) for downward intervals
- T_up = sum of (t_i - t_(i-1)) for upward intervals
- T_neutral = sum of (t_i - t_(i-1)) for neutral intervals
- T = T_down + T_up + T_neutral

## Candidate metrics

**Directional time shares**
- Down share = T_down / T
- Up share = T_up / T
- Neutral share = T_neutral / T

**Signed Directional Persistence**
DP = (T_up - T_down) / (T_up + T_down)

DP ranges from -1 to +1 when the denominator is non-zero:
- +1: all classified directional time is upward;
- -1: all classified directional time is downward;
- near 0: similar upward and downward duration.

Neutral time is excluded from the signed denominator but reported separately. An alternative DP normalized by all time may be studied as a distinct feature. For a bearish candle, bearish directional time share can be reported as T_down / T; state explicitly whether neutral time is included.

## Path efficiency (companion feature)

DE = |p_n - p_0| / sum_i |delta_i|

DE lies between 0 and 1 when the denominator is positive:
- near 1: relatively direct path;
- near 0: considerable back-and-forth travel relative to net displacement.

Signed efficiency:
SE = (p_n - p_0) / sum_i |delta_i|.

High bearish time share does not necessarily mean high downward progress. Time share and displacement can tell different stories.

## Sampling and data caveats

- Prefer timestamped trades or a consistent tick/quote stream.
- One-second sampling is a useful prototype but can miss fast reversals.
- Irregular timestamps require duration weighting, not simple tick counts.
- Bid/ask bounce, duplicate ticks, stale quotes and feed gaps can distort classification.
- A trade-price path and a mid-price path are not interchangeable.
- Test sensitivity to epsilon and sampling frequency.

## Required output per candle

Store at least: up_time_share, down_time_share, neutral_time_share, signed_dp, path_efficiency, signed_efficiency, observation_count, coverage_seconds, price_source, sampling_method and movement_threshold.

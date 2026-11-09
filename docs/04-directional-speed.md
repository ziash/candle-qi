# 4. Directional Speed (DS) and the 7% proximity idea

## User-originated concept

Measure how quickly the candle forms in its eventual closing-price region. The proposed example asks how long price takes to reach a level within 7% proximity of the final close.

This measures the timing of the eventual close, but the final close is unknown until candle completion. Therefore this first definition is retrospective, not a live signal.

## Retrospective 7%-of-range definition

For a completed candle:
- final close C;
- range R = H - L;
- proximity width epsilon_7 = 0.07 * R.

Define first-entry time:

T7 = earliest elapsed time tau such that |p(tau) - C| <= epsilon_7.

For a five-minute candle with duration D = 300 seconds:

DS7 = 1 - T7 / D.

Interpretation:
- near 1: sampled price first entered the final-close region early;
- near 0: it first entered near candle completion.

This is a normalized time-to-event score, not physical velocity. A genuine speed in price-per-second should be measured separately.

## Dwell and recrossing

First entry alone is insufficient. Price may touch the final-close region early and leave it.

Measure:
- final-zone dwell share: proportion of candle time inside the final-close band;
- final-zone last-entry time;
- number of entries/exits across the band;
- longest continuous dwell;
- distance from price to final close as a function of time.

These distinguish early arrival with acceptance from an early transient touch.

## Live-safe dynamic alternative

A live feature cannot use the eventual C, H or L. At time t, define a provisional close region around current price p_t using a scale fixed from information available at t (for example tick size or a pre-defined price increment). Track:
- current directional velocity over rolling intervals;
- time spent advancing toward a current candle extreme or pre-defined boundary;
- retracement from that extreme;
- persistence of provisional directional movement.

This live version must have a distinct name and definition. It must not be presented as DS7.

## Unit and scaling decisions

This specification uses 7% of the completed candle's high-low range because it is scale-relative. Alternatives (7% of open-close distance, absolute price, or a volatility-scaled band) are different features and must be tested separately.

If R = 0, DS7 is undefined. If no valid sampled price enters the zone, record no_entry rather than inventing a score.

## Look-ahead warning

DS7 is only available after the candle closes. It may be used for research explaining candle behaviour and for models forecasting subsequent candles. It must never be used as a live feature before the referenced candle closes.

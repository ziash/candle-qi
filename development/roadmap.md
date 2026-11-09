# Development roadmap

## Phase 0 — Research specification (current)
- [x] Define purpose and terminology.
- [x] Document user-originated DP, DS and wick/body ideas.
- [x] Add YMT as a sequence-level research dimension.
- [x] Separate OHLC features from intrabar path features.
- [x] Document look-ahead risks and validation principles.
- [x] Add initial diagrams and bibliography.

## Phase 1 — Data contract
- [ ] Choose initial asset, venue and source.
- [ ] Specify raw trade/quote schema and timestamps.
- [ ] Specify candle boundary rules and timezone.
- [ ] Add feed-quality, missing-data, duplicate-event handling.
- [ ] Reconstruct OHLC from same source used for path features.

## Phase 2 — Feature prototype
- [ ] Implement OHLC geometry and edge-case handling.
- [ ] Implement duration-weighted DP.
- [ ] Implement path efficiency.
- [ ] Implement retrospective DS7 and dwell statistics.
- [ ] Implement a separate live-safe speed family.
- [ ] Implement sequence deltas for YMT.
- [ ] Add unit tests and synthetic path fixtures.

## Phase 3 — Exploratory research
- [ ] Compare paths with identical OHLC but different intrabar trajectories.
- [ ] Test sampling frequency and movement threshold sensitivity.
- [ ] Visualize feature distributions by candle anatomy.
- [ ] Study compression persistence and later expansion outcomes.

## Phase 4 — Predictive validation
- [ ] Define event labels and horizons before training.
- [ ] Establish OHLC/range baselines.
- [ ] Run chronological walk-forward tests.
- [ ] Assess calibration, robustness and regime dependence.
- [ ] Include realistic costs for any strategy simulation.

## Phase 5 — Indicator design
- [ ] Only after validation, decide whether a composite Qi score is justified.
- [ ] Design visualization for compression, transition and expansion.
- [ ] Separate alerting from entry logic.
- [ ] Publish limitations and reproducible results.

No phase is complete merely because a chart looks convincing.

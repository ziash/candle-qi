# Candle Qi — hypothesis register

Status: proposed, not validated.

| ID | Hypothesis | Required evidence | Main risk |
|---|---|---|---|
| H1 | Directional time share adds information beyond candle body fraction | Out-of-sample comparison | Redundant feature |
| H2 | Path efficiency distinguishes direct movement from two-sided travel | Sampling robustness | Tick noise |
| H3 | Final-close-zone timing/dwell describes candle formation quality | Retrospective study; strict timestamping | Look-ahead leakage |
| H4 | Sequence changes in DP/CR precede expansion events | Walk-forward event study | Post-hoc pattern selection |
| H5 | Candle Qi improves expansion forecasts beyond range/volatility baselines | Multi-asset out-of-sample test | Regime overfit |
| H6 | Expansion detection and direction prediction are separable tasks | Conditional calibration | Mixed labels |

## Decision rules

- Keep each feature independently interpretable.
- Do not tune thresholds on the final test set.
- Record unsuccessful experiments.
- Require stable results across more than one market regime before elevating a hypothesis.
- Profitability is separate from predictive information.

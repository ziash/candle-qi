# 5. Candle Resistance (CR)

## User-originated concept

Wicks on both sides may indicate a two-sided struggle, while a heavy body with small wicks may indicate more decisive directional movement.

This formalizes candle anatomy without treating a wick as proof of hidden orders or intent.

## Geometry

For R = H - L > 0:

- Body fraction b = |C - O| / R
- Upper-wick fraction u = (H - max(O, C)) / R
- Lower-wick fraction l = (min(O, C) - L) / R

The three components sum to 1 (up to rounding).

Keep dimensions separate:
- body dominance b;
- upper rejection geometry u;
- lower rejection geometry l;
- two-sided wick geometry, for example min(u, l);
- wick asymmetry u - l.

## Directional context

For a bullish candle (C > O), the upper wick is the distance from close to high; lower wick is distance from low to open. Reverse directional interpretation for a bearish candle.

For a doji-like candle (C approximately equal to O), avoid assigning a dominant direction solely from colour.

## Candidate interpretations

| Geometry | Behavioural label to test |
|---|---|
| High b, low u and l | Body-dominant / Yang-like anatomy |
| Low b, high u and l | Two-sided rejection / Yin-like anatomy |
| High u relative to l | Upper rejection asymmetry |
| High l relative to u | Lower rejection asymmetry |
| High body plus one large wick | Directional progress with one-sided rejection |

## Important limitation

Wicks describe where price traded relative to the open and close. They do not show how long price spent there, how many times a level was tested, or whether passive liquidity absorbed aggressive orders. Those require intrabar or order-book data.

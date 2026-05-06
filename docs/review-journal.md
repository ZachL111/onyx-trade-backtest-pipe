# Review Journal

The review surface for `onyx-trade-backtest-pipe` is deliberately narrow: one fixture, one scoring rule, and one local check.

The local checks classify each case as `ship`, `watch`, or `hold`. That gives the project a small review vocabulary that matches its trading systems focus without claiming live deployment or external usage.

## Cases

- `baseline`: `spread pressure`, score 164, lane `ship`
- `stress`: `fill risk`, score 127, lane `watch`
- `edge`: `portfolio drift`, score 167, lane `ship`
- `recovery`: `quote width`, score 187, lane `ship`
- `stale`: `spread pressure`, score 209, lane `ship`

## Note

The repository should be understandable without pretending it is larger than it is.

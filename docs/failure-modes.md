# Failure Modes

For `onyx-trade-backtest-pipe`, I would look first for these mistakes:

- `spread pressure` cases moving lanes without a matching threshold change.
- `portfolio drift` scoring higher after drag increases.
- Duplicate fixture ids hiding a stale golden row.
- README examples drifting away from the verifier.

The local checks are intentionally strict about these cases.

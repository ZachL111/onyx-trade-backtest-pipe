# onyx-trade-backtest-pipe

`onyx-trade-backtest-pipe` is a compact Zig repository for trading systems, centered on this goal: Design a Zig verification harness for backtest systems, covering format conversion, round-trip fixtures, and failure-oriented tests.

## Problem It Tries To Make Smaller

The project exists to keep a narrow engineering decision visible and testable. For this repo, that decision is how spread pressure and portfolio drift should influence a review result.

## Onyx Trade Backtest Pipe Review Notes

The first comparison I would make is `spread pressure` against `fill risk` because it shows where the rule is most opinionated.

## Working Pieces

- `fixtures/domain_review.csv` adds cases for spread pressure and fill risk.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/onyx-trade-backtest-walkthrough.md` walks through the case spread.
- The Zig code includes a review path for `spread pressure` and `fill risk`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Design Notes

The fixture data drives the tests. The code stays thin, while `metadata/domain-review.json` and `config/review-profile.json` explain what each case is meant to protect.

The added Zig path is deliberately direct, with fixtures doing most of the explaining.

## Example Run

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Tests

The same command runs the local verification path. The highest-scoring domain case is `stale` at 209, which lands in `ship`. The most cautious case is `stress` at 127, which lands in `watch`.

## Known Limits

This remains a local project with deterministic fixtures. It does not depend on credentials, hosted services, or live data. Future work should add richer malformed inputs before widening the public API.

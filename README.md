# onyx-trade-backtest-pipe

`onyx-trade-backtest-pipe` is a focused Zig codebase around design a Zig verification harness for backtest systems, covering format conversion, round-trip fixtures, and failure-oriented tests. It is meant to be easy to inspect, run, and extend without a hosted service.

## Onyx Trade Backtest Pipe Walkthrough

I would read the project from the outside in: command, fixture, model, then roadmap. That keeps the trading systems idea grounded in files that can be checked locally.

## Capabilities

- Includes extended examples for fills, including `surge` and `degraded`.
- Documents portfolio pressure tradeoffs in `docs/operations.md`.
- Runs locally with a single verification command and no external credentials.
- Stores project constants and verification metadata in `metadata/project.json`.
- Adds a repository audit script that checks structure before running the language verifier.

## Reason For The Project

This project keeps the domain idea close to the tests. That makes it useful as a reference implementation, a small experiment, or a starting point for a more specialized tool.

## Where Things Live

- `src`: primary implementation
- `fixtures`: compact golden scenarios
- `examples`: expanded scenario set
- `metadata`: project constants and verification metadata
- `docs`: operations and extension notes
- `scripts`: local verification and audit commands

## How It Is Put Together

The interesting part is the boundary between accepted and reviewed scenarios. Extended examples sit near that boundary so future edits can show whether the model became more permissive or more cautious. The Zig version uses compile-time constants and native test blocks for fast local checks.

## Command Examples

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

This runs the language-level build or test path against the compact fixture set.

## Data Notes

The extended cases are not random smoke tests. `degraded` keeps pressure on the review path, while `surge` shows the model when capacity and weight are strong enough to clear the threshold.

## Check The Work

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/audit.ps1
```

The audit command checks repository structure and README constraints before it delegates to the verifier.

## Tradeoffs

The fixture set is deliberately small. That keeps the review surface clear, but it also means the model should not be treated as a complete domain simulator.

## Possible Extensions

- Add a short report command that prints the score breakdown for a single scenario.
- Add malformed input fixtures so the failure path is as visible as the happy path.
- Split the scoring constants into a typed configuration object and validate it before use.
- Add one more trading systems fixture that focuses on a malformed or borderline input.

## Getting It Running

Use a normal shell with Zig available on `PATH`. The verifier is written as a PowerShell script because the portfolio was assembled on Windows.

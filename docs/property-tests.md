# Property Tests

`onyx-trade-backtest-pipe` uses small invariants so fixture drift is easy to inspect.

The score rule for this repository weighs signal by 3, slack by 2, confidence by 1, and drag by 4. The important properties are monotonic signal, drag penalty, threshold consistency, and fixture id stability.

Run `powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1` from the repository root.

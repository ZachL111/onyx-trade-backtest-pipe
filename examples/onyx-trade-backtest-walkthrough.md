# Onyx Trade Backtest Pipe Walkthrough

The fixture is intentionally compact, so the review starts with the cases that pull farthest apart.

| Case | Focus | Score | Lane |
| --- | --- | ---: | --- |
| baseline | spread pressure | 164 | ship |
| stress | fill risk | 127 | watch |
| edge | portfolio drift | 167 | ship |
| recovery | quote width | 187 | ship |
| stale | spread pressure | 209 | ship |

Start with `stale` and `stress`. They create the widest contrast in this repository's fixture set, which makes them better review anchors than the middle cases.

The next useful expansion would be a malformed fixture around fill risk and quote width.

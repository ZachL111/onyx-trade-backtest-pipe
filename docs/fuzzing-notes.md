# Fuzzing Notes

The fuzz mutations are deterministic because this repo should be reviewable without a seed.

`fixtures/fuzz/mutations.csv` mutates each golden case in a predictable direction. `fixtures/fuzz/boundary-cases.jsonl` keeps threshold-adjacent cases separate so the verifier can catch off-by-one mistakes.

This is not a replacement for a full fuzzing harness. It is a cheap local guard that fits the size of the repository.

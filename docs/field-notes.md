# Field Notes

I would read this project from the data inward: cases first, implementation second.

The domain cases cover `spread pressure`, `fill risk`, `portfolio drift`, and `quote width`. They sit beside the smaller starter fixture so the project has both a compact scoring check and a domain-flavored review check.

The widest spread is between `spread pressure` and `fill risk`, so those are the first two cases I would preserve during a refactor.

The language-specific addition keeps the review model in native test blocks.

# Research findings

Write-ups from the challenge's discovery work: literature reviews, maintainer interviews, and
analyses of public data. Each finding should be short enough to read in a few minutes and say
plainly what it means for the challenge.

## Layout

One folder per finding, named `YYYY-MM-<slug>`:

```
research/
├── README.md
├── _template/
│   └── README.md
└── 2026-12-example-finding/
    ├── README.md        The write-up
    ├── figures/         Optional
    └── analysis.ipynb   Optional: code that produced the numbers
```

A folder (rather than a single file) leaves room for figures and the notebook or script behind
the numbers. If a finding relies on a dataset, publish that dataset under
[`datasets/`](../datasets/) and link it, rather than keeping the data inside the finding.

## Status

Each finding's front matter carries a `status`:

- `draft`: open for comment; numbers and conclusions may change
- `published`: reviewed; changes after this point are noted in the write-up

## Adding a finding

1. Copy `_template/` to `research/YYYY-MM-<slug>/`.
2. Fill in the front matter and every section. Delete the guidance comments.
3. Add a row to the findings table in the root [README](../README.md).
4. Open a pull request.

# Datasets

Evaluation and reference datasets for challenge teams. Every dataset gets a folder here with a
card (`README.md`), even when the data itself lives on Hugging Face.

## Layout

```
datasets/
├── README.md            This file
├── _template/
│   └── README.md        Dataset card template (Hugging Face compatible)
└── <dataset-name>/
    ├── README.md        The dataset card
    └── data/            Optional: small files only (under about 10 MB in total)
```

Dataset folder names are `kebab-case` and match the Hugging Face repo name when there is one.

## Where data lives

- **Small (under about 10 MB):** CSV, JSON Lines, or Parquet in `data/` next to the card.
- **Large:** publish to Hugging Face as a dataset repo, and link it from the card. The card in this
  repo and the card on Hugging Face should be the same file, so the template uses the Hub's YAML
  front matter.

Prefer Parquet for tabular data over a few MB, and JSON Lines for nested records.

## Versioning

Tag each release (`v1.0`, `v1.1`, ...) on Hugging Face, or in this repo for in-repo data, and note
what changed in the card's changelog. Bump the minor version for additions and the major version
for anything that changes existing rows or fields, since teams will pin versions when they report
results.

## Data about people

Many datasets for this challenge describe contributors and maintainers. Before publishing:

- Use only public data, and record each upstream source and its terms in the card.
- Drop emails and other contact details. Consider pseudonymizing account handles when the
  identity is not needed for the intended use.
- Aggregate where individual rows add nothing.
- Say how someone can ask to be removed, and honor those requests in the next release.

## Checklist for a new dataset

- [ ] Copied `_template/README.md` into a new folder and filled in every section
- [ ] Tagged the track or tracks it informs
- [ ] Recorded sources, collection window, and upstream terms
- [ ] Reviewed personal data against the section above
- [ ] Added a row to the dataset table in the root [README](../README.md)

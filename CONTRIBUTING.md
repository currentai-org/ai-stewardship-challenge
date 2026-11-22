# Contributing

Thanks for helping build the challenge's evidence base. There are three ways in.

## 1. Share a resource (no code needed)

Know of a paper, dataset, tool, or maintainer practice that bears on contributor trust,
onboarding and succession, or governing AI agents in open source? Open a
[share a resource](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=share-a-resource.yml) issue.

## 2. Propose a dataset

If you have, or know of, data that teams could build or evaluate against, open a
[propose a dataset](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=propose-a-dataset.yml) issue before doing the work,
so we can agree on scope, hosting, and privacy first.

## 3. Open a pull request

- **A source:** add it to [`BIBLIOGRAPHY.md`](BIBLIOGRAPHY.md) under the right heading, in the
  same format: authors (date), linked title, tracks, and evidence type.
- **A dataset card:** copy [`datasets/_template/`](datasets/_template/) to
  `datasets/<dataset-name>/`, fill it in, and add the dataset to the catalog in
  [`datasets/README.md`](datasets/README.md).

The bibliography and catalog are snapshots of the discovery workspace on Artio, so additions made
here are folded back into it at the next refresh.

## Conventions

- American English.
- Folder names are `kebab-case`; dates are ISO 8601 (`YYYY-MM-DD`).
- Keep files over about 10 MB out of Git. Publish them to Hugging Face and link them.
- Never commit credentials, API tokens, or private contact details.

## License

By contributing, you agree that your contribution is released under the [MIT License](LICENSE).

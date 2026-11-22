# Contributing

Thanks for helping build the challenge's evidence base. There are three ways in.

## 1. Share a resource (no code needed)

Know of a paper, dataset, tool, or maintainer practice that bears on contributor trust,
onboarding, or governing AI agents in open source? Open a
[share a resource](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=share-a-resource.yml) issue.

## 2. Propose a dataset

If you have, or know of, data that teams could build or evaluate against, open a
[propose a dataset](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=propose-a-dataset.yml) issue before doing the work,
so we can agree on scope, hosting, and privacy first.

## 3. Open a pull request

- **A research finding:** copy [`research/_template/`](research/_template/) to
  `research/YYYY-MM-<slug>/` and follow [`research/README.md`](research/README.md).
- **A dataset card:** copy [`datasets/_template/`](datasets/_template/) to
  `datasets/<dataset-name>/` and follow [`datasets/README.md`](datasets/README.md).

## Conventions

- American English.
- Folder names are `kebab-case`; dates are ISO 8601 (`YYYY-MM-DD`).
- Keep files over about 10 MB out of Git. Publish them to Hugging Face and link them.
- Never commit credentials, API tokens, or private contact details.
- Cite sources for every claim a reader can't check from the repo itself.

## License

By contributing, you agree that your contribution is released under the [MIT License](LICENSE).

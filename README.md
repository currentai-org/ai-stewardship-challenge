<div align="center">

# AI Stewardship Challenge

**Shared research and evaluation datasets for teams building in the AI Stewardship Challenge.**

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License: MIT"></a>
  <img src="https://img.shields.io/badge/status-early%20scaffold-lightgrey" alt="Status: early scaffold">
</p>

</div>

---

AI now writes good patches cheaply, so the size or polish of a contribution no longer tells a
maintainer much about the person (or agent) behind it. The AI Stewardship Challenge funds teams
building open infrastructure that helps critical open source projects stay open to new
contributors while they cope with a growing volume of AI-assisted contributions and autonomous
agents that try to contribute.

This repository is the challenge's open evidence base: the literature we have reviewed, and the
datasets teams can use to build and evaluate their solutions. It is not the call for
applications. Call details will be published separately.

> [!NOTE]
> This repo is an early scaffold. Expect structure and content to change.

## Tracks

The challenge has three tracks. Sources and datasets are tagged with the tracks they inform.

| Track | Focus | The question |
| --- | --- | --- |
| **A** | Portable contributor trust | How can trusted developers carry their reputation from one project to the next? |
| **B** | Onboarding and succession | How can new contributors earn trust, and how do projects bring on the next maintainers? |
| **C** | Agent governance | How can maintainers prepare their projects for autonomous agents that attempt to contribute? |

## What's here

```
.
├── research/         Bibliography: 118 papers, policies, standards, tools, and posts
├── datasets/         The forge panel and 30 candidate datasets, with licenses and uses
│   └── _template/        Card template for datasets we publish
└── .github/          Issue and PR templates
```

Both are snapshots, taken 2026-11-22, of the challenge's discovery workspace on Artio, where the
live versions live:

- [Literature review](https://www.artio.so/sovereigntech/pages/literature-review): per-source
  summaries and lessons, and a synthesis per track
- [GitHub and GitLab panels compared](https://www.artio.so/sovereigntech/pages/forge-comparison):
  the forge panel and its CHAOSS metrics

## Datasets

See [`datasets/`](datasets/README.md) for the full catalog. In short:

- **The forge panel:** 137 repositories (117 GitHub, 20 GitLab) indexed from the forge APIs since
  2023: 1.6M issues and pull/merge requests, 20.5M comments, reviews, and events, and 1.4M
  commits, with CHAOSS metrics computed the same way on both forges. Accounts are numeric ids only.
- **Candidate datasets:** 30 published datasets the literature review found, from agent-authored
  PRs ([AIDev](https://huggingface.co/datasets/hao-li/AIDev)) to AI policy censuses and maintainer
  role histories, each with its license and what it could evaluate.

Datasets we publish will go to Hugging Face, with a card in `datasets/`. Pin a version when you
evaluate against one, so results stay comparable as it changes:

```python
from datasets import load_dataset

ds = load_dataset("<hf-org>/<dataset-name>", revision="v1.0")
```

## Contributing

Know of a paper, dataset, tool, or maintainer practice we should look at? Open an issue with
[share a resource](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=share-a-resource.yml), or
[propose a dataset](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=propose-a-dataset.yml).
See [CONTRIBUTING.md](CONTRIBUTING.md) for pull requests.

## License

Everything in this repository (code, data, and text) is released under the [MIT License](LICENSE).
Third-party datasets and cited sources keep their own licenses and terms, as listed in the catalog.

## Citation

If you use this work, please cite it using the metadata in [`CITATION.cff`](CITATION.cff)
(GitHub's "Cite this repository" button generates APA and BibTeX from it).

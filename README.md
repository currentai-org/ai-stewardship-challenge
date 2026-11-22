<div align="center">

# AI Stewardship Challenge

**Shared research findings and evaluation datasets for teams building in the AI Stewardship Challenge.**

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

This repository is the challenge's open evidence base: what we learn during discovery, and the
datasets that teams can use to build and evaluate their solutions. It is not the call for
applications. Call details will be published separately.

> [!NOTE]
> This repo is an early scaffold. Expect structure and content to change as findings land.

## Tracks

The challenge has three tracks. Findings and datasets are tagged with the track or tracks they
inform.

| Track | Focus | The question |
| --- | --- | --- |
| **A** | Portable contributor trust | How can trusted developers carry their reputation from one project to the next? |
| **B** | Onboarding ladder | How can new contributors find meaningful pathways to earn trust in a community? |
| **C** | Governance of agents | How can maintainers prepare their projects for autonomous agents that attempt to contribute? |

## What's here

```
.
├── research/     Findings from discovery: literature, interviews, data analysis
│   └── _template/    Copy this to start a new finding
├── datasets/     Catalog and dataset cards; large files live on Hugging Face
│   └── _template/    Copy this to start a new dataset card
└── .github/      Issue and PR templates
```

## Datasets

Datasets are documented in [`datasets/`](datasets/). Each one has a card in this repo. Small files
(under about 10 MB) can live next to the card; anything larger is published to Hugging Face and
linked from the card, so the Git history stays light.

| Dataset | Tracks | What it is | Where |
| --- | --- | --- | --- |
| _None yet_ | | | |

Once a dataset is on Hugging Face, loading it will look like this:

```python
from datasets import load_dataset

ds = load_dataset("<hf-org>/<dataset-name>", revision="v1.0")
```

Pin a `revision` when you evaluate against a dataset so results stay comparable as it changes.

## Research findings

Findings are written up in [`research/`](research/), one folder per finding, each with a short
summary, the method, what it means for the challenge, and its limitations.

| Finding | Tracks | Date |
| --- | --- | --- |
| _None yet_ | | |

## Contributing

Know of a paper, dataset, tool, or maintainer practice we should look at? Open an issue with
[share a resource](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=share-a-resource.yml), or
[propose a dataset](https://github.com/currentai-org/ai-stewardship-challenge/issues/new?template=propose-a-dataset.yml). To add a finding or a dataset
card directly, see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

Everything in this repository (code, data, and written findings) is released under the
[MIT License](LICENSE). Datasets derived from third-party sources note any upstream terms in their
cards.

## Citation

If you use this work, please cite it using the metadata in [`CITATION.cff`](CITATION.cff)
(GitHub's "Cite this repository" button generates APA and BibTeX from it).

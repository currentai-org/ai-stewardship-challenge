---
# Hugging Face dataset card metadata. Keep this block when publishing to the Hub.
# Reference: https://huggingface.co/docs/hub/datasets-cards
pretty_name: <Dataset name>
license: mit
language:
  - en
size_categories:
  - n<1K
tags:
  - ai-stewardship-challenge
  - open-source
  - track-a # keep the tracks this dataset informs: track-a, track-b, track-c
# configs:
#   - config_name: default
#     data_files:
#       - split: train
#         path: data/*.parquet
---

# <Dataset name>

<!-- One paragraph: what this dataset is, and why a challenge team would want it. -->

| | |
| --- | --- |
| **Tracks** | A / B / C |
| **Status** | draft / published |
| **Version** | v0.1 |
| **Hosted at** | this repo / `https://huggingface.co/datasets/<hf-org>/<dataset-name>` |
| **Maintainer** | <name or GitHub handle> |

## Intended uses

<!-- How teams should use it: building, evaluating, or benchmarking. Name the questions it can
help answer. Also say what it should NOT be used for. -->

## Structure

<!-- Files or configs, row counts, and how tables join. -->

| Field | Type | Description |
| --- | --- | --- |
| `example_field` | string | What it holds, units, and allowed values |

## Collection

- **Sources:** <!-- e.g. GitHub REST API, project mailing lists, maintainer interviews -->
- **Collection window:** <!-- YYYY-MM-DD to YYYY-MM-DD -->
- **Selection:** <!-- Which projects, repos, or people are included, and why -->
- **Processing:** <!-- Link to the script or notebook that builds it -->
- **Upstream terms:** <!-- Terms or licenses that apply to the source data -->

## People and privacy

<!-- What personal data is included, what was removed or pseudonymized, and how to request
removal. See datasets/README.md. -->

## Limitations

<!-- Known gaps, biases, and ways the data could mislead. -->

## Changelog

- **v0.1** (YYYY-MM-DD): First draft.

## Citation

```bibtex
@misc{<key>,
  title  = {<Dataset name>},
  author = {<Authors>},
  year   = {<YYYY>},
  howpublished = {\url{https://github.com/currentai-org/ai-stewardship-challenge}}
}
```

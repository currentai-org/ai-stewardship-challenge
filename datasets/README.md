# Datasets

Data that challenge teams can build and evaluate against. Two groups for now:

1. **[The forge panel](#the-forge-panel)**: GitHub and GitLab activity data indexed for the
   challenge's discovery work, on Artio.
2. **[Candidate datasets](#candidate-datasets)**: published third-party datasets the literature
   review found, with what each could be used to evaluate.

This catalog is a snapshot of the `sovereigntech` workspace on Artio, taken 2026-11-22. Nothing
here is hosted in the repo yet; datasets will move to Hugging Face as they are published, each
with a card in this folder.

## The forge panel

A panel of 137 open source repositories (117 on GitHub, 20 on gitlab.com), indexed directly from
the GitHub and GitLab APIs from 2023-01-01 onward (2022-01-01 for 20 GitHub pilot repositories),
and refreshed daily. The GitHub side is the 100-repository cohort from
[Afroz et al. 2026](https://arxiv.org/abs/2607.04003) plus the 20 pilots; the GitLab side is the
20 most-starred eligible gitlab.com projects. The two panels were selected differently, so compare
trends between forges, not levels.

**Privacy:** accounts are numeric forge ids only. No logins, names, emails, titles, bodies, or
commit messages are stored, only derived flags.

| Dataset | What it is | Main tables |
| --- | --- | --- |
| `forge_index` | The GitHub panel, from the GitHub GraphQL API, with counts validated against GitHub's own totals | `repo_universe`, `items`, `item_activity`, `commits`, `contributor_repo`, `repo_week`, `repo_files_history`, `coverage` |
| `forge_gitlab` | The GitLab counterpart, from the GitLab REST and GraphQL APIs | `gitlab_items`, `gitlab_item_activity`, `gitlab_commits`, `gitlab_members`, `gitlab_repo_snapshots` |
| `forge_unified` | One cross-forge layer with the same columns and definitions for both forges | `repos`, `items`, `activity`, `commits`, `contributor_month`, `contributor_repo` |
| `chaoss` | [CHAOSS](https://chaoss.community/) community health metrics computed the same way on both forges | `repo_month`, `repo_sustainability`, `newcomer_cohorts`, `forge_period`, `activity_hours`, `metric_catalog` |
| `evaluation_milestones` | First responsibility milestones per GitHub account and repository (first review, first label, first merge of someone else's work) | `contributor_milestones` |

Size of `forge_unified` on 2026-11-22:

| Table | Rows | GitHub | GitLab |
| --- | ---: | ---: | ---: |
| `repos` | 137 | 117 | 20 |
| `items` (issues and pull/merge requests) | 1,629,413 | 1,539,022 | 90,391 |
| `activity` (comments, reviews, events) | 20,542,077 | 19,974,159 | 567,918 |
| `commits` (default branch) | 1,447,372 | 1,295,695 | 151,677 |
| `contributor_repo` | 402,926 | 383,230 | 19,696 |

**Known gaps:** GitLab maintainer flags rest on current membership, so former maintainers are
missed; GitLab records no label, reopen, or ready-for-review events; activity beyond 430 nodes
per GitHub item is truncated (and flagged). See each table's description on Artio.

The [GitHub and GitLab panels compared](https://www.artio.so/sovereigntech/pages/forge-comparison)
page summarizes the panel and its CHAOSS metrics. Tables are addressed on Artio as
`sovereigntech.<dataset>.<table>`.

## Candidate datasets

From the literature review (`sovereigntech.prior_art.datasets`). **Status:** _ingested_ means a
copy is loaded on Artio under `sovereigntech.prior_art`; _candidate_ means not yet. Licenses are
as stated by the publisher; "unclear" means we could not find one.

### Track A: portable contributor trust

| Dataset | Owner | License | Coverage | Evaluation use | Status |
| --- | --- | --- | --- | --- | --- |
| [new_pullreq](https://zenodo.org/records/4837135) | Zhang, Yu, Gousios, Rastogi | CC BY 4.0 | 3.3M PRs, 95 features, 11,230 GitHub projects (to about 2020) | Pre-AI baseline for how much contributor history predicts PR acceptance | candidate |
| [npm ecosystem replication package](https://zenodo.org/records/13286685) | Meijer, Riveni, Rastogi | CC BY 4.0 | About 1.8M PRs and 2.1M issues from 20,052 npm projects; identities obfuscated | Does cross-project experience predict newcomer acceptance? The core premise of portable trust (also Track B) | candidate |
| [Good Egg validation reports](https://github.com/2ndSetAI/good-egg/tree/main/validation) | 2ndSetAI | MIT | 43 PR authors across 8 repos | Baseline AUC for history-based trust scores (0.647 reported) | candidate |
| [OpenRank devrank scores](https://docs.openrank.com/integrations/github-developers-and-repo-ranking) | Karma3 Labs | unclear | Users and repos near OP Stack seed repos (to 2024-09) | Do seeded EigenTrust scores predict newcomer PR acceptance better than merge rate? | candidate |
| [Vouch Book index](https://vouchbook.dev/data/vouch_book.json) | rosslazer/vouch-book | unclear | 148 repos with VOUCHED.td, 346 handles, 3,087 vouch edges (2026-04-17) | Adoption census of vouch lists; how much cross-repo "reputation" is fork duplication | candidate |
| [Public VOUCHED.td files](https://github.com/ghostty-org/ghostty/blob/main/.github/VOUCHED.td) | Each adopting project | Each repo's license; contains handles | Ghostty 392 vouched / 28 denounced, Pi 278 approved (2026-11-15) | Do vouch gates change PR volume, close rate, and newcomer conversion? (also Track B) | candidate |
| [Human Passport credential weights](https://docs.passport.xyz/building-with-passport/stamps/major-concepts/credential-map-and-weights) | Human Passport | unclear | All stamp weights, including GitHub activity stamps | How much weight a production Sybil scorer gives forge activity | candidate |
| [World of Code identity resolution](https://zenodo.org/records/3700859) | Fry, Dey, Karnauch, Mockus | CC BY 4.0 | 38M hashed author ids from about 2B commits across forges | Ground truth for how often one person has several identities across forges | candidate |
| [Software Heritage archive and graph](https://archive.softwareheritage.org/) | Software Heritage | Per release; content keeps original licenses | 461M origins, 6.4B revisions across forges | Cross-forge activity of the same author, for forge-agnostic signals | candidate |
| [Drupal.org issue credits](https://www.drupal.org/) | Drupal Association | unclear | Credits for individuals and organizations, code and non-code | Measuring credit for non-code work such as review and reproduction (also Track B) | candidate |

### Track B: onboarding and succession

| Dataset | Owner | License | Coverage | Evaluation use | Status |
| --- | --- | --- | --- | --- | --- |
| [Good First Issue longitudinal replication](https://doi.org/10.5281/zenodo.18847761) | Hoshikawa et al. | CC BY 4.0 | 37 repos, 406,826 issues, 1,117 newcomer GFI PRs (2021-2025) | Baseline of good-first-issue supply and newcomer merge rate | candidate |
| [Stalled PRs replication](https://doi.org/10.5281/zenodo.20599077) | Rahman et al. | CC BY 4.0 | 19 repos, 14,234 stalled PRs, 164,562 review comments | Baseline of contributor loss after a PR stalls | candidate |
| [Rust team membership](https://github.com/rust-lang/team) | Rust project | MIT OR Apache-2.0 | 174 teams; 685 member ids, 256 alumni ids, with join and leave dates from git history | Ground truth for who became a maintainer when, and succession | candidate |
| [Kubernetes OWNERS file histories](https://github.com/kubernetes/kubernetes) | Kubernetes / CNCF | Apache-2.0 | Reviewers, approvers, emeritus approvers per directory over git history | Role-promotion ground truth (reviewer to approver to emeritus) | candidate |
| [Clippy community-review gate](https://github.com/rust-lang/rust-clippy/issues?q=label%3AS-waiting-on-community-reviews) | Rust project | GitHub data; derived counts only | Clippy PRs since the gate started (around July 2026) | Natural experiment for review-before-attention gating | candidate |
| [Debian New Member records](https://nm.debian.org/public/stats/) | Debian | unclear | Active and historical NM processes with dates | Time to promotion in a non-GitHub ladder | candidate |
| [CNCF DevStats](https://k8s.devstats.cncf.io/) | CNCF | Code Apache-2.0; data unclear | Kubernetes and CNCF contributor and review dashboards | Cross-check only; Kubernetes uses it to define inactivity | candidate |

### Track C: agent governance

| Dataset | Owner | License | Coverage | Evaluation use | Status |
| --- | --- | --- | --- | --- | --- |
| [AIDev](https://huggingface.co/datasets/hao-li/AIDev) | Hao Li et al. | CC BY 4.0 | Over 456,000 PRs by 5 coding agents in 61,000 repos (later releases are larger) | Size of the agent PR load a gate would divert; acceptance gap (all tracks) | candidate |
| [AGENTS.md and CLAUDE.md census](https://huggingface.co/datasets/pzarzycki/agents-claude-md-github-census-2026) | Pawel Zarzycki | Per repository | 22,854 popular repositories, instruction file texts and metadata (2026-10-16) | AGENTS.md adoption baseline and attribution rules; candidate carrier for machine-readable agent rules | candidate |
| [GHAW-H (with GHAgentCI)](https://doi.org/10.5281/zenodo.22084012) | Ogenrwot, Delgado Cervantes, Kim, Businge | CC BY 4.0 | 15K+ workflow histories from 6K+ repos with agent invocations in CI | Declared agent integrations in CI as a provenance signal independent of commit trailers | candidate |
| [AI policies (Hora, Robbes, Zacchiroli)](https://doi.org/10.5281/zenodo.22212208) | Hora, Robbes, Zacchiroli | CC BY 4.0 | Top-10k GitHub repos; 281 coded policies; 92 policy files with revision history | Dated policy treatment for difference-in-differences on contribution outcomes (also Track B) | ingested |
| [AI policies (Hora, Robbes)](https://doi.org/10.5281/zenodo.20214334) | Hora, Robbes | CC BY 4.0 | 118 repositories with AI contributor policies, coded for allowance, disclosure, human in the loop | Policy-bearing repos and their rules; compare PR intake before and after (also Track B) | ingested |
| [open-source-ai-contribution-policies](https://github.com/melissawm/open-source-ai-contribution-policies) | Melissa Weber Mendonça and contributors | CC0 1.0 | 189 projects across GitHub, GitLab, Codeberg, and self-hosted forges | Seed list of non-GitHub policies for cross-forge comparison | ingested |
| [Making AI Visible replication package](https://doi.org/10.5281/zenodo.21059330) | Chen, Zimmermann, Trinkenreich | CC BY 4.0 | 29,624 repos screened; 385 with AI policies | Prior causal estimates of policy effects, to set expected effect sizes (also Track B) | candidate |
| [What Will Replace Pull Requests? supplement](https://doi.org/10.5281/zenodo.23598329) | Treude, Baltes | CC BY 4.0 | 50 gray-literature documents from 31 sources, coded for problems and mechanisms | Catalog of proposed and adopted mechanisms (also Track B) | candidate |
| [RedMonk AI policy directory](https://oss-ai-policies.netlify.app/) | RedMonk | unclear | 88 foundations and projects: stance, year, policy URL | Stance and year per organization; commit-tag fragmentation | candidate |
| [Linux kernel Assisted-by trailers](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git) | Linux kernel community | GPL-2.0 code; metadata public | Mainline commits; Assisted-by era 2026-01 to 2026-10 | Natural experiment on an honor-based disclosure tag: adoption, decay, and removal | candidate |
| [Codeberg Community issues](https://codeberg.org/Codeberg/Community/issues) | Codeberg community | unclear (user content) | Issues about the July 2026 terms change and AI rules | Moderation load created by a platform-level AI rule on a non-GitHub forge | candidate |
| [BoDeGHa ground truth](https://doi.org/10.5281/zenodo.4000388) | Golzadeh, Decan, Legay, Mens | CC BY 4.0 | 5,000 account-repository pairs labeled bot or human | Benchmark for bot flags on pre-LLM bots (also Track A) | candidate |
| [RABBIT ground truth](https://doi.org/10.5281/zenodo.12588134) | Chidambaram, Decan, Mens | CC BY 4.0 | 2,150 contributors labeled bot or human, plus activity datasets | Test whether activity-based classifiers catch LLM-agent accounts (also Track A) | candidate |

## Adding a dataset

Every dataset published for the challenge gets a folder here with a card (`README.md`), even when
the data itself lives on Hugging Face:

```
datasets/
├── README.md            This catalog
├── _template/
│   └── README.md        Dataset card template (Hugging Face compatible)
└── <dataset-name>/
    ├── README.md        The dataset card
    └── data/            Optional: small files only (under about 10 MB in total)
```

- **Names:** folder names are `kebab-case` and match the Hugging Face repo name.
- **Where data lives:** files under about 10 MB can sit in `data/`; anything larger goes to
  Hugging Face. The card uses the Hub's YAML front matter so the same file works in both places.
- **Versioning:** tag releases (`v1.0`, `v1.1`, ...). Bump the minor version for additions and
  the major version for anything that changes existing rows or fields, since teams will pin a
  version when they report results.
- **Data about people:** use only public data and record each source's terms; drop emails and
  contact details; prefer numeric ids or pseudonyms over handles; aggregate where individual rows
  add nothing; say how someone can ask to be removed.

Then add the dataset to this catalog and to the root [README](../README.md).

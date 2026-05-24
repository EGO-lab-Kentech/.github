# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

This is the **organization-level `.github` repository** for `EGO-lab-Kentech` — the **Electric Grid Optimization Lab** led by Prof. Kim Jip at KENTECH (Korea Institute of Energy Technology). Remote: `https://github.com/EGO-lab-Kentech/.github.git`.

GitHub treats this repo specially — files placed here apply org-wide as defaults across all repositories in the organization. Expect lab-relevant content (research code conventions, citation/funding info, reusable CI for power-systems / optimization workflows) over time.

At the time of writing, the repo is empty (no commits). Content is expected to be added over time. The conventional layout for an org `.github` repo:

- `profile/README.md` — rendered on the organization's GitHub landing page (`github.com/EGO-lab-Kentech`).
- `ISSUE_TEMPLATE/` and `PULL_REQUEST_TEMPLATE.md` — default issue/PR templates inherited by repos that don't define their own.
- `workflows/` — **reusable** workflows callable from other repos via `uses: EGO-lab-Kentech/.github/.github/workflows/<name>.yml@<ref>`. Note: this directory does NOT auto-run workflows the way a per-repo `.github/workflows/` does — files here are libraries, not triggers.
- `FUNDING.yml`, `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md` — org-wide community health defaults.
- `dependabot.yml` — org-wide Dependabot defaults.

## Working in this repo

- There is no build, test, or lint step — this is a documentation/config repo. Changes are validated by GitHub itself once pushed (e.g., the profile README renders, templates appear on new issues).
- When adding a reusable workflow, remember the path consumers reference is `EGO-lab-Kentech/.github/.github/workflows/<file>.yml` (the doubled `.github/` is correct and required by GitHub).
- Changes here have org-wide blast radius: a broken template or workflow can affect every repo in the org. Prefer opening a PR over pushing directly to `main`, even for small edits.

# APIsec Surface scan (customer shell)

One workflow file. It runs APIsec's org-wide Surface scan on this organization's runners by calling the reusable workflow published at `apisec-inc/poc-apisec-orchestrator` (tag `v1`). Nothing else to copy, and updates arrive automatically when APIsec moves the tag.

## Setup

1. Click **Use this template** and create this repository in the organization you want to scan.
2. Add org secrets `APISEC_TOKEN` (required) and `ORG_READ_TOKEN` (recommended; Contents: read and Metadata: read).
3. Add org variable `APISEC_ENDPOINT`.
4. Actions tab, **Run workflow**, tick `dry_run`, run once. The nightly schedule takes it from there.

Optional org variables: `APISEC_RUN_PROFILE` (`surface` default, or `legacy`), `APISEC_LLM_ENRICHMENT` (`1` to opt in; off by default), `THROUGHPUT` (1 to 6), `ORCHESTRATOR_RUNNER` (`github-hosted` default, or `self-hosted`), `TARGET_ORG`, `EXCLUDE_REPOS`, `APISEC_CLI_VERSION`.

Source code is read only on this organization's runners and never reaches APIsec. Only the Surface analysis manifest is uploaded.

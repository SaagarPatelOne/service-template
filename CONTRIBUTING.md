# Contributing

Thanks for contributing.

This template is meant for service-style repositories maintained by a solo owner or a small project set, so the default process is intentionally lightweight.

## Verify the template locally

Run from the repository root with Git and Python 3 (including `venv` and pip).
CI selects Python `3.x`. The first pre-commit run downloads its pinned hook
repository and installs a local hook environment, so initial setup needs network
access; no deployment, credentials, or running application are required.

```bash
python3 -m venv .venv
. .venv/bin/activate
python3 -m pip install pre-commit
pre-commit run --all-files --show-diff-on-failure
```

This is the baseline used by [CI](.github/workflows/ci.yml), configured in
[.pre-commit-config.yaml](.pre-commit-config.yaml). For a workflow/YAML-only change,
start with `pre-commit run check-yaml --all-files --show-diff-on-failure`, then run
the baseline before opening a PR. Whitespace/end-of-file hooks can edit tracked
files: review `git diff` and rerun after any fixes.

GitHub separately runs [Secret Scan](.github/workflows/secret-scan.yml), which
requires the workflow's Linux gitleaks installation. A local baseline pass does
not replace that check. This language-agnostic template has no application test,
typecheck, build, or browser lane yet; add stack-specific checks when a consumer
adds a runnable implementation.

## Before you open a pull request

- Keep the change focused.
- Explain the problem being solved and the expected outcome.
- Include validation notes, even if they are manual.
- Call out deployment, migration, or rollback impact when relevant.
- Call out risks, tradeoffs, or follow-up work.

## Before you open an issue

- Search for an existing issue first.
- For bugs, include exact reproduction steps and expected behavior.
- For feature requests, explain the problem and the user value.
- For operational issues, include impact, scope, and affected environments.

Repository-specific docs can override this file when a project needs more detail.

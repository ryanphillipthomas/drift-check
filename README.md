# Drift Check (moved)

> **This repository is deprecated as the Action home.**
>
> Drift Check now lives in **[`ryanphillipthomas/ryanthomas-tools`](https://github.com/ryanphillipthomas/ryanthomas-tools)** (desk tooling monorepo).
>
> Prefer:
> ```yaml
> - uses: ryanphillipthomas/ryanthomas-tools@main
> ```
>
> Existing `uses: ryanphillipthomas/drift-check@v1` pins **keep working** for now — the Action code here is frozen for compatibility. New work happens in `ryanthomas-tools`.

---

## What it does

Dependency-free GitHub Action that blocks design drift (raw visual values + invalid design-token overrides). Reads only the checked-out repository; no telemetry.

## Migration

| Before | After |
|--------|--------|
| `ryanphillipthomas/drift-check@v1` | `ryanphillipthomas/ryanthomas-tools@main` (or a future tag) |

Docs, scanner source, and Action entrypoint: see the [ryanthomas-tools README](https://github.com/ryanphillipthomas/ryanthomas-tools#drift-check).

## Legacy quickstart (still valid on this repo)

```yaml
name: drift-check
on: pull_request

permissions:
  contents: read

jobs:
  drift-check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: ryanphillipthomas/drift-check@v1
```

Defaults (unchanged): parent namespace `focx`; token path `design/tokens/{namespace}/tokens.json`; scan dirs `apps`, `packages`; common web extensions.

## Local (legacy path)

```sh
node tools/drift-check/index.mjs
```

Prefer cloning / running from `ryanthomas-tools` going forward.

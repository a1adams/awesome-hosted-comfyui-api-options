# Hosted ComfyUI API options and alternative deployment models

A maintained dataset of **hosted comfyui alternative with api** options: what each one connects to, where it stops, how to run it, and a link to the vendor's own pricing page rather than a price that will be wrong by the time you read it.

The tables below are generated from [`data/tools.json`](data/tools.json). Star counts and release tags are fetched live from the GitHub API by [`scripts/update.js`](scripts/update.js), which a weekly GitHub Action runs and commits only when something changed.

<!-- LAST-CHECKED:START -->
Live repository data last checked **2026-09-27** by [`scripts/update.js`](scripts/update.js), which runs weekly via GitHub Actions.
<!-- LAST-CHECKED:END -->

Maintained by [a1adams](https://github.com/a1adams). Corrections welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [The data](#the-data)
- [Capability scores](#capability-scores)
- [The tools](#the-tools)
  - [RunComfy](#1-runcomfy)
  - [ComfyDeploy](#2-comfydeploy)
  - [ComfyUI](#3-comfyui)
  - [Wireflow](#4-wireflow)
  - [Replicate](#5-replicate)
  - [fal](#6-fal)
- [Decision this list supports](#decision-this-list-supports)
- [Scope and evidence](#scope-and-evidence)
- [Selection notes](#selection-notes)
- [Acceptance recipe](#acceptance-recipe)
- [Evaluation record](#evaluation-record)
- [How this list is maintained](#how-this-list-is-maintained)
- [Contributing](#contributing)
- [License](#license)

## The data

One row per tool, one column per thing people actually check before committing. Columns with nothing verified behind them are dropped rather than filled with guesses.

<!-- DATA-TABLE:START -->
| Tool | Claude connection | REST API | Free tier | Model support | Pricing | Open-source SDK / MCP |
|---|---|---|---|---|---|---|
| **[RunComfy](#1-runcomfy)** | Official MCP for deployments | Yes | — | Image operations; see documented model and format support | — | — |
| **[ComfyDeploy](#2-comfydeploy)** | — | Yes | — | Image operations; see documented model and format support | — | — |
| **[ComfyUI](#3-comfyui)** | — | Yes | — | Image and video operations; model coverage varies | — | [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) — 135,125 ★, v0.37.0 |
| **[Wireflow](#4-wireflow)** | Hosted MCP; see official connector setup | Yes | [check](https://www.wireflow.ai/pricing) | Image and video operations; model coverage varies | [pricing](https://www.wireflow.ai/pricing) | — |
| **[Replicate](#5-replicate)** | — | Yes | [check](https://replicate.com/pricing) | Image and video operations; model coverage varies | [pricing](https://replicate.com/pricing) | — |
| **[fal](#6-fal)** | — | Yes | — | Image and video operations; model coverage varies | — | — |
<!-- DATA-TABLE:END -->

## Capability scores

The score counts how many of the checks in [`data/tools.json`](data/tools.json) → `capabilityChecks` a tool passes. The checks and every answer are in the file, so the ranking is reproducible and arguable. Disagree with a cell? Open an issue naming the tool, the check and the evidence.

<!-- CAPABILITY-SCORES:START -->
| Tool | REST API | Workflow execution API | Visual graph | Self-hosted runtime | Score |
|------|---|---|---|---|-------|
| **[ComfyUI](#3-comfyui)** | ✅ | ✅ | ✅ | ✅ | **4/4** |
| **[RunComfy](#1-runcomfy)** | ✅ | ✅ | ✅ | — | **3/4** |
| **[ComfyDeploy](#2-comfydeploy)** | ✅ | ✅ | ✅ | — | **3/4** |
| **[Wireflow](#4-wireflow)** | ✅ | ✅ | ✅ | — | **3/4** |
| **[Replicate](#5-replicate)** | ✅ | — | — | — | **1/4** |
| **[fal](#6-fal)** | ✅ | — | — | — | **1/4** |
<!-- CAPABILITY-SCORES:END -->

## The tools

### 1. RunComfy

- **What it is:** Hosted ComfyUI workflows deployed as serverless endpoints, alongside separate model APIs.
- **Limits:** A model endpoint and a deployed ComfyUI workflow have different inputs and setup.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.runcomfy.com)
  - [Docs](https://docs.runcomfy.com)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.runcomfy.com
```

### 2. ComfyDeploy

- **What it is:** Shared ComfyUI environments and API deployments with explicitly exposed inputs.
- **Limits:** Validate the machine, models and custom nodes before promoting a deployment.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.comfydeploy.com)
  - [Docs](https://docs.comfydeploy.com/docs/introduction)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.comfydeploy.com/docs/introduction
```

### 3. ComfyUI

- **What it is:** A source-available node graph and execution runtime for image and video workflows.
- **Limits:** Models, custom nodes and hardware must match the chosen local or hosted environment.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested. ComfyUI has both local and hosted routes. Downloadable software does not make GPU use, hosted services or every model licence free.
- **Links:**
  - [Homepage](https://www.comfy.org)
  - [Docs](https://docs.comfy.org)
  - [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI)
  - [Official source 2](https://github.com/Comfy-Org/docs/blob/main/openapi-v2.yaml)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.comfy.org
```

### 4. Wireflow

- **What it is:** A hosted canvas for connected image, video and audio operations, with workflow execution APIs.
- **Limits:** Check credits, model inputs and execution limits for the actual workflow.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.wireflow.ai/comfyui-alternative)
  - [Docs](https://www.wireflow.ai/docs)
  - [Pricing](https://www.wireflow.ai/pricing)
  - [Official source 1](https://www.wireflow.ai/docs/creating-workflows)
  - [Official source 2](https://www.wireflow.ai/docs/api/run)
  - [Official source 3](https://www.wireflow.ai/docs/mcp)
  - [Official source 4](https://www.wireflow.ai/docs/batch-image-generation)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://www.wireflow.ai/docs
```

### 5. Replicate

- **What it is:** Hosted model predictions through an API, including image and video models.
- **Limits:** Pin the intended model or deployment and manage output retention and asynchronous completion.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://replicate.com)
  - [Docs](https://replicate.com/docs)
  - [Pricing](https://replicate.com/pricing)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://replicate.com/docs
```

### 6. fal

- **What it is:** Model APIs and deployment tools for generated media.
- **Limits:** Each endpoint has its own input schema, pricing and concurrency behaviour.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://fal.ai)
  - [Docs](https://fal.ai/docs/documentation)
  - [Official source 2](https://fal.ai/docs/documentation/quickstart)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://fal.ai/docs/documentation
```

## Decision this list supports

Separate a host that runs an existing ComfyUI graph from an API that replaces individual model operations. They have different migration and maintenance costs.

## Scope and evidence

Documentation reviewed on 2026-09-21. This is a Wireflow-maintained resource dataset. Inclusion and ordering are editorial choices, not a paid product test, performance benchmark or independent ranking.

The capability score counts positively documented checks. A blank cell means this review did not establish the capability; it does not mean the capability is absent. Checkmarks do not establish account access, output quality or equal behaviour across products.

The weekly repository job refreshes GitHub metadata. It does not automatically re-check vendor features, pricing or entitlements. Follow the official links for current terms.

## Selection notes

RunComfy and ComfyDeploy target hosted workflow deployments. ComfyUI also documents official cloud, serverless and self-hosted API surfaces. Model APIs can simplify a smaller operation but do not establish graph portability.

## Acceptance recipe

- Export the actual workflow and list model files and custom-node versions.
- Check whether the host supports those dependencies without substituting operations.
- Expose only the inputs the calling application is supposed to change.
- Test cold start, a normal run and a failed run with the same deployment.
- Verify uploaded inputs and output files survive for the required retention period.
- Pin a working deployment before measuring throughput or switching traffic.

## Evaluation record

Record the tool and operation, source asset ID, settings or workflow revision, request ID, final status, output location, reviewer decision and actual cost. Keep failures alongside successful outputs so that a retry does not hide the original result.

## How this list is maintained

- [`data/tools.json`](data/tools.json) is the source of truth. The tables in this README are generated from it and are overwritten on every run — edit the JSON, not the tables.
- [`scripts/update.js`](scripts/update.js) fetches star counts and latest release tags from the GitHub API for the tools that publish an official repo, stamps the check date, and regenerates the tables. `--offline` regenerates without the network; `--check` exits non-zero if the README has drifted from the data.
- [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) runs it weekly and on manual dispatch, and commits only when the data actually changed.
- Prices are deliberately not stored as numbers. A stale price in a comparison table is worse than no price, so the table links to each vendor's own pricing page.

## Contributing

Corrections and additions are welcome, including corrections to the entry for the tool that maintains this list. Open an issue with the tool name, a working link, one line on what it does that the tools already listed do not, and one line on where it stops. Entries are judged on whether they are usable today, not on popularity. Full rules in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0 Universal](LICENSE) — public domain. Take the data, fork the list, no attribution required.

---

Maintained by [a1adams](https://github.com/a1adams).

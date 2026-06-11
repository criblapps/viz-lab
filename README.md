# Viz Lab

A [Cribl App Platform](https://docs.cribl.io/stream/app-platform/) app for [Cribl Search](https://cribl.io/products/search/). It is a full **Search** workspace in the browser: run **KQL**, inspect **Events** and **Fields**, turn results into **Charts**, and compose **Dashboards** with variables, tabs, imports (Splunk XML, Cribl JSON, Viz Lab JSON), and collaboration where your org enables it. Light/dark **theme** follows Cribl when the app is embedded; you can override it when running standalone.

## What it does

- **KQL search** — Editor with time range, sampling, history, saved searches, CSV/NDJSON export, optional streaming rows, and annotations. Optional **Cribl Copilot** flows (query/dashboard conversion) call Cribl AI when your deployment allows it.
- **Results panes** — Switch between **Events** (raw rows), **Fields** (column stats), and **Chart**. Map result columns to visualization channels; many chart types include a **sample query** you can load and re-run.
- **Charts** — **46** built-in visualizations (bars, lines, gauges, heatmaps, Sankey, geo, security views such as MITRE ATT&CK, and more). Extend the catalog with **+ Plugins** from the gallery or a trusted ESM URL (plugin code runs with full page permissions—only install sources you trust).
- **Dashboards** — Drag-and-drop layout, parent/child searches, variables, versions, and export. **Knowledge** shortcuts jump to lookups, parsers, regexes, Grok, and macros using the same APIs as native Search.

Dataset administration stays in native Cribl Search; Viz Lab focuses on running searches and building visuals on top of data you already have access to.

## Installing

1. In [Cribl Cloud](https://cribl.io/cloud/), open **Cribl Search**, go to **App Platform → Add App → Import from Git**, and paste this URL: `https://github.com/criblapps/viz-lab`.
2. Open **Viz Lab** from the app launcher. No extra app configuration is required for everyday search and dashboards.

**Private Git repositories** — Use your platform’s Git import flow with credentials (for example an HTTPS URL that includes a personal access token), and pick a **branch** if you need two-way sync; tags are typically read-only.

**Admins** — Outbound calls are declared in [`default/proxies.yml`](default/proxies.yml). The repo ships with an allowlist for **Cribl Copilot** (`ai.cribl.cloud`). To use **live** Splunk REST pulls from the Search or Dashboard converter, uncomment and edit the Splunk host blocks in that file before you package or import the app so the platform proxy can allow those hosts.

## More detail

In-repo feature tour, visualization list, and plugin notes: [`default/README.md`](default/README.md).

## License

Licensed under the **Apache License, Version 2.0**. See [LICENSE](LICENSE).

# MySci — Internal Operations Platform (Wireframe)

A high-fidelity HTML wireframe for MySci, Molecular You's internal platform for managing biomarker data, scoring, and report operations across Science and Ops teams.

## Overview

MySci is a single-file interactive wireframe (`index.html`) built with vanilla HTML, CSS, and JavaScript. It simulates two team workflows — **Operations** and **Science** — with role-based access gating and realistic demo data throughout.

## Features

### Operations team
- **Samples** — browse kits by timepoint, lab, and status (complete, analyzing, compromised, rerun)
- **Build a report** — select a sample, choose proteomics/metabolomics datasets with assay conflict detection, generate scores, save or send to MYHI
- **Compare reports** — load two saved reports side by side with system/process/biomarker score diffs
- **Assay catalog** — view and edit assay identifiers, lot numbers, and expiry dates
- **Data versions** — track versioned releases of the scoring data model

### Science team
- **Reference ranges** — browse, filter, and edit biomarker reference ranges by lab, sex, age, and cycle phase
- **Associations** — view biomarker-to-system-to-process associations in table or interactive flowchart view
- **Weight adjustments** — interactive weight tree with per-biomarker/process multiplier, colour trigger, and direction controls
- **Compare weight profiles** — side-by-side weight diff with individual patient impact and population KDE overlay chart
- **Scoring params** — configure global score cutoffs and colour thresholds
- **Analytics** — summary tables and score histograms across systems, processes, and biomarkers

### Governance (both teams)
- **My drafts** — track submitted, rejected, and in-review changes
- **Review queue** — approve or reject pending changes with diff view
- **Audit log** — full history of approved changes with revert actions

## Tech

- Vanilla HTML/CSS/JS — no build step, no dependencies to install
- [Chart.js 4.4.1](https://www.chartjs.org/) via CDN (KDE overlay chart)
- Single file: `index.html`

## Usage

Open `index.html` directly in a browser — no server required.

Or if hosted via GitHub Pages:

```
[https://windyzn.github.io/mysci-design/](https://windyzn.github.io/mysci-design/)
```

### Login
Select a role (**Contributor** or **Admin**) and a team (**Ops** or **Science**). Admin role unlocks the **Send to MYHI** action in report workflows.

## Notes

This is a wireframe prototype — all data is hardcoded and no API calls are made. It is intended for internal design review and stakeholder walkthroughs only.

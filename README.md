# MySci — Developer Handoff

Internal operations platform for Molecular You. Single-page HTML wireframe; no build step required.

---

## Project structure

```
/
├── index.html         # Full application — all panels, styles, and logic in one file
├── tokens.css         # Design tokens (colours, typography, spacing, radius)
└── logos/
    ├── Molecular_You_MYLigature__Turquoise.svg    # Sidebar logo + favicon
    └── Molecular_You_MYLigature__Dark_BlueGray.svg  # Login card logo
```

---

## Running locally

Open `index.html` directly in a browser — no server or build step needed. Logo SVGs load via relative paths so keep the folder structure intact.

---

## What is MySci?

MySci is an internal tool used by two teams at Molecular You:

- **Operations** — manages sample batches, builds and compares patient reports, maintains the assay catalog
- **Science** — manages biomarker reference ranges, system/process/biomarker associations, scoring weights, and analytics

Users select their team at login. The sidebar nav and available panels change depending on which team is active.

---

## What is MYHI?

MYHI (Molecular You Health Insights) is the patient-facing platform. MySci can push finalised reports to MYHI for publishing. This action is admin-only and gated by the `currentRole` variable set at login.

---

## Authentication model (wireframe)

Login is simulated — no real auth. Two roles are available via the login dropdown:

| Role | Permissions |
|------|-------------|
| Contributor | View and edit; cannot send to MYHI |
| Admin | Full access including send to MYHI |

Role gating is applied via `applyRoleGating()` and checks `currentRole`.

---

## Panels

| Panel ID | Team | Description |
|----------|------|-------------|
| `batches` | Ops | Sample batch list with status and filters |
| `buildreport` | Ops | Dataset selection + score generation for a sample |
| `comparereports` | Ops | Side-by-side comparison of two saved reports |
| `assaycatalog` | Ops | Assay identifiers, labs, lot numbers |
| `refrange` | Science | Biomarker reference ranges with edit/review flow |
| `systems` | Science | Biomarker–process–system association table and flowchart |
| `weights` | Science | Interactive weight adjustment tree |
| `cmpprofiles` | Science | Compare two weight profiles with population distribution chart |
| `scoringparams` | Science | Global scoring parameters and colour cutoffs |
| `summary` | Science | Population-level summary statistics |
| `histograms` | Science | Score distribution histograms |
| `drafts` | Both | Current user's draft and submitted changes |
| `review` | Both | Pending changes awaiting approval |
| `audit` | Both | Log of approved changes with revert option |
| `dataversions` | Both | Data version history |

---

## Key design decisions

- **No teal on white** — `--color-brand-teal` (`#8CCFCF`) is only used on dark backgrounds (sidebar) or as a border/accent, never as text on white
- **Max 3 colours per component** — status pills, cards, and table rows follow this rule
- **Monospace for data** — barcodes, version numbers, and numeric biomarker values use `--font-mono`
- **Bold used sparingly** — `font-weight: 700` is reserved for active states, headings, and stat values; body text and table rows are regular weight

---

## Dependencies

| Library | Version | Usage |
|---------|---------|-------|
| Chart.js | 4.4.1 | KDE overlay chart in Compare profiles |
| Lato (Google Fonts) | — | Primary typeface |

Both loaded via CDN — no npm install needed.

---

## Browser support

Modern evergreen browsers. No IE support required.
# Misdiagnosis & Health Equity — Tableau Dashboard Plan

**Working title:** *Missed: How Diagnostic Error Falls Hardest on Women and People of Color*
**Focus conditions:** Sepsis and Cancer (within the national "Big Three" picture)
**Purpose:** Portfolio piece demonstrating Tableau skills — data storytelling, calculated fields, dashboard actions, accessible design.

---

## The story arc (three-act structure)

1. **The scale** — diagnostic error is a massive, under-recognized public health problem.
2. **The pattern** — a small set of conditions (including sepsis and cancer) cause most of the harm, and some are missed far more often than others.
3. **The disparity** — women and people of color bear a disproportionate share of that harm.

The honest through-line: the national study quantifies *how often* conditions are missed and *how much harm* results; the equity sources show *who* absorbs that harm. The dashboard connects the two.

---

## Data sources (all in /data)

| File | Contents | Primary source |
|---|---|---|
| `1_disease_error_harm.csv` | Per-disease incidence, error rate, serious harms (15 diseases) | Newman-Toker et al., *BMJ Qual Saf* 2023, Table 1 |
| `2_national_scale.csv` | Headline totals (795K harms, etc.) | Same + KFF/NBC 2024 |
| `3_demographic_disparities.csv` | Women/minority disparity multipliers | KFF Health News/NBC 2024 |
| `4_sepsis_context.csv` | Why sepsis is hard to diagnose | Vincent, *PLOS Medicine* 2016 |
| `5_race_sex_disparities.csv` | Race/sex disparities for sepsis & cancer | ACS; peer-reviewed research |
| `6_stage_at_diagnosis.csv` | Early- vs late-stage diagnosis by race | ACS; PMC10726717 |

**Data honesty note (important for a portfolio):** The national per-disease table is *not* broken down by race or sex. Present the two layers side by side and let the viewer connect them. Being explicit about this in a caption is a *strength* — it signals analytical maturity.

---

## Recommended layout (single dashboard, ~1000–1200px wide, vertical scroll)

```
+-------------------------------------------------------------+
|  TITLE + one-line thesis                                    |
|  "795,000 Americans die or are disabled by misdiagnosis     |
|   each year - and women and people of color are 20-30%      |
|   more likely to be misdiagnosed."                          |
+--------------+--------------+--------------+-----------------+
|  795,000     |   371,000    |   ~1 in 4    |   20-30%        |  <- KPI band (act 1)
| serious harms|    deaths    |hospital deaths| more likely     |
+--------------+--------------+--------------+-----------------+
|  ACT 2 - WHICH CONDITIONS?                                  |
|  Horizontal bar: serious harms by disease (sorted).         |
|  Highlight Sepsis + the 5 cancers; grey out the rest.       |
+-----------------------------+-------------------------------+
|  SEPSIS SPOTLIGHT           |  CANCER SPOTLIGHT             |  <- act 2 detail
|  79K harms/yr, 9.9% missed. |  Lung cancer missed 22.5%.    |
+-----------------------------+-------------------------------+
|  ACT 3 - WHO BEARS IT (disparities, files 5 & 6)           |
|  Grouped bars: Black vs white early-stage diagnosis;        |
|  sepsis mortality 2x; breast cancer death +38%.             |
+-------------------------------------------------------------+
|  Footer: sources, methodology note, your name/links         |
+-------------------------------------------------------------+
```

---

## Chart-by-chart build notes

**KPI band (BANs).** Big numbers from `2_national_scale.csv`. Keep to 4 tiles.

**"Serious harms by disease" (hero chart).** Bar chart, `disease` sorted descending by `serious_harms_k`. Calculated field for color:
```
IF [focus_flag] <> "" THEN "Focus (Sepsis / Cancer)"
ELSE "Other dangerous disease" END
```
Grey for "Other," strong accent for "Focus."

**Error rate vs. harm (optional scatter).** `error_rate_pct` x `serious_harms_k`, size = incidence. Shows sepsis is missed "only" 9.9% of the time but ranks #2 in total harm because it's so common.

**Sepsis panel.** Bars from `4_sepsis_context.csv` — 86% of physicians say sepsis is easily misattributed; 45% admit missing it.

**Cancer panel.** Bars of `error_rate_pct` for the five cancers; lung cancer (22.5%) towers over prostate (2.4%).

**Disparities (Act 3).** From `5_race_sex_disparities.csv` and `6_stage_at_diagnosis.csv`. Grouped bars comparing Black vs. white early-stage diagnosis (breast 58% vs 68%; cervical 41.7% vs 53.3%), plus relative-risk bars (sepsis mortality 2x; breast cancer death +38%).

---

## Interactivity to show off (pick 2–3)

- Category filter (Vascular / Infection / Cancer) as highlight buttons.
- Dashboard action: click a disease bar → filters the spotlight panels.
- Parameter to toggle top chart between "serious harms" and "error rate."

---

## Design & accessibility

- Muted greys for context, one strong accent for focus conditions; reserve red for the disparity act. Avoid red/green together (colorblind safety).
- Keep titles factual, not sensational — this is real mortality data. Cite sources visibly.
- Every chart gets a plain-language takeaway title, not just "Serious Harms by Disease."

---

## Suggested build order in Tableau

1. Connect all six CSVs (each as its own data source).
2. Build the four BANs from `2_national_scale.csv`.
3. Build the hero bar chart + the `focus_flag` color field.
4. Build sepsis and cancer spotlight sheets.
5. Build the disparities sheets from files 5 & 6.
6. Assemble the dashboard, add one highlight action + one parameter.
7. Write takeaway titles + source footer.

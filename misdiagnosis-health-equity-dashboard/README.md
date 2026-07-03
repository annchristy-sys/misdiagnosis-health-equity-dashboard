# Missed: Diagnostic Error & Health Equity

**Question:** Diagnostic errors seriously harm ~795,000 Americans a year.
Who bears that harm — and are women and people of color affected differently?

**Focus:** Sepsis and cancer, within the national "Big Three" (vascular,
infection, cancer) picture.

## Data (see /data — every CSV has source columns)
| File | Contents | Source |
|------|----------|--------|
| 1_disease_error_harm.csv | Per-disease error rates & serious harms (15 diseases) | Newman-Toker et al., BMJ Qual Saf 2023 |
| 2_national_scale.csv | Headline national totals | BMJ Q&S 2023 + KFF/NBC 2024 |
| 3_demographic_disparities.csv | Women/minority disparity figures | KFF Health News / NBC 2024 |
| 4_sepsis_context.csv | Why sepsis gets missed | Vincent, PLOS Medicine 2016 |
| 5_race_sex_disparities.csv | Race/sex disparities (sepsis, cancer) | ACS; peer-reviewed research |
| 6_stage_at_diagnosis.csv | Early- vs late-stage diagnosis by race | ACS; PMC10726717 |

## Status
In progress — interactive Tableau dashboard live soon.
Cleaned datasets and methodology available now.

## Key findings (so far)
- Sepsis is the #2 single cause of misdiagnosis harm (79k/yr) despite a ~10% error rate — it's just that common.
- Black Americans die of sepsis at ~2x the rate of white Americans.
- Black women: 38% higher breast cancer death rate, caught early only 58% of the time vs. 68% for white women.

## Note on the data
Diagnostic error isn't tracked by race in national data. Its fingerprints show
up in who dies and who is caught too late — which is what files 5 and 6 capture.

## Docs
- docs/dashboard_design_plan.md — layout, charts, story flow
- docs/project_and_portfolio_plan.md — build sequence + how to publish now

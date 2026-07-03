# Misdiagnosis Project — 2-Week Build Plan + How to Publish Now

You're applying now but the project needs 1–2 weeks. The answer isn't "wait" — it's **publish a live, honest work-in-progress today, then update the same public links as you build.** A public portfolio is a changelog, not a monument.

---

## Part 1 — The data fix (the race/gender gap)

The original CSVs described *how often* conditions are missed nationally, but not *who* is harmed by race and sex. That's now fixed with two files sourced from peer-reviewed research and the American Cancer Society:

- **`5_race_sex_disparities.csv`**:
  - Sepsis: Black Americans die from sepsis ~**2x** the rate of white Americans (risk range 1.5–3.5x).
  - Breast cancer: Black women have a **38% higher death rate** despite **5% lower incidence**; under 50 the death rate is **2x**; **2x** as likely to get aggressive triple-negative subtypes.
  - Cervical cancer: Black women have **1.18x** the odds of an advanced-stage diagnosis.
- **`6_stage_at_diagnosis.csv`** (grouped-bar ready):
  - Breast cancer diagnosed early: **58% of Black women vs. 68% of white women.**
  - Cervical cancer early-stage: **41.7% Black vs. 53.3% white women.**

**Framing (a strength, not a weakness):** A clean "misdiagnosis rate by race for sepsis" number mostly doesn't exist. What *does* exist — mortality gaps, late-stage diagnosis rates — are the measurable footprints of diagnostic inequity. Say so in a caption:

> *"Diagnostic error isn't tracked by race in national data. But its fingerprints show up in who dies and who gets caught too late — Black patients are diagnosed later and die more often from the same diseases."*

---

## Part 2 — Git & GitHub for a first-timer

You need ~6 button-clicks, no command line.

1. Free account at github.com.
2. Install **GitHub Desktop** — buttons for everything, skip the terminal.
3. Create a repo `misdiagnosis-health-equity-dashboard`. Check "public" and "add a README."

**The only workflow:** put files in the repo folder → in GitHub Desktop write a short summary → **Commit** → **Push**. Done; your public repo updates.

**Repo layout (this zip already matches it):**
```
misdiagnosis-health-equity-dashboard/
├── README.md
├── data/       <- the 6 CSVs
├── docs/       <- these two plans
├── images/     <- dashboard screenshots (add later)
└── notebooks/  <- any cleaning code (add later)
```

---

## Part 3 — Two-week build sequence

**Days 1–2 (makes it public immediately):**
- Create the GitHub repo, upload this whole folder.
- README already has the question, sources, and an "in progress" note.
- Make a free **Tableau Public** account.
- You are now publishable.

**Days 3–7 (build the dashboard):**
- Connect the CSVs in Tableau Public.
- Order: 4 KPI tiles → "serious harms by disease" hero chart → sepsis & cancer spotlights → race/sex disparity charts from files 5 & 6.
- Publish to Tableau Public even in rough form; overwrite as you refine.

**Days 8–12 (polish + write-up):**
- Takeaway chart titles, source footer, one highlight action.
- Finish README findings; add screenshots to /images.

**Days 13–14 (buffer):** proofread, get one person to review.

---

## Part 4 — How to link it RIGHT NOW (do all four today)

1. **Publish the GitHub repo** (public) with the README. A repo with a clear question, real sourced data, and methodology is a legitimate portfolio artifact even before the dashboard exists. Résumé-safe today.
2. **Give this project its own page/card** on your portfolio site, linking to the repo, with a small honest status line: *"Interactive Tableau dashboard in progress (live [date])."*
3. **Stop linking Google Drive.** Replace it with the GitHub link; add the Tableau Public link once the viz is up.
4. **In applications:** *"Currently building a Tableau dashboard on diagnostic-error health disparities — repo and data here: [link]."*

---

## The mindset

Recruiters care that you can frame a question, handle real data honestly, and communicate a finding. This project does all three. Publishing it half-built but clearly-in-motion is *better* than a hidden "perfect" version — it proves you ship.

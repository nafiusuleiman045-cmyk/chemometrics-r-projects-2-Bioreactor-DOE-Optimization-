# Design of Experiments for Bioreactor Yield Optimization

A full factorial Design of Experiments (DOE) study to identify which process factors drive yield in a batch bioreactor, with a follow-up plan for response-surface optimization.

## Objective
A **2⁴ full factorial design** (16 runs) was used to screen four controllable factors affecting bioproduct yield:
- **A** — Feed rate (slow vs. medium)
- **B** — Initial inoculant size (300 g vs. 700 g)
- **C** — Feed substrate concentration (40 g/L vs. 60 g/L)
- **D** — Dissolved oxygen set-point (4 mg/L vs. 6 mg/L)

## Method
- Full factorial linear model (`lm`) with all main effects and interactions
- Significance testing via three independent methods: confidence-interval plot, Lenth plot, Daniel (half-normal) plot
- A **2⁴⁻¹ fractional factorial** (Resolution IV, 8 runs) proposed as a cheaper screening alternative, with full confounding/aliasing structure and projectivity analysis
- Blocking check for a day-to-day effect
- Curvature diagnostics and a **Central Composite Design (CCD)** proposed as the response-surface follow-up

## Key Findings
- **Inoculant size (B)** is the dominant factor (effect = +18.0), followed by the **B×C interaction** (+12.75) and **substrate concentration (C)** (+8.0)
- Recommended settings — slow feed rate, 700 g inoculant, 60 g/L substrate, 4 mg/L oxygen — predict a **~60% yield improvement** (≈60 → ≈96 g/batch) over baseline
- Strong evidence of **curvature**: a follow-up rotatable CCD (14 runs) on inoculant size and substrate concentration is proposed to locate the true optimum, since a two-level design can't estimate quadratic effects

## Tools
R, FrF2, rsm, BsMD

## Files
- `bioreactor_doe_analysis.Rmd` — full analysis, knit with `output: github_document`
- `bioreactor_factorial_data.csv` — dataset (add your own copy here; not included if restricted)

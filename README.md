# ABQE Synthetic Benchmark Dataset (v1.0)

This repository contains a **fully synthetic** resume–job description benchmark dataset used to evaluate **semantic sensitivity** and **factor-level variance** in automated resume screening / matching pipelines.

It accompanies a controlled experimental study performed with the **ATS Bias Quantification Engine (ABQE)**.

## What’s inside

- **3 synthetic job descriptions (JDs)**:
  - `jd1_text.txt` (Backend Java baseline)
  - `jd2_text.txt` (Paraphrased backend JD)
  - `jd3_text.txt` (Adjacent full-stack JD)

- **8 synthetic resumes** (`r1`–`r8`) designed to isolate one factor at a time:
  - Skill phrasing (`r1`, `r2`)
  - Resume structure (`r3`, `r4`)
  - Employment gap (`r5`, `r6`)
  - Degree origin (`r7`, `r8`)

- **24 experiment runs** (8 resumes × 3 JDs):
  - Per-run JSON files in `dataset/runs/`
  - Summary table in `dataset/metadata/runs.csv`
  - Resume-factor mapping in `dataset/metadata/resume_factors.csv`

## File layout

```
dataset/
  job_descriptions/
  resumes/
  runs/
  metadata/
```

## Schema (runs.csv)

Key fields:

- `run_id`: e.g., `r3_jd2`
- `resume_id`: `r1` … `r8`
- `jd_id`: `jd1` … `jd3`
- `pair_id`: which controlled pair the resume belongs to (`r1_vs_r2`, `r3_vs_r4`, …)
- `aggregate_mean_percent`
- `factor_effect_size`, `max_effect_size`
- `bootstrap_ci_95_percent` represented by `ci_low`, `ci_high`
- `stability_index`, `sensitivity_index`

## Ethics & Data disclaimer

- All resumes and job descriptions are **synthetic** and created solely for research/benchmarking.
- No real candidate data, proprietary ATS outputs, or production screening decisions are included.
- The dataset is intended to support **replication** and **methodological comparison** of resume–JD matching approaches.

## Citation

If you use this dataset, please cite it using the metadata in `CITATION.cff`.


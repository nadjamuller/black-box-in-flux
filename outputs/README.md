# Outputs directory

**Purpose:** Stores results, summaries, and figures from each run.

| File | Description |
|------|--------------|
| `flux_sweep_results.csv` | Raw results: one row per (flux, seed) combination with all metrics. |
| `flux_sweep_summary.csv` | Averaged metrics per flux level (baseline seeds). |
| `flux_sweep_results_all.csv` | Extended run including additional seeds `[5,11,101]`. |
| `plot_*.png` | Single-metric plots (mean values across seeds). |
| `overlay_*.png` | Overlay plots showing all seeds for each metric. |
| `metrics_*.csv` | Optional metrics from future runs. |

Each figure is generated automatically from the notebook; rerun the notebook to regenerate all files.

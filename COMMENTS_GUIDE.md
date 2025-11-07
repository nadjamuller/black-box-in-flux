
# COMMENTS & REPRODUCIBILITY GUIDE

Clear, friendly, reproducible. That’s our goal.

## 1) Notebook structure

Use this outline in every notebook:
1. **Title + Purpose** — one sentence in plain language.
2. **Prerequisites** — list packages and versions you used.
3. **Parameters** — all knobs (e.g., `DRIFT_RATE`) in one place.
4. **Run** — the actual simulation.
5. **Metrics** — what we measure and why (quick bullets).
6. **Results** — plots and a one-paragraph interpretation.
7. **Save outputs** — CSV/figures with filenames that include key params.
8. **What’s next?** — 2 bullets on follow-up ideas.

## 2) Commenting rules (short and sweet)

- **Markdown cells** tell the story. Keep sentences short.
- **Code comments** explain *why*, not *what*.
  - Good: `# slow detuning drift = "flux" we want to test`
  - Meh:  `# create array`
- **Docstrings** for functions: say inputs, outputs, and a one-line purpose.
- One idea per cell. Name plots clearly.

## 3) Naming

- Variables you tweak often: ALL_CAPS (`DRIFT_RATE`, `T_STEPS`).
- Functions: verbs (`run_with_drift`, `delay_embed`).
- Files: include the key param and date, e.g. `metrics_drift-2e-4_2025-11-06.csv`.

## 4) Randomness

- Set a fixed seed at the top: `np.random.seed(7)` so others can reproduce your plots.

## 5) Results notes

After each plot, add a **tiny note**:
- “As `DRIFT_RATE` increased, `LLE` rose from 0.03 to 0.09, and `echo_mean` from 0.02 to 0.08.”
- Keep numbers, not opinions.

## 6) Shareable checklist

Before sharing, confirm:
- [ ] All cells run top-to-bottom without manual edits
- [ ] You listed your `pip freeze` (or at least versions) once
- [ ] Output files are saved under `outputs/` with descriptive names
- [ ] You wrote 3–5 bullet conclusions anyone can skim

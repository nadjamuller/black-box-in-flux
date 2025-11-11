# Black Box in Flux 

https://doi.org/10.5281/zenodo.17574087

## Cite this work
If you use this repository, please cite the Zenodo record:

**Muller, N. (2025). *Black Box in Flux: v0.1.0 – First reproducible experiment*. Zenodo.**  
https://doi.org/10.5281/zenodo.17574087



This repo gives you a no-lab, laptop-only pipeline to probe links between *flux* (slow parameter drift) in an open quantum system and *chaos-like* behavior in black-box output time series.

## Quick start

1. **Create a fresh environment (recommended)**  
   ```bash
   # with conda
   conda create -n bbif python=3.10 -y
   conda activate bbif

   # or with uv / pipx you can adapt accordingly
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

   > If QuTiP takes long to compile, try installing wheels:
   > ```bash
   > pip install qutip
   > ```

3. **Open the notebook**  
   ```bash
   jupyter notebook black_box_in_flux_setup.ipynb
   ```

4. **Run all cells**. You’ll generate:
   - A simulated driven–dissipative qubit under a PRBS drive with slow drift (the *flux*).
   - Time series of an observable (⟨σ_z⟩) for black-box analysis.
   - Classical chaos diagnostics: delay embedding, Rosenstein LLE, permutation entropy, recurrence rate.
   - Quantum-specific proxy: Uhlmann fidelity between two evolutions with tiny Hamiltonian detuning (a Loschmidt-echo-like sensitivity).

5. **Sweep the flux**: adjust `DRIFT_RATE` and re-run to see how metrics change.
   Use the final cell to produce a one-figure summary comparing metrics across flux settings.

## What’s inside?

- `black_box_in_flux_setup.ipynb` — main notebook with everything in one place.
- `requirements.txt` — minimal Python dependencies.
- `README.md` — this file.

## Notes

- The notebook intentionally avoids extra analysis packages to keep installs minimal. 
- Metrics implementations are compact and educational rather than ultrafast; they are sufficient for proof-of-concept.
- If you hit performance limits, reduce trajectory length (`T_STEPS`) or embedding dimension (`EMB_DIM`).

## Repository layout
setup/            # helper scripts or modules
notebooks/      # main Jupyter notebooks
data/            # input/output data (sample included)
outputs/         # notebook outputs and figures
docs/            # notes and publications
tests/           # quick smoke tests
configs/         # parameters and configuration files




v0.2.1 — Sensitivity confirmed on surrogate.
LZ↑, RR↓, φ-half↓, IF-spread↑ with flux; FWHM ~ constant. Code + outputs in /outputs (v021_*). See v021_stats_summary.md for slopes and gate decisions.

# Black Box in Flux 

<<<<<<< HEAD
https://doi.org/10.5281/zenodo.17574087
=======
https://doi.org/10.5281/enodo.17574087
>>>>>>> b449014607055b72888affa357abb5b1f9d8409b

## Cite this work
If you use this repository, please cite the Zenodo record:

**Muller, N. (2025). *Black Box in Flux: v0.1.0 – First reproducible experiment*. Zenodo.**  
<<<<<<< HEAD
https://doi.org/10.5281/zenodo.17574087
=======
DOI:10.5281/zenodo.17574087
>>>>>>> b449014607055b72888affa357abb5b1f9d8409b



This repo gives you a no-lab, laptop-only pipeline to probe links between *flux* (slow parameter drift) in an open quantum system and *chaos-like* behavior in black-box output time series.



# **Black-Box Indicators of Chaos**

*A reproducible pipeline for detecting complexity transitions in driven nonlinear systems*

This repository contains a complete experimental framework for studying how **black-box time-series indicators** behave when a system is pushed out of equilibrium. The project uses the **Duffing oscillator** as a nonlinear benchmark and analyzes how complexity, recurrence, phase stability, and instantaneous frequency dynamics evolve under increasing drive γ.

The core goal is to test whether a system’s **output alone** can reveal when it crosses into a more chaotic or complexity-rich regime — an early step toward linking chaos theory with quantum-like behavior in systems where the internal state is inaccessible.

All figures, results, and analysis steps are fully reproducible.

---

## **Key Findings (Current Status)**

* Increasing drive **increases complexity** (LZ complexity ↑).
* Recurrence patterns **break down** (RR ↓).
* Phase coherence **collapses** near γ ≈ **0.24–0.27**.
* Instantaneous frequency dynamics become **more irregular** (IFSP ↑).
* A simple **piecewise linear onset detector** consistently identifies the same transition region.
* Surrogate testing (IAAFT) verifies that these signatures are **not random artifacts**.

All plots are available in `/results/`.

---

## **Repository Structure**

```
.
├── notebooks/
│   ├── black_box_in__setup.ipynb           # Environment + utilities + smoke tests
│   ├── black_box_in__through.ipynb         # First full walkthrough (early POC)
│   ├── next_experiment__duffing.ipynb      # Main experiment pipeline
│   ├── 11_batch_runs.ipynb                 # (Legacy) prototype batch runs
│   ├── 12_physical_echo.ipynb              # (Legacy) echo experiments
│
├── results/                                # Generated figures + tables
├── outputs/                                # Optional additional data artifacts
├── environment.yml                         # Conda environment for reproducibility
├── requirements.txt                        # Python package list
├── data/                                   # Raw and temporary data (if used)
├── configs/                                # Experiment config files
├── docs/                                   # Documentation (optional)
├── CITATION.cff
└── README.md (this file)
```

---

## **Notebook Overview**

### **1. `black_box_in__setup.ipynb`**

Initial setup notebook.
Includes:

* dependency checks
* base imports
* small simulation tests
* helper utilities

Run this once to confirm your environment is ready.

---

### **2. `black_box_in__through.ipynb`**

A full end-to-end example used to establish the early concept.
Covers:

* the first implementation of black-box metrics
* basic drive sweep
* initial validation of methodology

Useful for understanding the rationale behind the project.

---

### **3. `next_experiment__duffing.ipynb` (Main Pipeline)**

This is the core notebook for the current study.

It includes:

#### **Simulation**

* Duffing oscillator ODE
* Stable integration
* Drive grid definition

#### **Metrics**

Black-box indicators computed from raw time-series only:

* **Lempel–Ziv complexity (LZ)**
* **Recurrence Rate (RR)**
* **Phase Dephasing Half-Life (DEPH)**
* **Instantaneous Frequency Spread (IFSP)**
  *(LLE is temporarily disabled for stability.)*

#### **Analysis**

* Full drive sweep
* Aggregation of means and variances
* Trend visualization

#### **Onset Detection**

* Fitting a **one-breakpoint piecewise linear model**
* Identifying transition γ*
* Saving all fit figures

#### **Surrogate Testing**

* IAAFT surrogates preserving amplitude + spectrum
* Checking whether trends are due to real structure
* Boxplots comparing surrogate distributions vs. real metrics

#### **Outputs**

* All figures saved to `/results`
* CSV tables where applicable

---

## **Installing & Running**

### **1. Create the environment**

```bash
conda env create -f environment.yml
conda activate bbif
```

### **2. Launch Jupyter**

```bash
jupyter lab
```

### **3. Run the main experiment**

Open:

```
notebooks/next_experiment__duffing.ipynb
```

and run all cells.
A fresh kernel is recommended for reproducibility.

---

## **Reproducibility**

* All randomness is controlled via fixed seeds.
* The Duffing ODE is integrated with deterministic solvers.
* Surrogate generation uses fixed RNG states.
* Every plot and table is produced automatically via the notebook.

---

## **Results**

After running the main pipeline, you’ll find:

* **metrics_vs_gamma.png**
* **piecewise_*.png** (breakpoint fits)
* **surrogates_gamma_*.png**
* **breakpoints.csv** (if enabled)

in the `/results` folder.

These files summarize the current state of the research and are suitable for publication or inclusion in a manuscript.

---

## **Roadmap**

* Reinstate a stable, long-series LLE implementation
* Extend experiments to quantum-inspired stochastic models
* Integrate higher-order black-box metrics
* Explore cross-system generalization
* Prepare a 5–7 page scientific manuscript
* Publish Zenodo DOI + preprint version

---

## **Citation**

If you use this repository or the ideas behind it, please cite using the `CITATION.cff` file included here.

---

## **License**

CC-BY 4.0



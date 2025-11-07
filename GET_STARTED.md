
# Black Box in Flux — Get Started (Step‑by‑Step)

This guide assumes **no recent Python experience**. Follow it line by line.  
If something fails, copy the error and we’ll fix it.

---

## 0) What you’re going to get

- A working Python environment with the right libraries
- A notebook you can **run cell by cell** and **understand each step**
- Clean commenting so others can reproduce your work

The project lives in a folder like this:
```
bbif_starter/
├─ GET_STARTED.md
├─ COMMENTS_GUIDE.md
├─ requirements.txt
├─ README.md
├─ black_box_in_flux_setup.ipynb
└─ black_box_in_flux_walkthrough.ipynb  ← use this first
```

---

## 1) Install Python (if needed)

- Windows/macOS: Install **Miniconda** (recommended for beginners).  
  Download from the official Miniconda site and install with defaults.

- Linux: If you already have `conda`, great. Otherwise install Miniconda as above.

> Why conda? It keeps your project isolated so one project can’t break another.

---

## 2) Create your project folder

Put the `bbif_starter` folder somewhere easy (e.g., Desktop). If you don’t have it yet, download it from ChatGPT and unzip it.

---

## 3) Open a terminal

- **Windows**: Open “Anaconda Prompt” (or “Miniconda Prompt”).
- **macOS**: Open “Terminal” (Applications → Utilities).
- **Linux**: Use your usual terminal.

Use `cd` to move into your folder (replace `PATH_TO` accordingly):
```bash
cd PATH_TO/bbif_starter
```

Tip: You can drag the folder into the terminal to paste the path automatically.

---

## 4) Create and activate your environment

### Option A: Using conda (recommended)

```bash
conda create -n bbif python=3.10 -y
conda activate bbif
```

### Option B: Using venv (works too)

```bash
python -m venv .venv
# Windows:
.venv\\Scripts\\activate
# macOS/Linux:
source .venv/bin/activate
```

> If you use venv, also run:
> ```bash
> pip install --upgrade pip
> ```

---

## 5) Install the required libraries

From inside the `bbif_starter` folder:

```bash
pip install -r requirements.txt
```

If `qutip` complains:
- Try: `pip install qutip`
- If it still fails on macOS with M1/M2 chips, make sure you have Xcode Command Line Tools installed:
  ```bash
  xcode-select --install
  ```

---

## 6) Launch Jupyter and open the walkthrough notebook

```bash
python -m pip install jupyter
jupyter notebook
```
A browser tab will open. Click **`black_box_in_flux_walkthrough.ipynb`**.

If your browser doesn’t open, the terminal shows a link. Copy it into your browser.

---

## 7) Run the notebook (one cell at a time)

In the menu: **Kernel → Restart & Run All** (or run with Shift+Enter cell by cell).  
The walkthrough will:
- Verify versions
- Simulate the *black box in flux* system
- Compute metrics
- Explain what each plot means
- Save a small CSV with results

---

## 8) Change one parameter to “see it move”

In the notebook, find **`DRIFT_RATE`** and double it. Re-run the metrics cell.  
You should see changes in:
- **Permutation entropy**
- **LLE slope**
- **Echo (1 - Fidelity)**

---

## 9) Comment as you go (see `COMMENTS_GUIDE.md`)

- Add short markdown notes before each change you make
- When you run comparisons (like different DRIFT_RATE values), list what you expect to see and what you actually saw

---

## 10) Share your work

- Export the notebook as HTML: **File → Download as → HTML**  
- Zip your folder and share via Drive / Dropbox / email

That’s it! If anything breaks, copy/paste the error text and we’ll fix it.

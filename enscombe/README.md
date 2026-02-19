# Anscombe's Quartet — Data Analysis

An exploratory analysis of [Anscombe's Quartet](https://en.wikipedia.org/wiki/Anscombe%27s_quartet), a classic dataset designed to demonstrate why visualizing data is essential and why summary statistics alone can be deeply misleading.

---

## What is Anscombe's Quartet?

Anscombe's Quartet is a set of four small datasets (I, II, III, IV), each containing 11 (x, y) pairs, constructed by statistician Francis Anscombe in 1973. The four datasets are remarkable because they share nearly **identical descriptive statistics**:

| Dataset | Mean x | Std x | Mean y | Std y | Pearson r |
|---------|--------|-------|--------|-------|-----------|
| I       | 9.00   | 3.32  | 7.50   | 2.03  | 0.8164    |
| II      | 9.00   | 3.32  | 7.50   | 2.03  | 0.8162    |
| III     | 9.00   | 3.32  | 7.50   | 2.03  | 0.8163    |
| IV      | 9.00   | 3.32  | 7.50   | 2.03  | 0.8165    |

Yet when plotted, they look completely different:

- **Dataset I** — a clean linear relationship with random scatter (the only case where a linear model is appropriate)
- **Dataset II** — a smooth curved (quadratic) relationship
- **Dataset III** — a linear pattern with a single high-leverage outlier at (13, 12.74)
- **Dataset IV** — all x values are identical (x = 8) except for one point at x = 19; the regression line is entirely driven by that single outlier

The lesson: **always plot your data before drawing conclusions from statistics.**

---

## Repository Contents

| File | Description |
|------|-------------|
| `anscombe_quartet.tsv` | Source data — tab-separated, columns: `dataset`, `x`, `y` |
| `anscombe_analysis.ipynb` | Jupyter notebook with full analysis and all plots |
| `plot1_scatter.png` | 2×2 grid of raw scatter plots |
| `plot2_regression.png` | Scatter plots with fitted OLS regression lines |
| `plot3_residuals.png` | Residual plots (y − ŷ vs. fitted values) |
| `plot4_boxplots.png` | Side-by-side box plots of x and y distributions |
| `PLAN.md` | Incremental analysis plan and iteration log |

---

## Notebook Overview

The notebook `anscombe_analysis.ipynb` walks through four analyses:

### 1. Descriptive Statistics
Loads the data with `pandas` and computes mean, standard deviation, min, max, and Pearson correlation for each dataset — confirming they are statistically indistinguishable.

### 2. Plot 1 — Scatter Grid
A 2×2 grid of raw scatter plots, one per dataset. Each panel is color-coded by dataset (blue / orange / green / red) to make them easy to distinguish.

### 3. Plot 2 — Scatter + OLS Regression Lines
The same scatter plots with an OLS regression line overlaid on each panel. All four lines are virtually identical (y ≈ 3 + 0.5x), illustrating how a single numerical summary can mask very different underlying structures.

### 4. Plot 3 — Residual Plots
Residuals (y − ŷ) plotted against fitted values. Good residual plots show random scatter around zero; these panels reveal:
- Dataset I: random scatter ✓ (linear model fits)
- Dataset II: a clear curve (quadratic, not linear)
- Dataset III: one extreme residual (outlier dominates the fit)
- Dataset IV: degenerate pattern (model has almost no valid data to fit)

### 5. Plot 4 — Box Plots
Side-by-side box plots of x and y per dataset. The near-identical boxes reinforce that standard summary statistics give no hint of the structural differences visible in the scatter plots.

---

## How to Run

### Prerequisites

```bash
pip install pandas numpy matplotlib
```

### Open in VS Code

1. Open `anscombe_analysis.ipynb` in the VS Code Explorer
2. Click **Select Kernel** (top right) → choose **Python 3**
3. Click **Run All** to re-execute all cells

The notebook was pre-executed and outputs are already embedded, so you can scroll through and view all plots immediately without running anything.

---

## Key Takeaway

Summary statistics (mean, variance, correlation, regression coefficients) are necessary but not sufficient for understanding data. Anscombe's Quartet is a canonical reminder that **visualization is a non-negotiable step in any data analysis**.

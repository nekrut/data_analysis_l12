# Data Analysis Projects

A collection of data analysis and bioinformatics projects.

---

## Projects

### 1. Anscombe's Quartet Analysis (`enscombe/`)

An exploratory analysis of [Anscombe's Quartet](https://en.wikipedia.org/wiki/Anscombe%27s_quartet), a classic dataset demonstrating why visualization is essential and why summary statistics alone can be misleading. All four datasets share nearly identical descriptive statistics (mean, standard deviation, Pearson correlation) yet exhibit fundamentally different structures when plotted.

**Contents:**
- Jupyter notebook with full analysis (`anscombe_analysis.ipynb`)
- Source data in TSV format (`anscombe_quartet.tsv`)
- Generated plots: scatter grids, OLS regression lines, residual plots, and box plots

**Key takeaway:** Always visualize your data before drawing conclusions from summary statistics.

### 2. CDKN2A/ARF Literature Search (`literature search/`)

A curated literature search on the CDKN2A and ARF genes covering publications from 2021 to 2025. Sources include PubMed and Europe PMC.

**Contents:**
- Annotated results with paper titles, links, descriptions, and DOIs (`RESULTS.md`)
- Search plan and methodology (`PLAN.md`)

---

## Requirements

- Python 3
- pandas, numpy, matplotlib (for the Anscombe notebook)

```bash
pip install pandas numpy matplotlib
```

---

## Usage

Open any `.ipynb` file in VS Code or Jupyter and select a Python 3 kernel to run the analyses. Notebook outputs are pre-rendered so results can be viewed without re-execution.

# An analysis of Anscombe data

## Goal

Analyze data set and visualize it, and see what we want to do next with it. 

## Implementation

- Need to analyze data in Anscombe_Quartet.tsc. 
- First, look at the data and generate descriptive statistics. 
- Second, create a Jupyter Light notebook in which you will generate plots. 
- Propose the types of plots that you would like to generate. 
- Save this proposal to the end of this file and let me look at it. 
- I will need to approve this plan and tell you to go ahead before we actually do anything. Please append the plan to the end of this file.

---

## Descriptive Statistics

All four datasets have nearly **identical** summary statistics — this is the central insight of Anscombe's Quartet.

| Dataset | Mean x | Std x | Mean y | Std y | Pearson r |
|---------|--------|-------|--------|-------|-----------|
| I       | 9.00   | 3.32  | 7.50   | 2.03  | 0.8164    |
| II      | 9.00   | 3.32  | 7.50   | 2.03  | 0.8162    |
| III     | 9.00   | 3.32  | 7.50   | 2.03  | 0.8163    |
| IV      | 9.00   | 3.32  | 7.50   | 2.03  | 0.8165    |

---

## Proposed Plots

### Plot 1 — 2×2 Scatter Plot Grid (the classic Anscombe visualization)
One scatter plot per dataset arranged in a 2×2 grid. Each panel shows the raw (x, y) points.
**Why:** Immediately reveals how different the four datasets are despite identical statistics.
- Dataset I: clean linear scatter
- Dataset II: curved (quadratic) relationship
- Dataset III: linear with one high-leverage outlier at (13, 12.74)
- Dataset IV: all x values clustered at 8 with one outlier at x=19

### Plot 2 — Scatter Plots with Fitted Regression Lines
Same 2×2 grid, but each panel overlays the OLS regression line (y ≈ 3 + 0.5x, identical for all four).
**Why:** Highlights that the same regression line fits all four datasets, yet is appropriate only for Dataset I.

### Plot 3 — Residual Plots
Four panels showing residuals (y − ŷ) vs. fitted values for each dataset.
**Why:** Residual patterns expose model misfit — Dataset II shows a clear curve, Dataset III shows a single large residual, Dataset IV shows a degenerate pattern.

### Plot 4 — Side-by-Side Box Plots
Two sets of box plots: one for x values and one for y values, grouped by dataset.
**Why:** Reinforces that the marginal distributions are nearly identical, setting up the contrast with the scatter plots.

## Iteration 1

- Go ahead and execute your plan. 
- Save it all in a Jupyter Notebook that I can start in this VS Code instance. 
- Explain to me how to start a Jupyter Notebook so I can validate your results. 

## Iteration 2

- Make it colorful so the four panels have different colors. 

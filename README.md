# COVID-19 Romania Research

A self-supervised neural-analytic method to assess the evolution of COVID-19 in Romania.

**Published on arXiv:** [2006.12926](https://arxiv.org/abs/2006.12926)

## Overview

This repository contains research materials for analyzing the COVID-19 pandemic progression in Romania using neural-analytic methods. The work includes LaTeX source code for the paper, figures, and simulation results.

## Contents

- `main.tex` - Main LaTeX paper source
- `main.bib` - Bibliography file
- `neurips_2019.sty` - LaTeX style file
- `figs/` - Generated figures and plots
  - `30-04-2020/` - Early analysis figures
  - `best_fit/` - Best-fit model results
  - `comparison/` - Comparative analysis plots
  - `moderate/` - Moderate scenario projections
- `results/` - Numerical simulation results

## Building

To compile the LaTeX paper:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

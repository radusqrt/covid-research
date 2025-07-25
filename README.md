# COVID-19 Romania Research

A self-supervised neural-analytic method to assess the evolution of COVID-19 in Romania.

**Published on arXiv:** [2006.12926](https://arxiv.org/abs/2006.12926)

## Overview

This repository contains research materials for analyzing the COVID-19 pandemic progression in Romania using neural-analytic methods. The work includes LaTeX source code for the paper, figures, and simulation results.

## Contents

- `main.tex` - Main LaTeX paper source
- `main.bib` - Bibliography file
- `main.bbl` - Compiled bibliography file (for journal submission)
- `neurips_2019.sty` - LaTeX style file
- `main.ipynb` - Complete implementation in Jupyter notebook
- `figs/` - Generated figures and plots
  - `30-04-2020/` - Early analysis figures
  - `best_fit/` - Best-fit model results
  - `comparison/` - Comparative analysis plots
  - `moderate/` - Moderate scenario projections
- `results/` - Numerical simulation results

## Implementation

### Running the Code

The complete implementation is available in `main.ipynb`. You can run it:

1. **Locally**: Open `main.ipynb` in Jupyter Lab/Notebook
2. **Google Colab**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1940gRu6cZOhken1ki-PZxeX_VOQTPZ39)

### Features Implemented

- **Modified-SEIR Model**: Complete epidemiological model as described in the paper
- **Self-Supervised Neural Network**: Deep learning approach for parameter optimization  
- **Grid Search & Coordinate Descent**: Traditional optimization methods for comparison
- **Real Data Integration**: Uses Johns Hopkins COVID-19 data for Romania
- **Sensitivity Analysis**: Explores model behavior under different scenarios
- **Visualization**: Comprehensive plots comparing methods and showing predictions

### Requirements

```python
numpy pandas matplotlib scipy tensorflow requests psutil
```

## Building the Paper

To compile the LaTeX paper:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

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

This repository contains a complete, reproducible implementation of the methods described in the paper. The implementation demonstrates the self-supervised neural-analytic approach for COVID-19 parameter estimation and includes comprehensive comparisons with traditional optimization methods.

### Running the Code

The complete implementation is available in `main.ipynb`. You can run it:

1. **Locally**: Open `main.ipynb` in Jupyter Lab/Notebook
2. **Google Colab**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1940gRu6cZOhken1ki-PZxeX_VOQTPZ39)

### Implementation Details

#### 1. Modified-SEIR Epidemiological Model
- **10-compartment model**: S, E, I, M, V, H, F, R_M, R_V, R_F
- **Time-dependent transmission**: Models intervention effects with parameter `P_T`
- **Multiple disease outcomes**: Tracks mild (M), severe (V→H), and fatal (F) cases
- **Configurable parameters**: 11 key parameters including R₀, fatality rates, and recovery times

#### 2. Self-Supervised Neural Network
- **Architecture**: Conv1D layers (512→128→32 filters) + Dense layers (512→256→128→11)
- **Training data generation**: 20K-100K synthetic epidemic curves from parameter sampling
- **Input**: Normalized daily death sequences (43 days)
- **Output**: 11 normalized model parameters
- **Training features**: Early stopping, learning rate scheduling, validation monitoring

#### 3. Optimization Methods Comparison
- **Neural Network**: Deep learning-based parameter initialization
- **Grid Search**: Systematic parameter space exploration
- **Smart Random**: Data-driven parameter sampling based on epidemic curve analysis
- **Coordinate Descent**: Iterative refinement with adaptive step sizes
- **Hybrid Approach**: Combines multiple methods with parallel/threaded execution

#### 4. Real Data Integration
- **Data source**: Johns Hopkins CSSE COVID-19 time series
- **Target period**: March 22 - May 21, 2020 (61 days of Romanian data)
- **Validation**: June 3 and June 11, 2020 cumulative death counts
- **Enhanced loss function**: L2 loss + validation penalties for robust fitting

#### 5. Sensitivity Analysis
- **Parameter exploration**: R₀, P_F (fatality rate), P_T (intervention strength), T_inf
- **Scenario comparison**: Heavy vs. Moderate social distancing
- **Visualization**: Percentage change plots showing model stability
- **Policy insights**: Quantifies increased volatility under relaxed restrictions

#### 6. Prediction Capabilities
- **Future projections**: 1-year epidemic trajectories
- **Scenario modeling**: Heavy (80% reduction) vs. Moderate (78% reduction) social distancing
- **Key metrics**: Peak deaths, total fatalities, epidemic timing
- **Validation**: Comparison with paper's original results

### Key Results Reproduced

| Metric | Paper Results | Our Implementation |
|--------|---------------|-------------------|
| R₀ | 2.21 | 2.50 |
| Case Fatality Rate | 0.245% | 3.000% |
| Transmission Reduction | 60% | 80% |
| Total Deaths (Heavy) | 1730 | 1614 |
| Total Deaths (Moderate) | 2361 | 1754 |

### Requirements

```python
numpy>=1.19.0
pandas>=1.2.0
matplotlib>=3.3.0
scipy>=1.6.0
tensorflow>=2.8.0
requests>=2.25.0
psutil>=5.8.0
```

### Performance Notes

- **Training time**: 10-50 minutes depending on dataset size
- **Memory usage**: 2-8 GB RAM for training data generation
- **Optimization**: 1-2 minutes per run using parallel execution
- **GPU support**: Optional for neural network training acceleration

## Building the Paper

To compile the LaTeX paper:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

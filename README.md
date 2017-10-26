# Density Ranking 
Analyzing data using density ranking.

- Paper reference: Chen, Yen-Chi, and Adrian Dobra. "Measuring Human Activity Spaces With Density Ranking Based on GPS Data." arXiv preprint [arXiv:1708.05017](https://arxiv.org/abs/1708.05017) (2017).
- Maintianer: yenchic@uw.edu
- `DR.R`: the main script for running the program.
- `DR_demo.R`: an example for applying `DR` method to a dataset.



## DR.R
Here is a description for the main functions.

### fms
`DR = function(data, h, kernel="Gaussian", xlim=NULL, ylim=NULL, CL_lev = NULL, n_res=201, n_tg=100, ...)`
- Density ranking analysis for 2D dataset (GPS).  
- Inputs:
  - data: Input 2D data matrix.
  - h: Smoothing parameter.
  - kernel: kernel function, choosing from "Gaussian", "uniform", and "quartic". Default is Gaussian kernel. 
  - xlim: The range of first variable. 
  - ylim: The range of second variable. 
  - CL_lev: The levels for contours lines. If not specify, it will automatically choose 0.05, 0.10, ..., 0.95 as the levels.
  - n_res: The resolution of grids. 201 means a $201\times201$ matrix over the range of `xlim` and `ylim`.
  - n_tg: The levels for evaluating the mass-volume curve and Betti number curve.
- Outputs:
  - The density ranking analysis result; a list consisting of
    - label: The cluster labels for query points.
    - modes: The local modes corresponding to each label.

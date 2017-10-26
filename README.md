# Density Ranking 
Analyzing data using density ranking.

- Paper reference: 
  - Chen, Yen-Chi, and Adrian Dobra. "Measuring Human Activity Spaces With Density Ranking Based on GPS Data." arXiv preprint [arXiv:1708.05017](https://arxiv.org/abs/1708.05017) (2017).
  - Chen, Yen-Chi. "Generalized Cluster Trees and Singular Measures." arXiv preprint [arXiv:1611.02762](https://arxiv.org/abs/1611.02762) (2016).
- Maintianer: yenchic@uw.edu
- `DR.R`: the main script for running the program.
- `DR_demo.R`: an example for applying `DR` method to a dataset.

To try this script, please execute the programs in `DR_demo.R`. 
Note that you need to download the dataset from https://archive.ics.uci.edu/ml/datasets/GPS+Trajectories before implementing `DR_demo.R`.  


## DR.R
Here is a description for the main function.

### DR
`DR = function(data, h, kernel="Gaussian", xlim=NULL, ylim=NULL, CL_lev = NULL, n_res=201, n_tg=100, ...)`
- Density ranking analysis for 2D datasets (GPS).  
- Inputs:
  - `data`: Input 2D data matrix.
  - `h`: Smoothing parameter.
  - `kernel`: kernel function, choosing from "Gaussian", "uniform", and "quartic". Default is Gaussian kernel. 
  - `xlim`: The range of first variable. 
  - `ylim`: The range of second variable. 
  - `CL_lev`: The levels for contours lines. If not specify, it will automatically choose 0.05, 0.10, ..., 0.95 as the levels.
  - `n_res`: The resolution of grids. 201 means a $201\times201$ matrix over the range of `xlim` and `ylim`.
  - `n_tg`: The levels for evaluating the mass-volume curve, Betti number, and persistence curves.
- Outputs:
  - The density ranking analysis result; a list consisting of
    - `h`: The smoothing bandwidth. 
    - `x_grid`: The grid point for the first variable.
    - `y_grid`: The grid point for the second variable.
    - `gr_alpha`: The density ranking value at each grid point.
    - `data_alpha`: The density ranking value at each data point.
    - `CL_lev`: The contour levels. 
    - `CL`: A list of contour lines corresponding to `CL_lev`.
    - `persistent`: The persistent diagram of density ranking.
    - `clevel`: The levels where the mass-volume, Betti number, and persistence curves are evaluated.
    - `Mcurve`: The value of the mass-volume curve evaluated at `clevel`.
    - `Bcurve`: The value of the Betti number curve evaluated at `clevel`.
    - `Pcurve`: The value of the persistence curve evaluated at `clevel`.
    
    

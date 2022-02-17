# TrOOP
Trajectory-based Optimization for Oblique Projections of dynamical systems

We provide a Jupyter notebook producing the results for the nonlinear system with an important low-energy feature presented in our paper:

S. E. Otto and C. W. Rowley, "Optimizing Oblique Projections for Nonlinear Systems Using Trajectories", 2022, SISC (under review), arXiv 2106.01211

In particular, we implement our prposed method TrOOP along with Petrov-Galerkin reduced-order models with subspaces determined by Proper Orthogonal Decomposition (POD), linear balanced truncation, quadratic-bilinear balanced truncation, and the quadratic bilinear iterative rational Krylov algorithm. 

Our implementation of each method is general enough to allow the user to try them on any quadratic-bilinear system. This may be done by changing the tensors A_FOM, B_FOM, C_FOM, H_FOM, and N_FOM which define the full-order model. 

Our implementation of the geometric conjugate gradient algorithm (Algorithm 4.2 in our paper) is completely general and can be used for any nonlinear system. Our implementation of the objective and its gradient following Algorithm 4.1 in our paper is general too. However, the user will need to re-define ROM, ROM_obs, d_ROM_adj, and d_ROM_obs_adj within the functions objective and objective_grad. For very high-dimensional systems such as the jet flow discussed in our paper, speciallized solvers are used. One must interface with the specialized solver to construct ROM, ROM_obs, d_ROM_adj, and d_ROM_obs_adj.

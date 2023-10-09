# rBGR
rBGR is an R package that implements a flexible Bayesian model to construct heterogeneous graphs under non-normal continuous data. For more details, please see Yao et al. (2023+)  Robust Bayesian Graphical Regression Models for Assessing Tumor Heterogeneity in Proteomic Networks.

# Manual
## Main MCMC Function
In this software, we offer the necessary R codes to demonstrate how our model constructs heterogeneous graphs under non-normal data with an example used in the paper of Yao et al. (2023+). We wrap up the whole model as an MCMC function of `rBGR_mcmc_Int()`. Specifically, given the example proteomic data $Y$ and the immune component abundance $X$, we regress one variable $Y_j$ on the rest of variables $Y_{-j}$ given the covariates $X$. The MCMC function `rBGR_mcmc_Int()` takes the target variable $Y_j$ by the argument `Y` and the rest of variables $Y_{-j}$ by the argument `X` with the covariates $X$ by the argument `U`. The function `rBGR_mcmc_Int()` also allows additional options to control the model, such as `N` for the number of iterations, `burnin` for the number of iterations to be discarded, and `seed_` for the initial seeds. 

## Summarizing Posterior Samples
rBGR offers two levels of graph: population and individual level. Two different R codes generate each of them. 

### Population graph
Once we obtain all posterior samples, we run the `pstSmpExt_hotCold_intSS_pop.R` to extract the population-level information and visualize the results through the `Res_hotCold_intSS_popLevel.R` 

### Individual graph
For the individual-level graphs, rBGR requires the user to extract the population information as the input. We can run `pstSmpExt_hotCold_intSS_noZ_ind.R` to obtain the information for different individuals and run `Res_hotCold_intSS_indQuantile.R` to visualize the graphs for different individuals. Currently, we use the 5, 25, 50, 75, and 95-th percentiles of the covariates from $X$ as the five different individuals and generate graphs as shown in the paper.

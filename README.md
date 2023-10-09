# rBGR
rBGR is an R package that implements a flexible Bayesian model to construct heterogeneous graphs under non-normal continuous data. For more details, please see Yao et al. (2023+)  Robust Bayesian Graphical Regression Models for Assessing Tumor Heterogeneity in Proteomic Networks.

# Manual
In this software, we offer the necessary R codes to demonstrate how our model constructs heterogeneous graphs under non-normal data with an example used in the paper of Yao et al. (2023+). We wrap up the whole model as an MCMC function of rBGR_mcmc_Int(). Specifically, given the example proteomic data Y and the immune component abundance X, we regress one variable Y_i on the rest of variables Y_{-i} given the covariates X. In the MCMC function, the variable Y with the rest nodes as the input argument X

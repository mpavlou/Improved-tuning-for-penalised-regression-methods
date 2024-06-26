# Modified tuning for penalised regression methods

This work relates to the article 

#### "Penalised regression methods with modified cross-validation and bootstrap tuning produce better prediction models" 

published in the Biometerical Journal: https://doi.org/10.1002/bimj.202300245

## Summary

Risk prediction models fitted using maximum likelihood estimation (MLE) are often overfitted resulting in predictions that are too extreme and a calibration slope (CS) less than 1. 

Penalised methods, such as Ridge and Lasso, have been suggested as a solution to this problem as they tend to shrink regression coefficients towards zero resulting in predictions closer to the average. 

The amount of shrinkage is regulated by a tuning parameter, λ, commonly selected via cross-validation (‘standard tuning’). Though penalised methods have been found to improve calibration on average, they often over-shrink and exhibit large variability in the selected λ and hence the CS. This is a problem particularly for small sample sizes but also when using sample sizes recommended to control overfitting.  

In this work we show that these problems are partly due to selecting λ using cross-validation with ‘training’ datasets of reduced size compared to the original development sample, resulting in an over-estimation of λ and hence, excessive shrinkage. 

We propose a modified cross-validation tuning method (‘modified tuning’) which estimates λ from a pseudo-development dataset obtained via bootstrapping from the original dataset, albeit of larger size, such that the resulting cross-validation training datasets are of the same size as the original dataset. Modified tuning can be easily implemented in standard software and is closely related to bootstrap selection of the tuning parameter (‘bootstrap tuning’). 

The figure below shows that the tuning parameter tends to be higher when the number of cross-validation folds is smaller, which agrees with the intuition above. Modified cross-validation tuning and bootstap tuning perform very similarly

![figure_1](https://github.com/mpavlou/Improved-tuning-for-penalised-regression-methods/assets/78787823/e39b6761-1645-4739-b1e5-3d3bd80b560e)

Our evaluations with simulated data (and real data) show that tuning with modified cross-validation results in clear improvement in terms of calibration (Calibration slope closer to 1 and reduced variability) as shown in the Figure below, compared to the standard tuning method. 

![figure_2_online](https://github.com/mpavlou/Improved-tuning-for-penalised-regression-methods/assets/78787823/bb5d7f64-6367-4bb1-9a0e-533d9e554d0a)



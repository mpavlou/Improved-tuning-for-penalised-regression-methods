# Modified tuning for penalised regression methods

This work relates to the article 

"Penalised regression methods with modified cross-validation and bootstrap tuning produce better prediction models" 

## Summary

Risk prediction models fitted using maximum likelihood estimation (MLE) are often overfitted resulting in predictions that are too extreme and a calibration slope (CS) less than 1. 

Penalised methods, such as Ridge and Lasso, have been suggested as a solution to this problem as they tend to shrink regression coefficients towards zero resulting in predictions closer to the average. 

The amount of shrinkage is regulated by a tuning parameter, λ, commonly selected via cross-validation (‘standard tuning’). Though penalised methods have been found to improve calibration on average, they often over-shrink and exhibit large variability in the selected λ and hence the CS. This is a problem particularly for small sample sizes but also when using sample sizes recommended to control overfitting.  

These problems are partly due to selecting λ using cross-validation with ‘training’ datasets of reduced size compared to the original development sample, resulting in an over-estimation of λ and hence, excessive shrinkage. 

We propose a modified cross-validation tuning method (‘modified tuning’) which estimates λ from a pseudo-development dataset obtained via bootstrapping from the original dataset, albeit of larger size, such that the resulting cross-validation training datasets are of the same size as the original dataset. Modified tuning can be easily implemented in standard software and is closely related to bootstrap selection of the tuning parameter (‘bootstrap tuning’). 

Our evaluations with real and simulated data show that that modified and bootstrap tuning for Ridge and Lasso can substantially improve the selection of λ (see, for example, Figure 1), resulting in improved CS compared to the standard tuning method (see, for example, Figure 2). They also improve predictions compared to MLE. 

# data standardization in regression task

## Reason

Because every feature has the dimension. the different dimension will cause huge difference in coefficient.

## When

### clustering

standardization is very important because clustering algorithm rely on the definition of intro-distance and inter-distance 

### PCA

very important. PCA give more weight to those variable with higher variance.

### KNN

very important. the reason is the same as clustering.

### SVM

very important. SVM is also relative with distance computing.

### LASSO Ridge

very important. Regularization will put penalty on coefficient. 



## When not

- linear regression

- logisitic

- decision tree

- boosting, stacking and bagging, ensemble learning

  

  
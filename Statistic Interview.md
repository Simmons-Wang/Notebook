# Statistic Interview

## Central Limit Theorem

- When we want to get the average value from whole population but we cannot obtain data from everyone, we can sample some points. 
- CLT means when we sample from a population using a sufficiently large sample, the mean of the samples will be normally distributed, the mean tending to the mean of the population and the variance tending to the  variance equal to the variance of the population divided by the size of sampling.
- That will be true, regardless of the distribution of the original population.



## Data sampling

- select, manipulate and analyze a representative subset of data points to identify patterns and trends in the larger data set being examined. 
- it enable us to work will a smaller, manageable amount of data about a population to build models more quickly, which still producing accurate findings.
- probability sampling: 
  - simple random: randomly select subjects from the whole population
  - stratified sampling: we firstly create several subgroup based on a common factor, randomly collected from each subgroup.
  - cluster sample. We divided the whole dataset into several cluster, then random choose several clusters. (we will study whole clusters).
  - muti-staged sampling 
  - systematic sampling. we set an interval at which to extract data- from the larger population.
- non-probability. 
  - convenience sampling
  - consecutive sampling

## type I and type II error

|                | no reject | reject  |
| -------------- | --------- | ------- |
| $H_0$ is true  |           | I error |
| $H_0$ is false | II error  |         |



## linear regression

- we assume the relationship between the  independent variables and the dependent variables is linear.
- P-value is the minimum significance level at which the coefficient is relevant. the lower, the more important is the variable in the prediction.
- The coefficient value means how much the mean of the dependent variable changes given a  one-unit shift in the independent variable while holding all the other variables in the model constant. it allow us to assess the effect of each variable in isolation from others.
- $R^2$ is a statistic measure that represent the proportion of the variance for a dependent variable that is explained by  independent variables.

## assumptions for linear regression

- linear relationship
- residuals of the data are normally distributed and independent from each other.
- minimal multicollinearity.
- homoscedasticity,  the residual is non-relevant with the predictor variables.

## statistical interaction

the effect of one independent variable may depend on the level of the other independent variable.



## selection bias



## variance and bias decomposition

**the expected prediction** is $\hat f (x) = E_D[f(x;D)] =E_D([y_d|x;D])$

which means the expected result of the model on test data using different train data,

$f(x;D)$ means the predicted result of test data based on train data D.

$y_d$ means the real tag in the test data.

y means the real tag in the real world.

![image-20220622161923693](https://cdn.jsdelivr.net/gh/Simmons-Wang/IMG/C:%5CUsers%5CKing%5CPictures%5Cnotebookimgimage-20220622161923693.png)

**variance**

means the volatility of  predicted result of test data based on different train data D.

**bias**

means the difference between of expected result of model and real tag of the test data.

**noise**

can be considered as the wrong manual mark



more flexible (with more degree of freedom) model will generate more variance and less bias (such as Polynomial), while less flexible model such  as Unary Linear will generate more bias but less variance.



## degree of freedom 

- degree of freedom usually represent the number of factors which play controlling role in a model system
- In statistic,  DF means the size of data to compute one statistic variable.
- In ML, DF means the number of the model parameter.

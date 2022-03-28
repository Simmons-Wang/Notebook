# Loss Function

Loss function is to evaluate the difference between predictor value and real target value.

Mainly, there are two types. Empirical Risk Loss function and Structural Risk loss function.

- Empirical Risk, measure how fit the predictor value and real target value are.
- Structural Risk,  measure some properties of the algorithm. For example, Structural Risk loss function may be equal to Empirical Risk Loss function plus regularization.

$$
J(w) = \sum_iL(m_i(w))+\lambda R(w)
$$

$$
y \in \{-1, 1\}
$$

$$
m_i = y^if_w(x^i)
$$

- L(x) must be decreasing function

## 0-1 zero-one loss

$$
L(Y, f(X)) = 
\begin{cases}
1, & Y \neq f(X) \\
0  & Y =f(X) \\
\end{cases}
$$

$$
L(m) = {1 \over 2}(1-sign(m))
$$



- directly determine the correct number, but it is non-convex.

In Perceptron,  it is such that:
$$
L(Y, f(X)) = 
\begin{cases}
1, & |Y - f(X)| \geq T \\
0  & |Y - f(X)| < T \\
\end{cases}
$$

## absolute loss function

$$
L(Y, f(X)) = |Y - f(X)|
$$

## square loss function

$$
L(Y, f(X)) = \sum_N(Y - f(X))^2
$$

- MSE(mean squared error) and $R^2$ are widely used in regression.
- MSPE(mean squared prediction error) share the same format with MSE. but MSPE is for predictor, MSE is for estimator. 



## Logarithmic Loss Function

$$
L(m) = log(1+exp(-m))
$$

$$
L(Y, P(Y|X)) = -logP(Y|X) = -log \prod_i^n P(y_i | x_i)=- \sum_i^n log P(y_i | x_i) \\
logP(y_i | x_i) = log\prod_j^m p_{ij}^{y_{ij}} = \sum_{j=1}^m y_{ij}log(p_{ij})
$$

- the output of the model is the predicted probability of  class $y_i$, P(Y|X) is a vector.
- $y_{ij}$ is bool value(1 or 0). if $y_i$ is equal to class j, $y_{ij}$= 1
- the second equation is just the expansion, it make us do not need to discuss the format of $p_{ij}$, the prob of $x_i$ belonging to class j。
- applied in logistic regression
- low Robustness, more sensitive to noise compared with hinge loss

## exponential loss

$$
L(Y|f(X)) = exp[-yf(x)]
$$

![指数损失函数](https://cdn.jsdelivr.net/gh/Simmons-Wang/IMG/C:%5CUsers%5CKing%5CPictures%5Cnotebookimgexponentialloss.png)

- It is an approximation of 0\1
- y is 1 or -1
- when $m = yf(x) >0$, denote that direction is predicted correctly. the loss penalty is small. Otherwise, loss is very large.
- sensitive to noise and outlier
- used in adaboost
- (2) is the loss function of logistic algorithm, sharing the same format with log loss.

## Hinge loss function

$$
L(y, f(x)) = max(0, 1-yf(x))
$$

- y is 1 or -1, $|f(x)| < 1$
- if correct, loss will be less than 1 or 0, or the loss will be 1-yf(x). 
- used in SVM
- $|f(x)| > 1$ is not recommended. when it is correct, loss is zero, there is no reward.
- high robustness, not sensitive to noise and outlier

### equivalent of hinge and SVM loss

the optimization target is:
$$
min_w[\sum_{i=1}^{n}max(0, 1-f_w(x^{i}))y^{i} + {1 \over 2}||w||^2]
$$
 we make the following inequity holds:
$$
max(0, 1-f_w(x^{i}))y^{i} = min_{\xi} \xi
$$


## perceptron loss

$$
L(y, f(x)) = max(0, -yf(x))
$$

- only record the loss of wrong point.

### loss function in perceptron algorithm

$$
min(- \sum_{i=1}^ny^i(w^Tx^i+b))
$$

the optimization target:
$$
min(\sum_{i=1}^nmax(0, -f_w(x^i)y^i))
$$
for wrong point:
$$
max(0, -f_w(x^i)y^i)  = -f_w(x^i)y^i
$$

- poor generalization not good

![img](https://cdn.jsdelivr.net/gh/Simmons-Wang/IMG/C:%5CUsers%5CKing%5CPictures%5Cnotebookimge9ef60e8f6aa41ed1c89e34ff4d8d7d2.png)


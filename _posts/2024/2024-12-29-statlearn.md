---
layout: post
math: true
title: The classical setting of statistical learning
---

To be honest. Writing this is like just summarize the topic in a fancy way. Not so much I hope it is.

The **general setting** of the learning problem can be defined as follows. Let the probability measure $F(z)$ be defined on space $Z$. Consider the set of functions $Q(z,\alpha),\alpha\in\Lambda$. The goal is to minimize the risk functional 

$$R(\alpha)=\int Q(z,\alpha) \, dF(z), \quad \alpha\in \Lambda$$

where the probability measure $F(z)$ is unknown, but an i.i.d. sample 

$$z_{1},\dots,z_{\ell}$$
is given. 
The learning problem considered above are particular cases of this general problem of *minimizing the risk functional* on the basis of empirical data, where $z$ describe a pair $(x,y)$ and $Q(z,\alpha)$ is the specific loss function. To apply them to specific problems, one has to substitute the corresponding loss functions in the formulas obtained. 
## Empirical risk minimization (ERM)
In order to **minimize** the risk functional with an unknown distribution function $F(z)$, the following inductive principle can be applied: 
1. The risk functional $R(\alpha)$ is replaced by the so-called *empirical risk functional*: 

$$R_{emp}(\alpha)=\frac{1}{\ell}\sum^{\ell}_{i=1}Q(z_{i},\alpha)$$
constructed on the basis of the training set. 
1. One approximates the function $Q(z,\alpha_{0})$ that minimizes risk by the function $Q(z,\alpha_{\ell})$ minimizing the empirical risk. 
This principle is often cited (or called) as the **empirical risk minimization** inductive principle, or ERM principle. 

We say that an **inductive principle** defines a **learning process** if for any given set of observations, the learning machine chooses the approximation using this inductive principle. In learning theory, the ERM principle plays a crucial role, as for nearly every single modelling system relies on the act of ERM principle at play, usually in the form of reducing the mean empirical risk to the true risk. 

The ERM principle, noted also, is quite general. The classical methods for the solution of a specific learning problem, such as the least-square method in the problem of regression estimation or the maximum likelihood (ML) method. 

The formulation of the learning problem, is indeed rather broad, but the main one as far as the classical theory is considered, should be of pattern recognition, regression estimation, and density estimation. 
___
## I. Pattern Recognition
Let the supervisor's output $y$ take only two values $y=\{0,1\}$, and $f(x,\alpha),\alpha\in\Lambda$ be a set of indicator functions (functions which take only two values: zero and one). Consider the discrete loss function: 

$$L(y, f(x,\alpha)) = \begin{cases}
0 & \text{if } y = f(x,\alpha) \\
1 & \text{if } y \neq f(x,\alpha)
\end{cases}$$

For this loss function, the functional $$R(\alpha)=\int L[y,f(x,\alpha)] \, dF(x,y) $$
determines the probability of different answers given by the supervisor and by the indicator function $f(x,\alpha)$. We call the case of different answers a *classification error*. 
## II. Regression Estimation
Let the supervisor's answer $y$ be a real value, and let $f(x,\alpha),\alpha\in \Lambda$ be a set of real functions that contains the *regression function*

$$f(x,\alpha_{0}) = \int y \, dF(y\mid x) $$

It is known that the regression function is the one that minimizes the functional with the following loss function:

$$L[y,f(x,\alpha)]=(y-f(x,\alpha))^{2}$$

Thus the problem of regression estimation is the problem of minimizing the risk functional with the loss function in the situation where the probability measure $F(x,y)$ is unknown but the data are given. 
## III. Density Estimation
Consider the problem of density estimation from the set of densities $p(x,\alpha),\alpha\in \Lambda$, we consider the following loss-function: $$L(p(x,\alpha))= -\log{(p(x,\alpha))}$$
It is known that the desired density minimizes the risk functional with the loss function. Thus, again, to estimate the density from the data, one has to minimize the risk functional under the condition where the corresponding probability measure $P(x)$ is unknown but i.i.d. data $x_{1},\dots,x_{n}$ are given. 

## Reference
The Nature of Statistical Learning, V. Nauvomich Vapnik. Springer-Verlag New York Inc (second edition, 1995-2000).
[ECE 543: Statistical Learning Theory](https://maxim.ece.illinois.edu/teaching/SLT/SLT.pdf) - Bruce Hajek and Maxim Raginsky (University of Illinois at Urbana-Champaign). 
# Prequisites

# References
Pattern Recognition and Machine Learning

# Basics

We want to minimize the error function $E$.  Typically $E$ is
$$E = \frac{1}{2} \sum_{n} \{y(x_n, w) - t_n\}^2$$
 We may also want to penalize overfitting by modifying the error function
 
$$\tilde{E} = \frac{1}{2} \sum_{n} \{y(x_n, w) - t_n\}^2  + \frac{\lambda}{2} \lVert w\rVert^2 $$
# Probability
$$p(X) = \sum_Y{p(X,Y)}$$
$$p(Y|X) = \frac{p(X,Y)}{p(X)}$$
$$p(x \in (a,b)) = \int_a^b p(x)dx $$
Due to the Jacobian factor, the probability transforms like:
$$p_y(y) = p_x(x) \left| {\frac{dx}{dy}} \right| $$
The average value of $f(x)$ is the expectation value:
$$\mathbb{E}[f] = \sum_x p(x)f(x)$$
For descrete value the expectation can be approximated:
$$\mathbb{E}[f] \approx \frac{1}{N} \sum_n f(x_n)$$
The variance is:
$$var[f] = \mathbb{E}[(f(x) - \mathbb{E}[f(x)])^2]$$

Variance denotes the variability in the values of x.  We can use covariant to determine the extent to which x and y vary together:
$$cov[x,y] = \mathbb{E}_{x,y}[x,y] - \mathbb{E}[x]\mathbb{E}[y]$$
The likelihood of the data given the weights is:
$$p(\mathcal{D}|w)$$
The Gaussian is:
$$\mathcal{N}(x|u,\sigma^2) = \frac{1}{(2\pi\sigma^2)^\frac{1}{2}} e^{-\frac{1}{2\sigma^2}(x-\mu)^2}$$
where $\mu$ is the mean and $\sigma^2$ is the variance.

The multidimensional Gaussian is:
$$
\mathcal{N}(\textbf{x}|\boldsymbol{\mu},\boldsymbol{\Sigma}) =
\frac{1}{(2\pi)^\frac{D}{2}} 
\frac{1}{|\boldsymbol{\Sigma|}^\frac{1}{2}}
e^{-\frac{1}{2} (\textbf{x} - \boldsymbol{\mu})^T }
\boldsymbol{\Sigma}^{-1}(\textbf{x} - \boldsymbol{\mu})
$$
$$$$
for some D-dimension vector $\textbf{x}$ where:
* the D-dimension vector $\boldsymbol{\mu}$ is the mean 
* the  D $\times$ D matrix $\boldsymbol{\Sigma}$ is the covariance
* $|\boldsymbol{\Sigma}|$ is the determinant of $\boldsymbol{\Sigma}$

TODO(maximum likelihood)

The maximum likelihood of $\boldsymbol{\mu}$  is the maximum value of $\mathcal{N}$ which is also the maximum value of $log(\mathcal{N})$.  Which gives
$$\mu_{ML} = \frac{1}{2} \sum x_n$$
and 

$$\sigma^2_{ML} = \frac{1}{N} \sum (x_n - \mu_{ML}))^2$$
The expected values are
$$\mathbb{E}[\mu_{ML}] = \mu$$
$$\mathbb{E}[\sigma^2_{ML}] = (\frac{N-1}{N})\sigma^2$$
Therefore if we have the $\sigma^2_{ML}$ of the sample then we can estaimate the varaince of the population as 
$$\tilde{\sigma^2} = (\frac{N}{N-1})\sigma^2_{ML}$$

For our data, we are typically given the training set $\vec{x}$ and the corresponding observations $\vec{t}$.

# Model Selection
Performance on training data is not always a good indication (due to overfitting).  Typically uou want to have a validation set to choose the best predictive performance.  And a test set can be used to confim the data model after validation.

# Decision Theory
We can change the loss function to penalize more serious losses (e.g. worse to not investigate cancer tissue then it is to investigate non-cancerous tissue.)

It's also good to take a Bayesian approach when deciding if the value is correct (e.g. much more likely that we someone incorrectly tests positive for a rare disease).

# Information Theory
Entropy is a measure of the amount of information needed to be sent in a process: 
$$H[x] = -\sum_x p(x) log_2p(x)$$

For example if we wanted to communicate the state of an object with 8 possible states where each state is equally likely, then we would need to send 3 bits.

If we wanted to communicate the state of a varialbe with the following probabilities (
$\frac{1}{2}$, $\frac{1}{4}$, $\frac{1}{8}$, $\frac{1}{16}$, $\frac{1}{64}$, $\frac{1}{64}$, $\frac{1}{64}$, $\frac{1}{64}$ ) then on average we would need to send 2 bits of information.  For example the following probabilities would correspond to the following states: (0, 10, 110, 1110, 111100, 111101, 111110, 111111).

Multiplicity can be thought of as the way to spread N items across bins where the number of items in bin $i$ is $n_i$.

$$W = \frac{N!}{\prod_in_i!}$$
Entropy can also be defined as
$$H = \frac{1}{N}ln(W)$$

# Distributions

The Beta distribution can be used to give the probability that some population has a variable (e.g. population probability) given a sample.

The Dirichlet distribution can be used to give the probability that some population has a variable given a sample for a multi variable sample.

Some limitations of the gaussian can be overcome by using the Von Mises Distribution (cyclical) and using mixtures of Gaussians (multiple peaks).

Bernoulli is part of the exponential family.  The exponential distribution has the form:
$p(\vec{x}|\eta) = h(x)g(\eta)e^{\eta^T u(x)}$


A kernel function can be thought of as a probability space in three dimensions with different windows (just like windows in a histogram).  One example is to break space into many hypercubes and have a value of 1 if a sample point lies within the space.  Instead of a value of 1, we can use the gaussian if we want to avoid discontinuities.

K nearest neighbors is a technique to classify a point by looking at it's k nearest neighbors and choosing the most common class. K nearest neighbors can be used in regression by taking the average value of k of the nearest neighbors.

# Linear Regression

## Linear Basis

linear models go by the function:
$y(\vec{x},\vec{w}) = w_0 + \sum \limits_{j=1}^{M-1} w_j \phi_j(\vec{x})$
$\phi$ is the **basis function** and $w_0$ is the **basis parameter**. $\phi$ does not have to be linear.

**spline functions** break the divide the input space and apply different polynomials to each region.

Different types of basis functions include gaussian, sigmoid, polynomial, and wavelets.

To find $\vec{w}_{ML}$:

$\vec{w}_{ML} = (\Phi^T \Phi)^{-1} \Phi^T \vec{t}$.
where, $\Phi$, the design matrix is:
$$\Phi = \begin{bmatrix}
\phi_0(x_1) && \phi_1(x_1) & ... & \phi_{M-1}(x_1) \\
\phi_0(x_2) && \phi_1(x_2) & ... & \phi_{M-1}(x_2) \\
... && ... && ... \\
\phi_0(x_N) && \phi_1(x_N) & ... & \phi_{M-1}(x_N) \\

\end{bmatrix}$$

$\Phi^{\dagger} = (\Phi^T \Phi)^{-1} \Phi^T$. Where $\Phi^{\dagger}$ is known as the Moore-Penrose pseudo-inverse of the matrix $\Phi$.


Finding the maximum likelihood function can be computationally costly for large data sets $O((N_x * N_\phi)^2)$.  In this case it may be worthwhile to us an on-line algorithm like stochastic gradient descent:

$\vec{w}^{(\tau + 1)} = \vec{w}^{(\tau)} -  \eta \nabla E_n$

where $w^{(0)}$ is the starting vector of weights, $\eta$ is the learning rate parameters, and $E_n$ is the Error for some input $x_n$ (????).

To avoid overfitting we can also use
$\vec{w}_{ML} = (\lambda I + \Phi^T \Phi)^{-1} \Phi^T \vec{t}$.

Analogously, for multiple outputs we have:

$$\vec{y}(\vec{x}, \vec{w}) = W^T\vec{\phi}(\vec{x})$$

### Questions ???

* is the first layer of a neural network just $\sigma(\vec{y})$ where $\vec{\phi_0} = 1$ and $\vec{\phi_{i \neq 0}} = x$
* Does the sigmoid help at all?  Wouldn't the first layer already map well?
	* Why two layers?
	* Does the deformation of a topological mapping help (by way of the sigmoid)
* Maybe play around with Cat theory
	* e.g. A set (which a vector belongs to) transforms to a function (technically to a probability of functions for a sample) under the Gaussian transofmation

### Bias-Variance Decomposition
TODO

### Bayesian Models
TODO

### Evidence Approximation
TODO


# Linear Classification

Classification takes an input vector and assigns it to one of K discrete classes.  (The classes are also disjoint in the most common scenario.). The input space is divided into **decision regions** whose boundaries are called **decision boundaries** or **decision surfaces**.

A target vector can represent classes.   For example $(0, 0, 1)$ can represent an object where the third class is valid.

The target vector can also have the probabilities of belonging to a class.  For $\vec{t} = (t_0, t_1, ... ,T_K)^T$, $t_k$ is the probability that the class is $C_k$.

There are three distinct ways (two types) of solving classification problems:
* Creating a discriminant function that assigns $\vec{x}$ to a class
* Creating a conditional probability distribution that assigns $\vec{x}$ to a probability of a class , e.g. $p(C_k|x)$.
	* There are also two different ways of determining the conditional probability distribution

For classification we have a non-linear function $f$ where
$$y_f(\vec{x}) = f(\vec{w}^T \vec{x} + w_0)$$
(if we don't consider $\phi_0 = 1$) where the decision boundary is $y(\vec{x}) = c$.

$f$ is called the **activation function**. The inverse of $f$ is called the **link function**.

$y_f$ is a **generalized linear model** since the decision surfaces are linear functions of $\vec{x}$ (TODO: understand this).

## Discriminant Functions

A simple version of a linear discriminant function is

$$y(\vec{x}) = \vec{w}^T\vec{x} + w_0$$

where $w_0$ is (also) called the **bias** and $\vec{w}$ is the **weight vector**.  The **threshhold** is the negative of the bias.

If we have $y(\vec{x})$ map to $C_1$ if $y \geq 0$, then $y=0$ is the **decision boundary**.

For a $D$ dimensional input space, the decision boundary is a $D-1$ dimensional hyperplane.

$\vec{w}$ determines the orientation of the decision surface and $w_0$ determines it's location.

The decision boundary would be:
$$y(\vec{x}) = \tilde{\vec{w}}^T \tilde{\vec{x}}$$.
where $\vec{w}$ is perpendicular to the decision boundary.

### Multiple Classes

For $k$ multiple classes we have 
$$y_k(\vec{x}) = \vec{w}_k^T = w_{k,0}$$
and assign $x$ to the class with the greatest $y_k$.

### Calculating values for linear discriminant

#### Least squares


#### Fisher's linear discriminant
Fisher's linear discriminant is used to reduce a D-dimensional vector to one dimension using $y=\vec{w}^T\vec{x}$.

#### Perceptron

A Perceptron is a linear discriminant where
$$f(a) = 1 \text{ if } a \geq 0$$$$ 
f(a) = 0 \text{ if } a < 0$$ 
This is a different target scheme that are traditional t vector.

You can use the perceptron to calculate values for the linear discriminant.

## Probabilistic Generative Models

For a class prior of $p(C_k)$ the posterior is

$$p(C_1|x) = \frac{ p(\vec{x}|C_1)p(C_1) }{ p(\vec{x}|C_1)p(C_1) + p(\vec{x}|C_2) p(C_2)}$$

which can be written as

$$\sigma(a) = \frac{1}{1 + exp(-a)}$$
where $$a = ln\frac{p(\vec{x}|C_1)p(C_1)}{p(\vec{x}|C_2)p(C_2)}$$.

$\sigma$ is commonly referred to as the sigmoid.

For more than two classes:
$$p(C_k|\vec{x}) = \frac{exp(a_k)}{\sum_j (exp(a_j))}$$
this is called the **softmax function**.

--------------

If class conditional densities are gaussian around some point then:

$$p(\vec{x}|C_k) =
\frac{1}{(2*pi)^{\frac{D}{2}}} 
\frac{1}{ |\vec{\Sigma}|^{\frac{1}{2}}} 
exp\{
-\frac{1}{2}(\vec{x} - \vec{u}_k) \Sigma^{-1}
(\vec{x}-\vec{u}_k)
\}$$

To find the most likely values of a 2 class system, we have:
$u_{1,ML}= \frac{1}{N_1} \sum \vec{t}_n \vec{x}_n$
$u_{1,ML} = \frac{1}{N_1} \sum (1-\vec{t}_n) \vec{x}_n$
$\Sigma = S$
$S = \frac{N_1}{N}S_1 \frac{N_2}{N}S_2$
$S_1 = \frac{1}{N_1} \sum(\vec{x}_n-\vec{u}_1)(\vec{x}_n-\vec{u}_1)^T$.
$S_2 = \frac{1}{N_2} \sum(\vec{x}_n-\vec{u}_2)(\vec{x}_n-\vec{u}_2)^T$.


# Neural Networks

# Kernel Methods


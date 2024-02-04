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

# Linear Regression

# Linear Classification

# Neural Networks

# Kernel Methods


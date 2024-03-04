# References
Probability Theory: The Logic of Science
probabilitybook.net

# Probability Operations 

The sample space $S$ is the set of all possible outcomes of the experiment.

An event $A$ is a subset of the sample space $S$.

For *disjoint* events:

$P(\bigcup\limits_j A_j) = \sum\limits_j P(A_j)$
$P(\bigcap\limits_j A_j) = \prod\limits_j P(A_j)$

$P(S) = 1$
$P(\{\}) = 0$
$P(A_i \bigcup A_j) = P(A_i) + P(A_j) - P(A_1 \bigcap A_j)$
$P(A|B) = \frac{P(A \bigcap B)}{P(B)}$

$P(B) = \sum\limits_i P(B|A_i)P(A_i)$ (aka the Law of Total Probability)

A **random variable** is a variable that that maps the outcomes of random events to a number (e.g. **X** is 1 if a coin is heads).

## Combinatorics
Number of ways to choose $m$ people from a group of $n$ is $n \choose m$.

Permutation is also $n \choose m$.

## Moments

Moments are quantitative measures related to the shape of a functions graph.

For a probability distribution, $p$, the zeroth moment is the total mass (i.e. 1).

The first moment is the **expected value**, $u$.

For discrete values:

$E[X] = \sum\limits_i x_i p_i$

For continuous values:

$E[X] = \int_{-\infty}^{\infty}xp(x)dx$

The second moment is the **variance**, $\sigma^2$.

For discrete values:

$var(x) = \sum\limits_ip_i \dot (x_i - u)^2$

For continuous values:

$var(x) = \int_{-\infty}^{infty}(x-\mu)^2p(x)dx$


The third moment is skewness(asymmetry)and the fourth moment is kurtosis (tailedness).

Other relations:
$var(x) = E[X^2] - E[X]^2$


## Samples

## Discrete Distributions

### Binomial

The Binomial distribution is useful for finding the probability that a number of attempts will be successful (with replacement).

$Pr(k;n,p) = {n \choose k}p^k(1-p)^{n-k}$

Where $p$ is the probability of success. $k$ is the number of successes.  $n$ is the total number of attempts. 

$E[X] = np$
$var(x) = np(1-p)$

### Bernoulli

The Bernoulli distribution is the binomial distribution when $n=1$. i.e. what is the probability of success on a single try.

### Hypergeometric

The Hypergeometric distribution describes the probability of k successes from $n$ attempts of without replacement from a size of $N$ items with $K$ successful items.

$Pr(k;n,p,N) = \frac{{K \choose k}{N-K \choose n-k}}{N \choose n}$

### Poisson

The Poisson distribution describes the probability of $k$ events happening in a time period, with an average rate of $\lambda$.

$Pr(X=k) = \frac{\lambda^k e^{-\lambda}}{k!}$

$E[X] = var(X) = \lambda$

### Geometric

The probability of getting $k$ failures and then a success.

$Pr(Y=k) = (1-p)^kp$

$E[X] = \frac{1}{p}$
$var(X) = \frac{1-p}{p^2}$

Here $Y$ is the probability of failures before successes and $X$ is the number of trials needed before a success, so $Y = X - 1$.

## Continuous Distributions
### Gaussian (aka normal)

A continuous distribution that has many useful properties.  When many samples ares observed, they often converge to the gaussian due to the central limit theorem.

$Pr(x; \sigma, \mu) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2} (\frac{x-\mu}{\sigma})^2 }$

$E[X] = \mu$
$var(X) = \sigma^2$

## Multivariate Distributions

### Discrete

A **joint** or multivariate distribution is of a form similar to (in the case of two random variables):

$p_{x,y}=P(X=x, Y=y)$

A **marginal** or unconditional distribution is a distribution for only one variable of a multivariate distribution.  E.g. $p_x$ for $p_{x,y}$:

$P(X=x) = \sum\limits_y P(X=x, Y=y)$

The **conditional** distribution is the distribution for a variable given another variable:
$P(X=x|Y=y_1)$.

For Bayes rule with join distributions:

both discrete: $P(Y=y|X=x) = \frac{P(X=x|Y=y) P(Y=y)} {P(X=x)}$
both continuous: $f_{Y|X}(y|x) = \frac{f_{X|Y}(x|y) f_Y(y)}{f_X(x)}$

If X and Y are independent

both discrete: $F_{X,Y}(x,y) = F_X(x) F_Y(y)$
both continuous: $f_{X,Y}(x,y) = f_X(x)f_Y(y)$

There are also hybrid models when one random variable is discrete and another random variable is continuous.

### Covariance

Covariance is the relation of two random variables to each other.  If the covariance between two random variables is 0, then they are independent.

$Cov(X,Y) = E((X-EX)(Y-EY))$
$=E(XY) - E(X)E(Y)$


### Multinomial Distribution

Like the Binomial but with multiples success and failure cases:

$P(X_1=n_1, X_2=n_2, ..., X_k=n_k) = \frac{n!}{n_1!n_2!...n_k!} p_1^{n_1}p_2^{n_2}...p_k^{n_k}$

### Multivariate Gaussian

TODO: ... explained well in pattern recognition

## Transformations

$f_Y(y) = f_X(x)|\frac{dx}{dy}|$

## 
## Other useful things

Beta

Gamma













## Markov Chains
1.1 We want to find the $w$ that minimizes $E$.

$$E = \frac{1}{2} \sum_{n} \{y(x_n, w) - t_n\}^2$$
$$y(x_n,w) = \sum_j(w_jx^j)$$
We want to find $\frac{dE}{dw}$ which is
$$\frac{d}{dw}(\frac{1}{2}\sum_n\{\sum_j(w_jx^j) - t_n\}^2)$$
$$\frac{1}{2} \sum_n \{\frac{d}{dw} (\sum_jw_j x^j) - t_n)^2\}$$
$$\sum_n(\sum_j(w_jx^j - t_n)*\sum_j(x^j))$$
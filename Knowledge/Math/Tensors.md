From eigenchris and David Tong

A contravarient vectors transform to the opposite of a change in basis.  E.g. if the basis is halved than the contravariant vector will double.  These are usually just called vectors.

The metric space for contravariant vectors is

$$(V, S, *, +)$$

A covariant vector transform the same way as the change in basis.  These are usually called Covectors.

The metric space for covectors is

$$(V^*, S, *, +)$$
where V* is a mapping from V to a scalar.

----------------

The $ith$ component of vectors are typically written as $v^i$ .
The vector can be written as $\vec{v} = v^ie_i$.

The $ith$ component of covectors are written as $c_j$.
The covector can be written as $\vec{c} = c_i \epsilon^i$

Note: An index in the subscript indicates that the item scales with the basis change.  An index in the superscript indicates that the item scales against the basis change.


Instead of writing vector multiplication as $$
\begin{bmatrix}
c_1, c_2, c_3
\end{bmatrix}

\begin{bmatrix}
v_1 \\ v_2 \\ v_3
\end{bmatrix}$$
We can write it as a sum.   In einstein notation we drop the summation sign.a

$$y = \sum_\limits{i=1}^3 v^ic_i
= v^1c_1 + v^2c_2 + v^3c_3 =
v^ic_i$$

A covector kind of sets the direction of a topographical map.

-------------
Transformations:
$$B=F^{-1}$$
For covariant (0,1):

$$c_j' = F^i_jc_i$$
$$e_j' = F^i_je_i$$
For contravariant (1,0):
$$x'^i=B^i_j x^j$$
$$\epsilon'^i=B^i_j \epsilon^j$$
For tensor (1,1):
$$L'^i_j = B^i_k L^k_l F^l_j$$

Note: The above is linear map that makes a copy of the basis and transforms (stretches + rotates) it.

For tensor (0,2):
$$g'_{ij} = F^k_i F^l_j g_{kl}$$
$$$$
------------------

A tensor product distributes the thing on the left to each item on the right.  Example:

$$\vec{v} \otimes \alpha =
\begin{bmatrix}
v^i \\ v^j \\ v_k
\end{bmatrix}
\begin{bmatrix}
\alpha_a, \alpha_b, \alpha_c
\end{bmatrix} =

\begin{bmatrix}
\alpha_a
\begin{bmatrix}
v^i \\ v^j \\ v_k
\end{bmatrix},
\alpha_b,\begin{bmatrix}
v^i \\ v^j \\ v_k
\end{bmatrix}, \alpha_c\begin{bmatrix}
v^i \\ v^j \\ v_k
\end{bmatrix}
\end{bmatrix} =

\begin{bmatrix}
\alpha_a v^i && \alpha_b v^i &&  \alpha_c v^i \\
\alpha_a v^j && \alpha_b v^j &&  \alpha_c v^j \\
\alpha_a v^k && \alpha_b v^k &&  \alpha_c v^k \\
\end{bmatrix}
$$

This is technically the Kroenecker delta, but it's basically a tensor product.  For a "real" tensor product, each entry is like $e_i \otimes \epsilon^j$ (e.g. a matrix with only one zero).


------------------
TODO: Tensor as a combination of vectors and covectors

$$D^i_{jk} = 
\begin{bmatrix}
\begin{bmatrix}
\begin{bmatrix}
v \\ w
\end{bmatrix}
\begin{bmatrix}
x \\ y
\end{bmatrix}
\end{bmatrix} &&
\begin{bmatrix}
\begin{bmatrix}
a \\ b 
\end{bmatrix}
\begin{bmatrix}
c \\ d 
\end{bmatrix}
\end{bmatrix}
\end{bmatrix}
$$

$$D^i_{jk} = D^i_{jk}e_i\epsilon^j \epsilon^k$$ but we typically omit the basis.

---------------------
TODO: examples: electromagnetic tensor, other stuff from david tong....

--------------------
TODO in a long time: derivatives
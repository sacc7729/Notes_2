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
Differential forms are covectors:
$$df = \frac{\partial f}{\partial x^i}dx^i$$
and
$$\nabla_v f = df(v)$$

The derivative is a vector:
$$\frac{dR}{d\lambda} = \frac{dx_i}{d\lambda}\frac{\partial R}{\partial x_i} =
\frac{dx_i}{d\lambda}\hat{x_i}$$ since $$R=x_i\hat{x_i}$$

The Jacobian is the backward/forward transform
$$J=\frac{\partial f_i}{\partial x_j}$$

---------------------------

TODO(metric tensor and see if this is correct)

The first fundamental form $ds^2$ is inviariant under coordinate transforms.

So is the second fundamental form 

----------------------------------
Intrinsic vs External geometry

For some $x_i \in R^n$ and $x_j \in R_m$ where n < m.  Then
$$\frac{dR}{d \lambda} = \frac{dx_i}{d \lambda}\frac{\partial R}{\partial x_i}$$ is intrinsic and 

$$\frac{dR}{d \lambda} = \frac{dx_j}{d \lambda}\frac{\partial R}{\partial x_j}$$ is extrinsic.

------------------------

The arc length of a curve is given by
$$s = \int ||\frac{dR}{d\lambda}|| d\lambda$$
$$=\int \sqrt{\frac{dR}{d\lambda} \frac{dR}{d\lambda}} d\lambda$$
$$\int \sqrt{ds^2}$$
where we defined $ds^2$ by the above equation.  $ds^2$ is known as the first fundamental form and is invariant in all coordinates.

For some extrinsic space in $R^n$. We can embed a surface.

For example:

$$(u(\lambda), v(\lambda)) \rightarrow (x(\lambda), y(\lambda), z(\lambda))$$
$$\frac{dR}{d\lambda} \cdot \frac{dR}{d\lambda} $$
$$=(\sum \frac{\partial R}{\partial x_i} \frac{dx_i}{d \lambda}) \cdot 
(\sum \frac{\partial R}{\partial x_i} \frac{dx_i}{d \lambda})$$

For the u,v example, this means that:
$$ds^2 =
\begin{bmatrix}du & dv \end{bmatrix}
\begin{bmatrix}
\frac{\partial R}{\partial u}\frac{\partial R}{\partial u} & \frac{\partial R}{\partial u}\frac{\partial R}{\partial v} \\
\frac{\partial R}{\partial v}\frac{\partial R}{\partial u} & \frac{\partial R}{\partial v}\frac{\partial R}{\partial v}
\end{bmatrix}
\begin{bmatrix}du \\ dv\end{bmatrix}$$
The inner portion is known as the metric tensor $g$. 

This means that if we have some mapping onto $R^n$ then we can create a $ds^2$ that is invariant of the surface we bound ourselves too / the basis we take.

Since $\frac{\partial R}{\partial u} = \hat{u}$ then we can write the metric tensor in basis form.
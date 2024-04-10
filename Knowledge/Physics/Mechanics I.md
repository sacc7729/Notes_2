# Prequisites

# References
University Physics with Modern Physics (Ch 1 - 14)

David Tong

## Newtonian

$$\vec{F} = \dot{\vec{p}}$$

where

$$\vec{p} = m \vec{r}$$

If $\dot{m} = 0$, then (Newton's first law):

$$\vec{r} = \vec{r}_0 + \vec{v} t $$

An inertial frame is not unique.  It holds for 10 transformations:
(3) Rotational $\vec{r}' = O\vec{r}$
(3) translational $\vec{r}' = \vec{r} + \vec{c}$
(3) boosts $\vec{r} = \vec{r} + \vec{u}t$
(1) time $t' = t + c$

These transformations make up the Galilean Group.


TODO: look at this group
------------------------

Angular Momentum $\vec{L} = \vec{r} \times \vec{p}$.
Torque $\vec{\tau} = \vec{r} \times \vec{F}$
These values depend on where we take the origin.

If $\dot{\vec{r}} \times \vec{p} = 0$ then $\frac{d}{dt}(\vec{L}) = \vec{\tau}$.


Conservation laws:

$\vec{F} = 0 \implies \vec{p} = c_0$
$\vec{\tau} = 0 \implies \vec{L} = c_1$



## Lagrangian

TODO, questions from apple notes

(e.g. what happens when F not conservative, can we do calculus like that, why $y = y_0 + y_{minimizing}$.

For conservative forces, $F=m\vec{a}$ is equivalent to:
$$
\frac{\partial L}{\partial x^A} -
\frac{d}{dt}
\frac{\partial L}{\partial \dot{x}^A} =
0
$$

where
$$
L(x^A, \dot{x}^A) =
T(\dot{x}^A) - V(x^A)
$$

where
$T= \frac{1}{2} mv^2$ and $V$ is the potential energy.

$$
\frac{\partial L}{\partial x^A} -
\frac{d}{dt}
\frac{\partial L}{\partial \dot{x}^A} =
0
$$
The above equation is also equivalent to finding the extrenum $S$ such that
$$
S[x^A(t)] =
\int L(x^A(t),\dot{x}^A(t)) dt
$$
from the calculus of variations.

Note: you have to use a modified lagrangian for non conservative forces (see Hamilton's principle).

## Hamiltonian

$$H =
\sum \dot{q}\frac{\partial L}{\partial \dot{q}} -
L
$$
## Noethers

If
$$
\frac{\partial}{\partial s} 
L(
Q_i(s,t),
\dot{Q}_i(s,t),
t
)
= 0
$$
then 
$$
\frac{\partial L}{\partial \dot{q_i}}
\frac{\partial Q_i}{\partial s}
$$

is constant.

Example: $Q_i = \vec{r} + s\vec{n}$ and $Q_i = \dot{\vec{r}}$ implies the total linear momentum in direction n, ($p_i \cdot n$), is conserved.
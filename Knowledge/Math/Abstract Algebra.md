# Prequisites

# References

\section{Fundamentals}
 For any set $A$, we define an operation, $*$, to have the following properties
 \begin{equation}
  a*b \text{ is defined for every pair}
 \end{equation}
 \begin{equation}
  a*b \text{ is uniquely defined}
 \end{equation}
 \begin{equation}
  a*b \in A
 \end{equation}
 
 An operation may have the following properties
 \begin{equation}
  a*b = b*a \text{ (commutative)}
 \end{equation}
 \begin{equation}
  (a*b)*c = a*(b*c) \text{ (associative)}
 \end{equation}
 
 There may be some identity element, $e$, such that
 \begin{equation}
  \forall a \in A \text{, } e*a = a
 \end{equation}
 and
 \begin{equation}
  \forall a \in A \text{, } a*e = a
 \end{equation}
 
 There may be some inverse, $a^{-1}$, such that
 \begin{equation}
  a*x = e
 \end{equation}
 and
 \begin{equation}
  x*a = e
 \end{equation}
 
 \section{Groups}
 A group is a set $G$ with an operation $*$ such that 
 \begin{enumerate}
\item $*$ is associative
\item $e \in G$
\item $\forall a \in A \text{, } \exists \ a^{-1}$
\end{enumerate}

A group that is also commutative is an abelian group.

It can be shown that there exists only one $e \in G$.  There is also only one unique $a^{-1} \in G$ for each $a \in G$.

The order of a group, $|G|$, is the number of element in the set $G$.

A subgroup $S$ of a group $G$ is defined as
\begin{enumerate}
 \item $S \subset G$
 \item $S$ is a group
\end{enumerate}

\section{Functions}
\subsection{Fundamentals}
A function $f: A \rightarrow B$, is the mapping to some element in $B$ for every element in $A$. 

A function $f: A \rightarrow B$, is injective if each element of B is the image of no more than one element of A (aka no collisions).

A function $f: A \rightarrow B$, is surjective if each element of B is the image of at least one element of $A$ (aka all of B is covered).

A function is bijective if it is both injective and surjective.

A compositve function $f \circ g$ is defined as
\begin{equation}
 [f \circ g] = f(g(x))
\end{equation}

\subsection{Permutations}
A permutation $f$, is a bijective function from $A$ to $A$ (aka rearrangement).  The set of all possible permutations of $A$ with the operation $\circ$ is a group denoted as $S_A$.  

A cycle is a composition of permutations that maps some element in $A$ to itself.  For example:
 \[
  f(n) =
  \begin{cases}
                                   0 & \text{if $n=0$} \\
                                   2 & \text{if $n=1$} \\
                                   3 & \text{if $n=2$} \\
                                   1 & \text{if $n=3$} \\
  \end{cases}
\]

would have the following cycles (0) and (1,2,3).  Every permutation is either the identity, a single cycle, or a product of disjoint cyles.

\subsection{Isomorphism}
For two groups $<G_1, *>$ and $<G_2, +>$ an isomorphism $f: G_1 \rightarrow G_2$ is a bijection function such that
\begin{equation}
 f(a * b) = f(a) + f(b)
\end{equation}
If there exists some isomorphism between two groups, the groups are said to be isomorphic.

For example:
\begin{center}
\begin{tabular}{ c|ccc } 
 * & a & b & c\\ 
 \hline
 a & a & b & c\\ 
 b & b & c & a\\ 
 c & c & a & b\\
\end{tabular}
\end{center}

and 

\begin{center}
\begin{tabular}{ c|ccc } 
 + & d & e & f\\ 
 \hline
 d & d & e & f\\ 
 e & e & f & d\\ 
 f & f & d & e\\
\end{tabular}
\end{center}

are isomorphic.

\section{Cyclic Groups}
\begin{equation}
 a^n = a * a * .... * a \text{ (n times)}
\end{equation}
\begin{equation}
 a^m * a^n = a^{m+n}
\end{equation}
\begin{equation}
 (a^m)^n = a^{mn}
\end{equation}
\begin{equation}
 a^{-n} = (a^{-1})^n = (a^n)^{-1}
\end{equation}

If $G$ is some group and $a \in G$ and if $G$ consists all of the powers of $a$
\begin{equation}
 G = \{ a^n: n \in \Z \}
\end{equation}
then $G$ is called a cyclic group (sometimes written as $ \langle a \rangle$).

$\Z_{n}$ is the set of integers modulo n. 

\section{Equivalence Relations}
A partition of set $A$ is the union of disjoint sets of $A_i$.  

An equivalence relation $\sim$, is a relation such that 
\begin{equation}
 \forall x \in A \text{, } x \sim x \text{ (reflexive)}
\end{equation}
\begin{equation}
 \text{if } x \sim y \text{, } y \sim x \text{ (symmetric)}
\end{equation}
\begin{equation}
 \text{if } x \sim y \text{ and } y \sim z \text{, then } x \sim z \text{ (symmetric)}
\end{equation}


\section{Cosets}
A (right) coset, $Ha$, of $H$ in $G$ is defined as 
\begin{equation}
 Ha = \{h*a : h \in H\}
\end{equation}
where $H \subset G$, $G$ is a group, and $a \in G$.

The family of all cosets of $Hx$ is a partition on $G$ (aka you can escape to some partition in $G$ from $H$ by some operation $*$).  The family of all cosets of $Hx$ on $G$ is written as $G/H$.

For example: $H = \{0,2\} \text{ and } G=\Z_4$

\section{Homomorphisms}
For two groups $<G_1, *>$ and $<G_2, +>$ an isomorphism $f: G_1 \rightarrow G_2$ is a function such that
\begin{equation}
 f(a * b) = f(a) + f(b)
\end{equation}
for $a,b \in G_1$.

A kernel, $K$, is defined as
\begin{equation}
 K=\{x \in G : f(x) = e\}
\end{equation}

If some homomorphism $f: G \rightarrow H$ with kernel $K$
\begin{equation}
 f(a) = f(b) \text{ iff } Ka = Kb
\end{equation}

The fundamental homomorphism theorem is
\begin{equation}
 H \sim G/K
\end{equation}

\section{Rings}

\subsection{Fundamentals}
A ring, $A$, is some set with two operations $+$ (addition) and $\times$ (multiplication) such that
\begin{enumerate}
 \item $\langle A, + \rangle$ is an Abelian group
 \item Multiplication is associative
 \item Multiplication is distributive over addition
\end{enumerate}

\subsection{Homomorphism}
A homomorphism (for a ring) is a function $f$ from ring $A$ to ring $B$ such that 
\begin{equation}
 f(x_1 + x_2) = f(x_1) + f(x_2)
\end{equation}
and
\begin{equation}
 f(x_1 \times x_2) = f(x_1) \times f(x_2)
\end{equation}

\subsection{Quotient Rings}
A coset of $J$ in $A$ is defined as
\begin{equation}
 J + a = \{j+a: j \in J\}
\end{equation}

The family of all cosets of $J$ is a parition of $A$

\section{Fields}
A neutral element under multiplication is called a unity.  When multiplication is commutative in a ring, the ring is called a commutative ring.  If a commutative ring has the unity element, it is called a communitative ring with unity.  A communitative ring in which every non-zero element is invertible is called a field.

\subsection{Extensions of fields}
If $F$ is a field, then a subfield of $F$ is some nonempty subset of $F$ that is closed under addition, negative addition, multiplication, and multiplicative inverses.  If $K$ is a subfield of $F$, then $F$ is an extension field of $K$.

\section{Galois Theory}













 
\end{document}


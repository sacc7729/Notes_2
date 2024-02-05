

# Introduction

A set is a collection of distinct elements.  A set is denoted by $\{\}$.  Examples:

$\{4,5,6\}$ is the set which contains 4, 5, and 6.
$\{red, blue, green, purple\}$ is a set which contains some colors.

$x \in A$ denotes x is an element of A.

Some general properties:

$A \subseteq B \text{ iff } x \in A \implies x \in B$ -> A is a subset of B
$A=B \text{ iff } A \subseteq B \text{ and } B \subseteq A$ -> A is equal to B
$A \bigcup B = \{x:x \in A \text{ or } x \in B\}$ -> union
$A \bigcap B = \{x:x \in A \text{ and } x \in B\}$ -> intersection
$A^C  = {x: x \notin A}$ -> Compliment


$(A \bigcup B)^C = A^C \bigcap B^C$ - > De Morgan's Law

Unions and Intersections are commutative, associative, and idempotent.  

$A \bigcap (B \bigcup C) = (A \bigcup B) \bigcap (A \bigcup C)$ -> Distributive

$A-B = A \bigcap B^C$


# Useful Sets

$\{a, b\}$ -> unordered pair
$(a,b) = \{\{x\},\{x,y\}\}$ -> ordered pair.  a is the first element and b is the second element
$A \times B = {(x,y): x \in A \text{ and } y \in B}$
$G = \{(a,b): a = x \text{ and } b = f(x)\}$ -> Graph
$G \circ H = \{(x,y): (x,z) \in H \text{ and } (z,y) \in G\}$
$\text{ dom } G = \{x: (x,y)\in G\}$
$\text{ ran } G = \{y: (x,y)\in G\}$
$\{A_i\}_{i \in I} = \{A_1, A_2, ..., A_n\}$
$\bigcup\limits_{i \in I} A_i = \{x: x \in A \text{ for some } A_i\}$
$\bigcap\limits_{i \in I} A_i = \{x: x \in A \text{ for all } A_i\}$
$\prod\limits_{n}A_n = A_0 \times A_1 \times ... \times A_n$

A partition of A is $\{A_i\}_{i \in I}$  such that:
1. $\forall i,j \in I, A_i \bigcap A_j = 0 \text{ or } A_i = A_j$
2. $A=\bigcup\limits_{i \in I}A_i$




# Functions

A function, $f: A \rightarrow B$ , is a graph such that:

1. $\forall x \in A, \exists y \in B \text{ such that } (x,y) \in f$
2. $\text{if } (x,y_1) \in f \text{ and } (x,y_2) \in f \text{, then } y_1 = y_2$

y is the image of x with respect to f
x is the pre-image of y with respect to f

A function is injective if:

1. $\text{if } (x_1, y) \in f \text{ and } (x_2,y) \in f \text{, then } x_1 = x_2$

A function is surjective if:
1. $\forall y \in B, \exists x \in A \text{ such that } (x,y) \in f$

A function is bijective if it is injective and surjective.

Let $C \subseteq A$ for $f: A \rightarrow B$.  Then the direct image of C under f is

$\bar{f}(C) = \{y \in B: \exists x \in C \text{ and } y = f(x)\}$

The inverse image of D under f is the class of all pre-image of elements in D:

$\breve{f}(D) = \{x \in A: f(x) \in D\}$






# Relations

A relation $G \in A \times A$ is defined as

$\{(x,y): R(x,y) \text{ is true } \}$

Some possible properties:

$\forall x \in A, (x,x) \in G$ (reflexive)
$\forall x \in A (x,x) \notin G$ (irreflexive)
$(x,y) \in G \rightarrow (y,x) \in G$ (symmetric)
$(x,y) \in G \rightarrow (y,x) \notin G$ (asymmetric)
$(x,y) \in G \text{ and } (y,x) \in G \rightarrow x = y$ (anti-symmetric)
$(x,y)\in G \text{ and } (y,z) \in G \rightarrow (x,z) \in G$ (transitive)
$(x,y) \in G \text{ and } (y,z) \in G \rightarrow (x,z) \notin G$ (intransitive)

An equivalence relation is a relation that is reflexive, symmetric, and transitive.

An order relation is a relation that is reflexive, antisymmetric and transitive.

A strict order relation is a relation that is irreflexive, asymmetric, and transitive.


# Natural Numbers

We can construct $\mathbb{N}$ by 0 = $\{\}$ and $n+1 = n \bigcup \{n\}$.


## Note on Classes

Classes can lead to paradoxes so we use sets.

E.g. The class of all classes that don't contain themselves is a paradox.  We can use the term set to get rid of the paradoxes.












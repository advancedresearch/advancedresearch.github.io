# Avatar Extensions

This page is for organizing all important ideas about Avatar Extension in one place.

[Reading Sequence of papers](https://github.com/advancedresearch/path_semantics/blob/master/sequences.md#avatar-extensions)

### Avatar Logic

For an experimental implementation, see [Avalog](https://github.com/advancedresearch/avalog).

Avatar Logic replaces predicates with binary relations with some additional axioms:

```text
p(a, b)         b : p           p(a) = b
p(a, q'(b))     q'(b) : p       p(a) = {q'(_)} ∈ q'(b)
```

This means that `(a, b)` contains all information needed to represent a labeled edge.

```text
b : p             `b` has the role `p`
q'(b)             the `q` 1-avatar of `b`
p(a) = q'(b)      the `p` property of `a` is `q'(b)`
p(a) => q'(b)     the `p` property of `a` has `q'(b)`
.q'(b) = b        the inner operator is a `.` in front of an expression
uniq q            make the `q` 1-avatar behave uniquely
```

### Avatar Algebra

Avatar Algebra relates theorems in algebra to theorems about Avatar Extensions.

```
*     introduction operator
1     the natural 1-avatar
0     the contracting 1-avatar
-     negation is an involution that covers symmetries in products
+     symmetry operator
```

Theorems:

```
a * 1 = 1 * a = a                       introduction of new 1-avatar
-(a * b) = (-a) * b = a * (-b)          coverage of products using 1->1 avatar involutions
(a + b) * f(x) = a * f(x) + b * f(x)    superposition of mathematical objects related to 1-avatar symmetry
(a * b) * c = a * (b * c)               associativity is a 6-avatar of a 9-vertex filled avatar graph
a + b = b + a                           symmetry between 1-avatars
```

### Avatar Graphs

For visualization, see [Avatar-Graph](https://github.com/advancedresearch/avatar_graph).

The "core self" is an object which has no internal relations for introspection.
Avatars are created to model relations.

- A 1-avatar is directly communicating with the core, but can not communicate with each other
- A 2-avatar integrates information between two 1-avatars
- A 3-avatar integrates information between three 1-avatars, or one 2-avatar plus one 1-avatar
- An N-avatar integrates information between a partition of lower avatars

Information must be passed down from higher avatars in the direction of the core.
An Avatar Graph "forgets" which node is the core.

- A black node represents a core candidates
- A white node represents an N-avatar with smallest N greater than zero
- A black edge connects two avatars
- A gray/dashed edge identifies a unique highest N-avatar per core

![square](./images/avatar4-01.png)
![5-avatar](./images/avatar5-01.png)
![wagner](./images/wagner.png)
![wagner-mobius](./images/wagner-mobius.png)
![counter example to 2^n conjecture](./images/avatar6-03.png)
![associativity](./images/associativity.png)

A filled Avatar Graph consists only of core candidates.

- Every hypercube is a filled Avatar Graph
- Wagner graph is a filled Avatar Graph with Möbius topology
- Filled Avatar Graphs are bases for groupoid self-similarity

A reflection witnessed by a product `(x, x)` is impossible to model in an Avatar Graph.
This means that a "copy" of `x` must be constructed, which eventually requires copies of 1-avatars.
Translated into a theorem about Avatar Extensions, this means 1->1 avatars "covers" products.

### Avatar Semantics

The [core axiom](https://github.com/advancedresearch/path_semantics/blob/master/sequences.md#foundation) of [Path Semantics](https://github.com/advancedresearch/path_semantics) can be naively modeled in Avatar Logic as following:

```
(C, D) :- (A, B), (B, A), (A, C), (B, D).
```

This propagates products from every identity morphisms using outgoing arrows.
Adding this axiom to Category Theory collapses a category into a partial groupoid.
It is kind of like extending a square matrix.
Can also be thought of as a compact representation of an equivalence class.

The analogue for isomorphisms (without identity morphisms) constructs the following way:

![step1](./images/iso-step1.png)
![step2](./images/iso-step2.png)
![step3](./images/iso-step3.png)

Step 1 is the smallest possible example of a Möbius topology.

In [Path Semantical Logic](https://github.com/advancedresearch/path_semantics/blob/master/sequences.md#path-semantical-logic),
propositions are separated by levels, which gets rid of Möbius topology.
Applying the core axiom to a single level would contract all propositions along implications,
because of reflexivity `x = x` is a tautology.

In the language of graphs, it is possible to avoid contraction in a single level since identity morphisms are not necessary.

The diagonals corresponds to highest N-avatars in hypercubes,
which can be interpreted as the smallest reduction of an inconsistent theory to a consistent theory.

For example, Giard's paradox is avoided in type systems by using cumulative universes or types.
The highest N-avatars in this context are morphisms between type levels, which are just type memberships.
Therefore, Type Theory is essentially a highest N-avatar reduction to make modeling of mathematics consistent.

The diagonals on a cube can be thought of as swap operations,
which generates all permutations by selecting a face + rotation in the plane:

![swap-cube](./images/cube-swap.png)

This interpretation is the only one that preserves structure.

Group Theory might be thought of as operations on highest N-avatars satisfying the notion of "resources" in linear logic.

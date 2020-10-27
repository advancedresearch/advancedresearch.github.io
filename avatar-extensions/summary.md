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
p(a) = q'(b)      the `p` property of `a` is `b`
p(a) => q'(b)     the `p` property of `a` has `b`
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
a * 1 = 1 * a = a                       introduction of new 1->1 avatar
-(a * b) = (-a) * b = a * (-b)          coverage of symmetries using 1->1 avatar involutions
(a + b) * f(x) = a * f(x) + b * f(x)    superposition of mathematical objects related to 1-avatar symmetry
```

### Avatar Graphs

The "core self" is an object which has no internal relations for introspection.
Avatars are created to model relations.

- A 1-avatar is directly communicating with the core, but can not communicate with each other
- A 2-avatar integrates information between two 1-avatars
- A 3-avatar integrates information between three 1-avatars, or one 2-avatar plus one 1-avatar
- An n-avatar integrates information between a partition of lower avatars

Information must be passed down from higher avatars in the direction of the core.
An Avatar Graph "forget" which node is the core.

- A black node represents a core candidates
- A white node represents an N-avatar with smalles N larger than zero
- A black edge connects two avatars
- A gray/dashed edge identifies a unique highest N-avatar per core

![square](https://raw.githubusercontent.com/advancedresearch/avatar_graph/master/images/avatar4-01.png)

![5-avatar](https://raw.githubusercontent.com/advancedresearch/avatar_graph/master/images/avatar5-01.png)

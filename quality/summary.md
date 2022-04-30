# Path Semantical Quality

Path Semantical Quality is a partial equivalence relation that lifts biconditions with symbolic distinction.

This page is for organizing all important ideas about quality in one place.

[Paper](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/path-semantical-quality.pdf)

The model of Path Semantical Quality is formalized in [Prop](https://github.com/advancedresearch/prop).

### Notation

A quality between `a` and `b` is written:

```
a ~~ b
```
In Prop, this is written `Q<A, B>`.

### Path Interpretation

A [homotopy path](https://en.wikipedia.org/wiki/Homotopy) is a path between paths such that one path can be deformed into another.

![homotopy path](https://upload.wikimedia.org/wikipedia/commons/7/7e/HomotopySmall.gif)

`a ~~ b` means that there is a path between two paths `a` and `b`.

Notice that there is a slight difference in terminology between "homotopy path" and "path":

- `(a => b) => (a ~~ b)` a homotopy path in [univalence foundations](https://en.wikipedia.org/wiki/Univalent_foundations) (`Hom<A, B>` in Prop)
- `a ~~ b` a path between `a` and `b` (`Q<A, B>` in Prop)

To avoid ambiguity, one can say "quality" instead of "path".

### Homotopy paths, Univalence and Symbolic Distinction

A homotopy path implies univalence (`(a == b) ~~ (a ~~ b)`, `Univ<A, B>` in Prop).
However, univalence does not imply a homotopy path.
Therefore, a homotopy path is a stronger assumption than univalence.

Univalence is equal to symbolic distiction (`(a == b) => (a ~~ b)`, `EqQ<A, B>` in Prop).

### Space and Pieces

A space is a mathematical structure, which is a set, sometimes called a "universe",
with some added structure.

A piece is a part of a space that is connected by paths.

For an introduction, see lecture by Vladimir Voedvodsky ["An Intuitive Introduction to Motivic Homotopy Theory"](https://www.youtube.com/watch?v=b4BlA7NymIE).

### Quality and Inquality in Philosophy

In philosophy, quality and inquality has deep consequences for mathematical languages that are biased toward Platonism or Seshatism respectively.

[Avatar Extensions](https://advancedresearch.github.io/avatar-extensions/summary.html)
is an abstraction generalization technique that exploits symmetries inside “simpler” theories.
There is a more complex theory behind quality and inquality in Avatar Extensions that is called
["Avatar Witness Theory"](https://advancedresearch.github.io/avatar-extensions/summary.html#avatar-witness-theory).

### Quality and Inquality in Logic

In the context of logic, we use the terms "quality" and "inquality" to make the language more precise.
This means, "quality" and "inquality" refers to the logical structure without any interpretation.
However, in Prop, it is common that tactics for inquality use "sesh" as a shorthand.

- Quality: `a ~~ a` (Self-Quality) or `a ~~ b` (Other-Quality)
- Inquality: `!(a ~~ a)` (Self-Inquality) or `!(a ~~ b)` (Other-Inquality)

### Quality and Inquality in Topology

In topology, quality and inquality is related to connectedness of pieces:

- Other-Quality implies topological connectedness (paths)
- Other-Inquality implies topological disconnectedness (holes)

Holes are absence of paths between pieces of spaces.
This *does not* imply that the truth value of the pieces are inequal.
In fact, one must use symbolic distinction to convert a hole into inequality.
This means that when two pieces are disconnected and no symbolic distinction is used,
any hole between them does not enforce the truth value of each piece.

Self-inquality `!(a ~~ a)` implies a hole `!(a ~~ b)` for any proposition `b`.

### Homotopy Limit

A homotopy limit of `a` is defined as:

```
(a ~~ a) => a
```

In Prop, one can use the `QId` trait to do homotopy limits.

### PSQ - Path Semantical Quantum Propositional Logic

PSQ extends PL (Classical Propositional Logic) with a `qubit` and `qual/q` operators.

You can find an implementation in the [Pocket-Prover](https://github.com/advancedresearch/pocket_prover) library.

List of theorems:

| Name | Formula |
| ------------ | ------------------------------------ |
| Qual-Platonism-Product | `(a ~~ b) => ((a ~~ a) ⋀ (b ~~ b))` |
| Qual-Seshatism-Sum | `(¬(a ~~ a) ⋁ ¬(b ~~ b)) => ¬(a ~~ b)` |
| Qual-Symmetry | `(a ~~ b) => (b ~~ a)` |
| Qual-Transitivity | `((a ~~ b) ⋀ (b ~~ c)) => (a ~~ c)` |
| Qubit-Excluded-Middle | `qubit(a) ⋁ ¬qubit(a)` |
| Qubit-Qual | `qubit(a) == (a ~~ a)` |

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

PSQ extends PL (Classical Propositional Logic) with a `~` operator (called a "qubit"),
which is used to define `~~` and `hom_eq`.

You can find an implementation in the [Pocket-Prover](https://github.com/advancedresearch/pocket_prover) library.

Technically, one can use `~~` only, but the implementation is easier to understand in terms of the `~` operation.

List of theorems:

| Name | Formula |
| ------------ | ------------------------------------ |
| Aqual-Definition | `(a ~¬~ b) == ((a == b) ⋀ ¬~a ⋀ ¬~b)` |
| Cont-Definition | `(a ~> b) == ((a => b) ⋀ (~a => ~b))` |
| Cont-Reflexivity | `a ~> a` |
| Cont-Transitivity | `(a ~> b) ⋀ (b ~> c) => (a ~> c)` |
| Contra-Qual-Antisymmetry | `((a ¬~~ b) ⋀ (b ¬~~ a)) => (a == b)` |
| Contra-Qual-Asymmetry | `(a ¬~~ b) => ¬(b ¬~~ a)` |
| Contra-Qual-Definition | `(a ¬~~ b) == ((a == b) ⋀ ¬~a ⋀ ~b)` |
| Contra-Qual-Contrapositive | `(a ¬~~ b) == (¬b ¬~~ ¬a)` |
| Contra-Qual-Irreflexivity | `¬(a ¬~~ a)` |
| Eq-Catuskoti | `(a == b) == ((a ~~ b) ⋁ (a ~¬~ b) ⋁ (a ¬~~ b) ⋁ (b ¬~~ a))` |
| Hom-0 | `hom_eq(0, a, b) == true` |
| Hom-1 | `hom_eq(1, a, b) == (a == b)` |
| Hom-2 | `hom_eq(2, a, b) == ((a == b) ⋀ (~a == ~b))` |
| Hom-2-Cont | `hom_eq(2, a, b) == ((a ~> b) ⋀ (b ~> a))` |
| Hom-2-Qual | `hom_eq(2, a, b) == ((a ~~ b) ⋁ (a ~¬~ b))` |
| Hom-Lim | `lim n -> ∞ { ¬hom_eq(n, a, b) }` |
| Hom-N | `hom_eq(n, a, b) == ∀ i n { qubit^i(a) == qubit^i(b) }` |
| Hom-Reflexivity | `hom_eq(n, a, a)` |
| Hom-Symmetry | `hom_eq(n, a, b) => hom_eq(n, b, a)` |
| Hom-Transitivity | `hom_eq(n, a, b) ⋀ hom_eq(n, b, c) => hom_eq(n, a, c)` |
| Hom-Xor | `hom_eq(2, a, b) == xor(a ~~ b, a ~¬~ b)` |
| Qual-Definition | `(a ~~ b) == ((a == b) ⋀ ~a ⋀ ~b)` |
| Qual-Hom | `(a ~~ b) => hom_eq(2, a, b)` |
| Qual-Platonism-Product | `(a ~~ b) => ((a ~~ a) ⋀ (b ~~ b))` |
| Qual-Seshatism-Sum | `(¬(a ~~ a) ⋁ ¬(b ~~ b)) => ¬(a ~~ b)` |
| Qual-Symmetry | `(a ~~ b) => (b ~~ a)` |
| Qual-TransiTivity | `((a ~~ b) ⋀ (b ~~ c)) => (a ~~ c)` |
| Qual-TransPort | `((a ~~ a) ⋀ hom_eq(2, a, b)) == (a ~~ b)` |
| Qubit-Excluded-Middle | `~a ⋁ ¬~a` |
| Qubit-0 |  `qubit^0(a) == a` |
| Qubit-1 | `qubit^1(a) == ~a` |
| Qubit-Not | `~¬a == ¬~a` |
| Qubit-Qual | `~a == (a ~~ a)` |

#### Translation from PSQ into Homotopy Type Theory

| PSQ | HoTT |
| ------------ | ------------------------------------ |
| `a` | `x : isContr(A)` |
| `¬a` | `x : isContr(A) -> ⊥` |
| `~a` | `x : A` |
| `a => b` | `f : isContr(A) -> isContr(B)` |
| `a => ~a` | `f : isContr(A) -> A` |
| `a => ~b` | `f : isContr(A) -> B` |
| `~a ⋀ (a => ~b)` | `(x, f) : (A, isContr(A) -> B)` |
| `~a => a` | `f : A -> isContr(A)` |
| `~a => b` | `f : A -> isContr(B)` |
| `~a => ~b` | `f : A -> B` |
| `a ~> b` | `f : (isContr(A) -> isContr(B), A -> B)` |
| `a == a` | `refl{A} : Id(A, A)` |
| `a == b` | `p : Id(A, B)` |
| `a ~~ b` | `q : (Id(A, B), A, B)` |
| `~a == ~b` | `f : A <-> B` |
| `hom_eq(2, a, b)` | `f : (Id(A, B), A <-> B)` |
| `a ⋀ b` | `(x, y) : (isContr(A), isContr(B))` |
| `~a ⋀ ~b` | `(x, y) : (A, B)` |
| `a ⋀ ~a` | `(x, y) : (isContr(A), A)` |
| `~a ⋀ ~~a` | `(B, x) : (A, B)` |
| `a ⋁ b` | `x : isContr(A \| B)` |
| `~a ⋁ ~b` | `x : A \| B` |
| `false` | `x : ⊥` |
| `true` | `x : ⊤` |
| `¬~a` | `x : A -> ⊥` |
| `~¬a` | `x : A -> ⊥` |

#### Homotopy Level 0

In PSQ `~~a` is to `~a` what `~a` is to `a`.
However, there is no way to go from `a` to something else.
The idea that there is no way to go from `a` to something else,
makes it natural to use `a` as Homotopy Level 0, or `isContr(A)` in HoTT.

#### Continuous Maps

In PSQ a continuous map is written `a ~> b`, which connects a space `a` to a space `b`.
By Cont-Definition, `a ~> b` is equal to `(a => b) ⋀ (~a => ~b)`.
In HoTT `a ~> b` is a type `(isContr(A) -> isContr(B), A -> B)`.

In PSQ `a => b` projects arbitrary small loops in a space `A` to arbitrary small loops in space `B`.
In HoTT this is the type `isContr(A) -> isContr(B)`.

In PSQ `~a => ~b` projects points in space `A` to points in space `B`.
In HoTT this is the type `A -> B`.

#### Propositional Equality, Id and the Pointcaré conjecture

In PSQ, `(a => b) ⋀ (b => a)` is equal to `a == b`.
In HoTT this means that `(isContr(A) -> isContr(B), isContr(B) -> isContr(A))` equals `Id(A, B)`.
When arbitrary small loops in space `A` are projected to `B` and vice versa,
it follows that `A` and `B` are topologically equivalent up to homotopy.

Another way to think about this is by using the [Pointcaré conjecture](https://en.wikipedia.org/wiki/Poincar%C3%A9_conjecture).
Wherever in `A` is locally contractible, then `A` has the same local topology as a hypersphere.
Wherever in `B` is locally contractible, then `B` has the same local topology as a hypersphere.
When `A`'s contractibility is equal to `B`'s contractibility, they both have same topology by some shape.
This shape can be constructed by hyperspheres, using a glue operation.

#### Higher Homotopy Levels and Type Universe Polymorphism

In PSQ, `~~a` is tricky to imagine as a type in HoTT.
However, one can use `~a ⋀ ~~a` translated as `(B, x) : (A, B)` to help the intuition.
To make `B : A` and `x : B`, it requires `A` to have a higher type universe than `Type(0)`.
This means `~~a` naturally describes `A` as `Type(1)` or higher.
Since any two proofs of `Type(0)` are propositionally equal (Homotopy Level 1),
it means that `Type(1)` has the structure of sets (Homotopy Level 2).

Similarly, `~~~a` naturally describes `A` as `Type(2)` or higher.

Since PSQ treats type universes this way, it corresponds naturally to type universe polymorphism in HoTT.

To turn on type universe polymorphism in Coq, use the flag `Set Universe Polymorphism.`.

### PSQ is an Outside Theory of Mathematics

It is impossible to build a complete model of `~` with within PSQ.
However, it is possible to build a model up to some homotopy level.

This means, that PSQ is Outside theory of mathematics, in the sense of [Avatar Schema Theory](https://advancedresearch.github.io/avatar-extensions/summary.html#avatar-schema-theory).
The reason is that PSQ contains a symbol, which is `~`, that does not refer to the theory of PSQ.

### Translation into Hegel's Philosophy

Hegel's philosophy is centered on interpretation of history and existence through time.
In Path Semantics, there are two kinds of "moments" in the sense of Hegel:

1. Moments distinguished by repeated application of self-quality/qubit `a, ~a, ~~a, ...`
2. Moments distinguished by path semantical layers using the core axiom

Physically, the first kind might be thought of as unstructured relativistic time (clocks in local space-time),
since `~a` comes after `a` but it is unknown whether `~a` comes after `~b`.
The second kind might be thought of as Newtonian time (universal clock),
where order in time is determined by path semantical layer.

Unstructured relativistic time happens prior to the observer, where order of events can be undefined.
It is the observer that relates events by order,
such that from the perspective of a single observer,
the universe appears to have a universal clock (the time in local space-time projected onto the universe).

Hegel did not distinguish the two kinds of time physically,
because at his time the only notion was in terms of Newtonian time (universal clock).
Relativistic time appeared later through the work of Einstein.

This means, when reading Hegel's "Science of Logic",
one should be aware that he expresses his ideas ambiguously in relation to modern physics,
viewed through the lens of Path Semantics.
The easiest way to solve this ambiguity is to use the first kind by default
and the second kind by mentioning it explicitly.

#### Self-Quality

Hegel's notion of self-quality can be translated directly to self-quality/qubit in Path Semantics:

```text
~a    self-quality of `a`
```

#### Ground

Hegel's notion of ground is how the appearance of an object is related to previous moments by thought or by itself.

```text
`a` is the ground of `~a`
```

#### Being

Hegel's notion of Being is a constructive proposition.

```text
a    `a` is Being of `a`
```

Being-In-Itself and Being-For-Itself are movements of Being into self-quality
through two different ways.

```text
a ~~ a                  Being-In-Itself as movement through direct self-quality
(a ~~ b) => (a ~~ a)    Being-For-Itself as movement to self-quality through an Other
```

In [Avatar Witness Theory](https://advancedresearch.github.io/avatar-extensions/summary.html#avatar-witness-theory),
it is common to call Being-In-Itself for "Loop Witness" and Being-For-Itself for "Product Witness".

#### Essence and Shine

Hegel's notion of essence is a potential in relation to Being.
Essence can be though of as a type where the type operator is shine.

```text
a : T    `T` is the essence of Being `a` and `:` here is the shine
```

Notice that Being `a` here is dialectically biased toward a proof of Being `a : ...`.
Therefore, essence implies bias toward "proof sense" which for Hegel is shine.
The unbiased Being is `a` as constructive proposition `a`.

In Path Semantics, this is equal to:

```text
(a => T) ⋀ (a < T)
```

Where `<` is order of path semantical layer.
Therefore, essence and shine is in relation to the observer.

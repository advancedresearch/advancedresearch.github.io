# Improving Brute Force Theorem Proving
by Sven Nilsen, 2020

In this blog post I explain the recent breakthrough in Path Semantical Logic.

### Background

[Logic](https://en.wikipedia.org/wiki/Logic) has been studied for millenia,
but is still an extremely active field of research.
It is an important tool in mathematics, philosophy and science.

The dominant logic used in mathematics is [First-Order Logic](https://en.wikipedia.org/wiki/First-order_logic).
At the core of First-Order Logic, and many other logical languages,
there is [Propositional Calculus](https://en.wikipedia.org/wiki/Propositional_calculus).

### Time Complexity

A proof in Propositional Calculus of `N` arguments has worst-case time complexity `O(2^N)`.
For First-Order Logic, the worst-case time complexity is even worse.
This means it is impractical to use brute force for automatic theorem proving.

To overcome the limitation of computational complexity in practical use, logicians developed formal systems with inference rules.
One such system is [Natural Deduction](https://en.wikipedia.org/wiki/Natural_deduction).
Another system is [Sequent Calculus](https://en.wikipedia.org/wiki/Sequent_calculus).

### Tautologies

An inference rule is valid to use when it is a tautology.
A tautology means the expression is `true` for all possible inputs.
Tautologies are used to bootstrap from a brute force theorem prover to a practical logical formal language.

With other words, tautologies are zero-cost in memory complexity of storing inference rules.
Once you have a brute force theorem prover of a theory, one can derive all inference rules to construct a practical theorem prover.

### Modern Mathematics

The problem of time complexity is not the only problem in modern mathematics.

In modern mathematics, most applications of theorem proving involve some sort of type hierarchy.
This is because one would like to prove properties of computer programs.

[Type Theory](https://en.wikipedia.org/wiki/Type_theory) is the foundation of many general purpose programming languages.
It is also the foundation for formal checking of theorems in pure mathematics, e.g. [Homotopy Type Theory](https://en.wikipedia.org/wiki/Homotopy_type_theory).

However, Propositional Calculus is too unrestricted to model Type Theory very well.

### Dependent Types

The proof assistants that are capable of checking proofs of modern mathematics, relies on [Dependent Types](https://en.wikipedia.org/wiki/Dependent_type).

### Path Semantics

[Path Semantics](https://github.com/advancedresearch/path_semantics) is a research project that uses re-interpretation of functions for expressing mathematics.

Path Semantics is more expressive than dependent types.
The problem with Path Semantics is that it is so expressive that it gets very hard to develop formal languages.

### Core Axiom of Path Semantics

At the core of Path Semantics there is a single axiom.
This axiom is not encoded in a formal language, but can be interpreted in e.g. First-Order Logic.

The core axiom received a lot of unconstructive criticism, because it is so *different* from normal logic.
Some people believed it was nonsense, or "not even wrong" as they put it.

Through discussions with Adam Nemecek, I have come to some sort of understanding of why.

In many situations that arise from constructions of "optimal solutions" in mathematics,
[Adjoint Functors](https://en.wikipedia.org/wiki/Adjoint_functors) seem to pop up all over the place.

Path Semantics is kind of an adjoint to Logic.
This is why Path Semantics seem so *different* from normal logic.
When implementing Path Semantical Logic in [Pocket-Prover](https://github.com/advancedresearch/pocket_prover),
I could see typical patterns, such as diagonal tracing, that occurs often in mathematics of adjoints.

One day I would like to understand this better.

### Path Semantical Logic

By applying the core axiom of Path Semantics to Propositional Calculus,
it is possible to introduce relations that resemble a type hierarchy.

Instead of treating all propositions as equal, they are grouped into levels.

For example, to express `one : nat` and `two : nat`, one writes:

```text
(one, two) (nat):
and(
  imply(one, nat),
  imply(two, nat)
)
```

- The proposition `one` has level 1
- The proposition `two` has level 1
- The proposition `nat` has level 0

In normal Propositional Calculus, the same would be expressed as:

```text
(one, two, nat):
and(
  imply(one, nat),
  imply(two, nat)
)
```

These two expressions means exactly the same.
However, by introducing a new variable `x` of type `list`:

```text
(one, two, x) (nat, list):
and!(
  imply(one, nat),
  imply(two, nat),
  imply(x, list)
)
```

In normal Propositional Calculus, the same would be expressed as:

```text
(one, two, x, nat, list):
and!(
  imply(one, nat),
  imply(two, nat),
  imply(x, list),
  imply(and!(imply(one, nat), imply(x, list), eq(one, x)), eq(nat, list)),
  imply(and!(imply(two, nat), imply(x, list), eq(two, x)), eq(nat, list)),
  imply(and!(imply(one, list), imply(two, nat), eq(one, two)), eq(nat, list))
)
```

It could be worse, since the core axiom contains a lot of symmetry,
but the point is that the more arguments are added, the more axioms are required to model a type hierarchy.

### Performance

In addition to reducing the number of axioms, Path Semantical Logic improves performance of brute force proofs significantly.

For example:

- `(one, two, x) (nat, list):` requires checking 24 cases
- `(one, two, x, nat, list):` requires checking 32 cases

This does not sound like much, but for larger number of arguments there is an exponential difference.

The worst-case time complexity of Path Semantical Logic is approximately the sum of exponential time complexity in each group.

Or, more precisely:

```text
O(|F|, |X|) = 2^(1+|F|) + (1 + |F|) · (2^|X| – 2)
```

This is a signficiant speed up from Propositional Calculus.

A thumb rule: If one can brute force check each group in Propositional Calculus within reasonable time,
then one can brute force check both groups within reasonable time.

### Conclusion

[Path Semantical Logic](https://github.com/advancedresearch/path_semantics/blob/master/sequences.md#path-semantical-logic) contributes to the field of logic in the following ways:

- Speed up of brute force checking
- Reduction in axioms to model a type hierarchy

In addition to making brute force theorem proving more practical,
this also makes it easier to extract tautologies for logical systems.

Q.E.D.

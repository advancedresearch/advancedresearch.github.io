# Language Bias

Every language has language bias.

A language bias is something that is a property of a particular language being used,
not because of an external reality.

Language bias is an important research topic, for the following reasons:

1. Language bias results in limited applicability of language tools
2. Human brains learn to organize information using language biases

### Negation

In classical logic, one can think about individual states as `0` and `1`.
The negation of `0` is `1` and vice versa.
If we have an unknown `a`, then the negation of `a` is `!a`.
This means, if `a = 0`, then `!a = 1` and vice versa.

In constructive logic, negation of `a` is `a => false`.
Here, `false` is an empty type: A type without any members.
Constructive logic breaks the symmetry of classical logic between `0` and `1`.

Negation is a language bias because depending on whether we use classical or constructive logic,
what negation means is a property of the language and not because of an external reality.
While Negation might seem like a very fundamental idea, it is simply a language mechanism.

Philosophers can have different ideas about Negation depending on their personal preferences.

### Space and Time

In Newtonian physics, time is uniform for all observers.
This means, a unit of time is the same in every reference frame.
No matter how fast an observer moves, or accelerates, a unit of time is fixed.

In Relativity, time is non-uniform for all observers.
A unit of time of an observer A might need a transform to predict the same unit of time for an observer B.

From Relativity, we get the philosophy of Relativistic Monism.
Relativistic Monism tells us that space is an imaginary direction where we pretend light can move at infinite speed.
Likewise, time is an imaginary direction where matter is at rest.

Therefore, according to Relativistic Monism, Space and Time are language biases.
While Space and Time might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about Space and Time depending on their personal preferences.

### Static and Dynamic

In physics, what is perceived as static is a matter of perspective,
where the observer is at rest relative to the reference frame of the phenomena being observed.

Dynamic is when an observer moves relative to reference frame of the phenomena being observed.

Therefore, Static and Dynamic are language biases.
While Static and Dynamic might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about Static and Dynamic depending on their personal preferences.

### Identity

A common notion of identity in mathematics is by using equality.

In constructive logic, `a == b` means that in some context, one can prove `a => b` and `b => a`.
This context is unknown: It can be empty or assuming some theory.
With other words, `a == b` can be true depending on context.

In meta-logic, we can write `a == b` being true in the context `c` as `(a == b)^c`.
Another way is to write is `c -> (a == b)`.
Notice that here, we use `->` and not `=>`.
The `->` symbol means a function pointer and the `=>` symbol means a lambda or closure.

When `(a == b)^true` (tautological equivalence), this is logically equivalent to `a =^= b` (power equivalence).
Power equivalence `a =^= b` means that in some context, one can prove `a -> b` and `b -> a`.
The precise meaning is that `a -> b` and `b -> a` are provable,
but since they are function pointers it is impossible to construct such examples depending on context.
Yet, in meta-logic we might use function pointers as assumptions and do axiomatic transformations.
This means, in meta-logic, function pointers might depend on the context.

The correct framework for meta-logic in constructive logic is the HOOO EP axioms.

Traditionally, mathematicians have used Provability Logic, which is a Modal Logic we can model in HOOO EP.
Provability Logic has a different notion of provability than HOOO EP.

Gödel's work on the incompleteness theorems is based on the notion of Provability Logic.
When using HOOO EP instead, it is not possible to construct Gödel's proof.
Hence, since the proof is not constructible, one can not draw the same conclusions using the correct notion of provability.

Therefore, Identity is a language bias.
While Identity might seem like a very fundamental idea, it is simply a language mechanism.

Philosophers can have different ideas about Identity depending on their personal preferences.

### Induction and Coinduction

Induction is a theorem proving technique that allows one to reason about properties of infinite structures.

Basically, Induction says that if we can produce a certain proof that some property holds assuming a special cover of an infinite set,
then we can lift this special cover together with a base case such that the property holds in every case.

The most common way to learn about Induction is by studying the Peano axioms of natural numbers.
A natural number is `0, 1, 2, 3, ...`, but not including infinity.

Induction for natural numbers works this way:

If `f(0)` holds and `f(x) => f(x + 1)` for all `x`, then by Induction: `f(x)` holds for all `x`.

To reason about natural numbers this way, one of the Peano axioms is Induction.
With other words, Induction is introduced as an axiom and not part of the natural properties of constructive logic.
This axiom assumes that predicates are normal congruent.
A congruent predicate `f` means that for all `a, b`, `(a == b) -> (f(a) == f(b))`.

To make Peano axioms work properly in a setting where normal congruence is not assumed,
one has to add an assumption for Induction that the predicate is normal congruent.

Coinduction is a theorem proving technique where assuming that some property `f` does not hold leads to a contradiction
assuming a special cover of an infinite set, then we can lift this special cover together with a base case such that the property holds in every case.

The analogy of Coinduction in classical logic is that `!!a == a`.

A proof system might be Inductive or Coinductive.

Therefore, Induction and Coinduction are language biases.
While Induction and Coinduction might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about Induction and Coinduction depending on their personal preferences.

### Types and Booleans

In programming a type `A` is a data structure with a grammar to construct valid data satisfying the type.

For example, the type `bool` has two members: `false` and `true`.

In Type Theory, booleans can be:

1. Normal programming, where one computes with `bool` or bits
2. A theory using excluded middle for all members of `type(0)`
3. An axiomatic theory used to model booleans

Normally, we refer to `bool` as in normal programming, or when computing with bits `0` and `1`.

In constructive logic, `false` and `true` are types.
A boolean in constructive logic can be modeled using `false : type(0)` and `true : type(0)` and `type(0) -> a | !a` for all `a`.
Another way to model booleans is to use symbols and axioms at type level `false' : bool'` and `true' : bool'` and `(x : bool') -> (x == false') | (x == true')`.
The axiomatic theory uses a `:` operator at type level.
This can be confusing when people write `false : bool`, because it might be interpreted in different ways.

Therefore, Types and Booleans are language biases.
While Types and Booleans might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about Types and Booleans depending on their personal preferences.

### Homotopy Type Theory and Path Semantics

Homotopy Type Theory (HoTT) can be thought of as a perspective of mathematics which is biased toward synthetic topology.

HoTT is a subset of Type Theory, which sits as a language stronger than Type Theory but weaker than Logic.

What makes HoTT useful as a perspective of mathematics, is the ability to classify mathematical languages by homotopy levels:

- Proofs and truth is a subset of HoTT of homotopy level 0
- Logic, whether it is constructive or classical, is a subset of HoTT of homotopy level 1
- Set Theory is a subset of HoTT of homotopy level 2
- Groupoids, which models symmetries, are at homotopy level 3
- 2-Groupoids are at homotopy level 4
- ...
- N-Groupoids are at homotopy level N + 2
- Infinity-Groupoids is when we take the limit of homotopy levels toward infinity

Path Semantics at fundamental level is usually considered the study of the core axiom of Path Semantics.
From this core axiom, one can design the path semantical qubit operator `~` for Logic.

By adding the qubit operator `~` to Logic, one gets higher homotopy levels by how many times `~` is applied recursively.

For example, `~a` is a proposition in homotopy level 1.
`~~a` is a proposition in homotopy level 2.

In Path Semantics, path semantical quality is defined as:

`(a ~~ b) := (a == b) & ~a & ~b`

Quality `a ~~ b` might be thought of as a path with trivial homotopies in HoTT.

The homotopy levels in Path Semantics are a subset of HoTT.
This is because when we use a path `a ~~ b`, all such paths are propositional.
It means, if `p : (a ~~ b)` and `q : (a ~~ b)`, then `p == q`.

HoTT can be understood as a weaker theory than Path Semantics.
With other words, synthetic topology is an interpretation of Types biased toward Spaces.
In turn, Path Semantics is an interpretation of Spaces toward Logic.

Path Semantics can model HoTT as a logical theory.
This means, you can go from HoTT to Path Semantics and from Path Semantics to HoTT.
It works because the `:` operator can be used at type level as an axiomatic theory.

Therefore, HoTT and Path Semantics are language biases.
While HoTT and Path Semantics might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about HoTT and Path Semantics depending on their personal preferences.

### Inside and Outside theory

An Inside theory is defined by the property that an unknown `x` is a sentence in some grammar.

For example, when we solve equations in math, we solve for `x` by finding the sentence that expresses its value:

`x = y + 1`

The unknown `x` is a sentence in the grammar `<expression> + <literal>`.

An Outside theory is defined by the property that it contains at least one symbol that is intrinsically uknown.

For example, a function `mouse_cursor_pos()` that returns the mouse cursor position in a game engine.

The value of `mouse_cursor_pos()` is intrinsically unknown in the sense that it means what the user controls.

If we think about `mouse_cursor_pos()` as an unknown 2D vector, then we use Inside theory.
Inside theory ignores the semantical content of the data, the fact that `mouse_cursor_pos()` means the position of some mouse cursor.

Therefore, Inside and Outside theory are language biases.
While Inside and Outside theory might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about Inside and Outside theory depending on their personal preferences.

### Platonism and Seshatism

When language biases are studied, it is easier to classify them generally using two fundamental language biases:

- Platonism credits knowledge by abstraction
- Seshatism credits knowledge by causality

For example, classical logic is Seshatic biased because it is easier to use than constructive logic when building computers.
Constructive logic is Platonic biased because it is in a sense representing "true" ideas as constructible structures,
while "false" ideas are impossible to construct.

Other examples:

- `0` (Platonic) and `1` (Seshatic)
- Space (Platonic) and Time (Seshatic)
- Static (Platonic) and Dynamic (Seshatic)
- Induction (Platonic) and Coinduction (Seshatic)
- Types (Platonic) and Booleans (Seshatic)
- Homotopy Type Theory (Platonic) and Path Semantics (Seshatic)
- Inside theory (Platonic) and Outside theory (Seshatic)

It is often possible to tell whether one bias is more Seshatic or Platonic than another.
Sometimes, one bias can be more Platonic in one sense and more Seshatic in another sense.

For example, Induction might be seen as both Platonic and Seshatic, depending on perspective.
Induction is Platonic because it has less Negation: In Path Semantics, `~a` is Platonic biased and `!~a` is Seshatic biased.
However, when thinking about using Induction in theorem proving,
this process is closer casually linked to construction, hence more Seshatic.

When we view causality in general compared to abstraction,
we think of causality as more Seshatic.
However, when we view forward in time compared to backward in time,
we view forward in time as more Platonic and backward in time as more Seshatic.

This symmetry can also be used in Path Semantics, where theorems using path semantical quality
can be turned into path semantical aquality by replacing `~a` with `!~a` and vice versa:

`(a ~!~ b) := (a == b) & !~a & !~b`

In philosophy the difference between `~~` and `~!~` is called an "internal difference".
This is a difference that might be impossible to distinguish for those who do not speak a certain language.

For example, a sequence of random bits looks the same whether you invert every bit or not.
The sender of a such sequence knows whether the bits are inverted,
but the receiver can not tell the difference.

To construct higher dualities based on Seshatism vs Platonism, we use Joker Calculus.

Therefore, Platonism and Seshatism theory are language biases.
While Platonism and Seshatism theory might seem like very fundamental ideas, they are simply language mechanisms.

Philosophers can have different ideas about Platonism and Seshatism theory depending on their personal preferences.

# Plato's Cave Found in Mathematics
by Tupshin Harper, Adam Nemecek, Sven Nilsen, 2021

In this blog post, we will summarize a result of discussions in [Philosophy of Mathematics](https://en.wikipedia.org/wiki/Philosophy_of_mathematics) the past few months. The discussions took place on our [Discord server](https://discord.gg/JkrhJJRBR2).

The basic result is that mathematics contains a fundamental illusion, like shadows on the walls of Plato's cave.
This illusion exists at the deepest level of mathematics and can not be avoided.
This has many implications in philosophy, for example in the philosophy of the mind.

### Introduction to Plato's Cave

From the [article on Wikipedia](https://en.wikipedia.org/wiki/Allegory_of_the_cave):

> In the allegory, Socrates describes a group of people who have lived chained to the wall of a cave all their lives, facing a blank wall. The people watch shadows projected on the wall from objects passing in front of a fire behind them and give names to these shadows. The shadows are the prisoners' reality but are not accurate representations of the real world. Three higher levels exist: the natural sciences; mathematics, geometry, and deductive logic; and the theory of forms.
>
> Socrates explains how the philosopher is like a prisoner who is freed from the cave and comes to understand that the shadows on the wall are not reality at all. A philosopher aims to understand and perceive the higher levels of reality. However, the other inmates of the cave do not even desire to leave their prison, for they know no better life.

In the context of this blog post, the Plato's Cave will be used about one of the higher levels of reality explained by Socrates: Mathematics.
With other words, mathematics as we know it is also an illusion, a mere shadow of higher levels of mathematics.

### Inside vs Outside Theories of Mathematics

#### Definition of The Inside

An Inside Theory is a mathematical language which models external objects as unknowns.

#### Definition of The Outside

An Outside Theory is a mathematical language with at least one symbol which does not refer to its theory.

#### Properties of Inside Theories

An Inside Theory is like a puzzle game where you have all the pieces.
The only work that remains is to figure out how to put the pieces together.

#### Properties of Outside Theories

An Outside Theory is like a puzzle game where new pieces can be created.
Not only figure out how to put the pieces together,
but also what kind of puzzle game one would like to play
given the partial solution found so far.

### Position

The philosophical position argued for is that Outside Theories are the "true" theories of mathematics,
while Inside Theories are projections, or illusions, hence the allegory of Plato's cave.

### Argument

Imagine a puzzle game which can be solved upside down.
Swapping the image on the front does not change the puzzle.

A such image that can be swapped, exists in the core axiom of [Path Semantics](https://github.com/advancedresearch/path_semantics).
The order assumption (`F > X`) is introduced to eliminate a particular form of inconsistency.

[Avatar Extensions](https://advancedresearch.github.io/avatar-extensions/summary.html) implies that the order can be weakened in the language of graphs,
by constructing using [Möbius](https://en.wikipedia.org/wiki/M%C3%B6bius_strip) topologies and remove diagonals using highest N-avatars.

These two operations are derived from:

1. A naive model in Avatar Logic of the core axiom without the order assumption,
which produces the smallest graph with Möbius topology for two orthogonal faces.
2. The fact that hypercubes are filled avatar graphs, which diagonals aligns with the edges between cores and the corresponding unique N-avatars.

With other words, the core axiom and Avatar Extensions are the only ingredients needed to construct hypercubes, which represents higher dimensions.
The reason this method is new, is that the order assumption can be removed temporarily from the core axiom,
since a localised form of order can be reintroduced later by "cleaning up" the graphs.

Filled avatar graphs are kind of like prime numbers, by the property that the group product of two avatar graphs has groupoid self-similarity.
Every hypercube is a filled avatar graphs, but there exists other filled avatar graphs with deep mathematical properties.
Groupoid self-similarity means that a complex graph can be "factorised" into clusters of nodes, kind of like a number can be factorised into primes.
When clusters have same internal structure as a filled avatar graph, its homotopy limit (contracted to a point),
gives the same global structure as an avatar graph (filled or not).

This points toward the possibility that weaker notions of order is accessible in higher [homotopy levels](https://ncatlab.org/nlab/show/homotopy+level).
There might be a trade-off between the homotopy level complexity of the mathematical language used,
and the weakest possible notion of order.

Today, we understand the mathematics we know as a projection of a higher dimensional mathematics.
This projection is like a shadow, or illusion of knowing what mathematics is.
The illusion happens because the order introduced in low dimensions,
is much stronger than the weakest possible order in higher dimensions,
so higher dimensional mathematics includes all the mathematics of lower dimensions.

When the assumption of order is swapped uniformly from low dimension to a higher dimension,
it is undetectable from within the mathematical theory.
This means that there exists some property that can not be modelled within mathematics,
without also embedding the entire mathematics into itself.

Explained in other words, the image on the front of the puzzle game can be swapped,
creating a different coherent picture, while the pieces of the puzzle can be put together without knowing the image.

Now comes a part that is special for mathematics, which has no analogue in puzzle games.
To learn about the image on the front, the entire puzzle game needs to be simulated inside the puzzle game.
However, since one can not learn about the image on the front from the pieces being upside down,
one has to guess among all possible images that can be on the front!

Avatar Extensions implies that there are many, many different ways higher dimensional mathematics can project onto low dimensional mathematics.
A similar argument exists in higher Category Theory, where categories can be combined to form more complex categories.
However, the important role of Möbius topologies, or weaker notions of particular forms of consistency in mathematical languages,
is a new idea that is might help to unify, or find principles underlying the Philosophy of Mathematics.

Out research group studies many mathematical languages where notions of consistency are weakened.
Many of these languages have practical value, such as:

- [AI Behavior Trees with Parallel Semantics](https://github.com/pistondevelopers/ai_behavior)
- [Formal Logic satisfying Avatars](https://github.com/advancedresearch/avalog)
- [Point-Free Theorem Proving using Normal Paths](https://github.com/advancedresearch/poi)

These languages go beyond the normal semantics of mathematical languages and are notoriously hard to understand from a formal perspective.
One question we ask ourselves, is what makes the normal semantics of mathematical languages unsuitable to deal with all mathematical languages of practical value?
By learning from many different mathematical languages, we have come to a simple assumption, yet often hidden, that causes this mistake:

A mathematical language that models external objects as unknowns, assumes that everything can be "understood"
as a construction within its own theoretical structure, meaning there is no "outside world".
We call such mathematical languages for Inside Theories.

Every Inside Theory is covered by the strictest form of order assumption in the core axiom of Path Semantics.
With other words, imposing a too strong constraint limits the universe of mathematical languages that are considered "mathematical".

However, by showing that this universe can be replaced by a greater universe with higher dimensions,
we hope to convince people to give up the idea that Inside Theories can model everything.

For example, languages which changes semantics by introducing new rules,
e.g. by self-modification, can satisfy some notions of consistency, even that notion of consistency is weaker than usual.

To define such languages, we say that the language has a least one symbol which does not refer to its theory.
This can mean the language is incomplete, or parts of the language is undefined.
We call such languages for Outside Theories.

Therefore, Outside Theories are the only "true" theory of mathematics.
An Inside Theory is merely an illusion.

### The Notion of Truth

Different mathematical languages have different notions of truth.
This means that we have to be careful by what we means about "true" in this context.

For example, languages that can be modelled using a [monotonic solver](https://github.com/advancedresearch/monotonic_solver),
have a different notion of truth from languages that can be modelled using a [linear solver](https://github.com/advancedresearch/linear_solver).
However, both monotonic and linear solvers are generic mathematical languages.

Our argument is about *any* mathematical language, which is separated into families of Inside and Outside Theories.

In particular, we wish to avoid the [No true Scotsman](https://en.wikipedia.org/wiki/No_true_Scotsman) fallacy.
Excluding Inside Theories, by definition only, is an appeal to purity and therefore not valid reasoning.

However, we use the idea that mathematics, in the broadest sense possible,
must satisfy a weaker criteria of consistency than for more narrow mathematical languages.
This broadest sense possible, that we know of, is using the core axiom of [Path Semantics](https://github.com/advancedresearch/path_semantics),
with arbitrary levels of weakened order.

### Who are affected by this illusion?

People who study mathematics, usually limit themselves to a particular area.
This is because acheiving mastery in all areas is practically impossible.
Mathematics has grown too big for a single person to know everything.

Any phenomena we know of, even in pure mathematics,
can be studied using modelling.
It means that for every field of mathematics,
some mathematical language is usually constructed to model the phenomena.

This illusion affects all people who model anything, whatever they are studying.
This is because the illusion is built-in to the very construction of mathematical languages.

Intuitively, most people understand that the model is not the same as reality.
However, we are not talking about reality here.
Our argument is based on mathematics, not meta-physics.

The key to understand this, is that the reason any model is an illusion,
can be made without any appeal to a higher reality, in the sense of non-mathematical reality.
Or, to put it this way: Even if mathematics *was* reality, Plato's cave would apply.

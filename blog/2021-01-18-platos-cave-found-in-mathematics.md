# Plato's Cave Found in Mathematics
by Sven Nilsen, 2021

In this blog post, I will summarize a result of discussions in [Philosophy of Mathematics](https://en.wikipedia.org/wiki/Philosophy_of_mathematics) the past few months (Tupshin Harper, Adam Nemecek and Sven Nilsen). The discussions took place on our [Discord server](https://discord.gg/JkrhJJRBR2).

The mathematics in this post is based on previous discussions on a Discord server for Applied Category Theory,
which was kicked off by ideas of [Kent Palmer](https://www.researchgate.net/profile/Kent_Palmer) (Ph.D. Systems Engineering; Ph.D. Sociology).
The broader theoretical framework was developed inspired by work of [Sylvester James Gates, Jr.](https://watson.brown.edu/people/faculty-fellows/gates) (Ph.D Theoretical Physics) and [Vladimir Voevodsky](https://en.wikipedia.org/wiki/Vladimir_Voevodsky) (Ph.D Mathematics).

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
2. The fact that hypercubes are filled avatar graphs, which diagonals align with the edges between cores and the corresponding unique N-avatars.

With other words, the core axiom and Avatar Extensions are the only ingredients needed to construct hypercubes, which represents higher dimensions.
The reason this method is new, is that the order assumption can be removed temporarily from the core axiom,
since a localised form of order can be reintroduced later by "cleaning up" the graphs.

Filled avatar graphs are kind of like prime numbers, by the property that the group product of two avatar graphs has groupoid self-similarity.
Every hypercube is a filled avatar graph, but there exists other filled avatar graphs with deep mathematical properties.
Groupoid self-similarity means that a complex graph can be "factorised" into clusters of nodes, kind of like a number can be factorised into primes.
When clusters have same internal structure as a filled avatar graph, its homotopy limit (contracted to a point),
gives the same global structure as an avatar graph (filled or not).

This points toward the possibility that weaker notions of order is accessible in higher [homotopy levels](https://ncatlab.org/nlab/show/homotopy+level).
There might be a trade-off between the homotopy level complexity of the mathematical language used,
and the weakest possible notion of order.

Hypercubes have already been used as theoretical basis for mathematical languages.
In 2016, [Cubical Type Theory](https://arxiv.org/abs/1611.02108) was released and many versions of this theory has since been developed.
Mathematicians know that moving into higher dimensions of type theory gives more powerful proof techniques,
where the use of hypercubes is considered a "nicely behaved" subset of a larger theoretical framework.

One argument against diving into higher dimensions of mathematics, is that such languages will be esoteric,
besides all the common properties that low dimensional mathematics have.
Against this position, we have come across two arguments:

1. Cubical Type Theory shows that proofs can become shorter and easier to read.
2. Avatar Logic is better at modelling some real-world relations without adding exceptions to inference rules.

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
A similar argument exists in higher [Category Theory](https://en.wikipedia.org/wiki/Category_theory), where categories can be combined to form more complex categories.
However, the important role of Möbius topologies, or weaker notions of particular forms of consistency in mathematical languages,
is a new idea that might help to unify, or find principles underlying Philosophy of Mathematics.

Out research group studies many mathematical languages where notions of consistency are weakened.
Many of these languages have practical value, such as:

- [AI Behavior Trees with Parallel Semantics](https://github.com/pistondevelopers/ai_behavior)
- [Formal Logic satisfying Avatars](https://github.com/advancedresearch/avalog)
- [Point-Free Theorem Proving using Normal Paths](https://github.com/advancedresearch/poi)

These languages go beyond the normal semantics of mathematical languages and are notoriously hard to understand from a formal perspective.

In discussions with Kent Palmer (Ph.D. Systems Engineering; Ph.D. Sociology), he said that
a lot of languages were developed during the 90's, which could not be formalised within current mathematical knowledge of formal languages.
Kent seeked to understand this phenomena through philosophy,
which he thought was able to argue for higher levels of mathematics, but somehow these levels never managed to materialise mathematically.

One question we ask ourselves, is what makes the normal semantics of mathematical languages unsuitable to deal with all mathematical languages of practical value?
By learning from many different mathematical languages, we have come to a simple assumption, yet often hidden, that causes this mistake:

A mathematical language that models external objects as unknowns, assumes that everything can be "understood"
as a construction within its own theoretical structure, meaning there is no "outside world".
We call such mathematical languages for Inside Theories.

Every Inside Theory is covered by the strictest form of order assumption in the core axiom of Path Semantics.
With other words, imposing a too strong constraint limits the universe of mathematical languages that are considered "mathematical".

However, by showing that this universe can be replaced by a greater universe with higher dimensions,
we hope to convince people to give up the idea that Inside Theories can model everything.
(Technically, we are not saying that there are other languages that can model everything.
We are just saying there are better mathematical languages for some domains, without emphasis on modelling.)

For example, languages which changes semantics by introducing new rules,
e.g. by self-modification, can satisfy some notions of consistency, even that notion of consistency is weaker than usual.

To define such languages, we say that the language has a least one symbol which does not refer to its theory.
This can mean the language is incomplete, or parts of the language is undefined.
We call such languages for Outside Theories.

When people use Inside Theories, they might get biased by how the language influences their thinking.
Just like the prisoners in Plato's cave, these languages become their reality,
but does not represent the real world.
In our case the "real world" is about mathematics, or what characterises a mathematical language in general.

On the other hand, when studying Avatar Extensions, it is clear that it is always possible to extend the theory in a way that has not been thought of before.
This does not mean that Avatar Extensions is less mathematical than low dimensional mathematics.
Quite the contrary: Higher dimensional mathematics is *more* mathematical than low dimensional mathematics.

Therefore, given the choice between Inside and Outside Theories,
we argue for the position that Outside Theories are the only "true" theory of mathematics.
An Inside Theory is merely an illusion.

### The Notion of Truth

Different mathematical languages have different notions of truth.
This means that we have to be careful by what we mean about "true" in this context.

For example, languages that can be modelled using a [monotonic solver](https://github.com/advancedresearch/monotonic_solver),
have a different notion of truth from languages that can be modelled using a [linear solver](https://github.com/advancedresearch/linear_solver).
However, both monotonic and linear solvers are generic mathematical languages.

Our argument is about *any* mathematical language, which is separated into families of Inside and Outside Theories.

In particular, we wish to avoid the [No true Scotsman](https://en.wikipedia.org/wiki/No_true_Scotsman) fallacy.
Excluding Inside Theories by definition only, is an appeal to purity and therefore not valid reasoning.

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

### A Brief History of This Development

In the past century, [First Order Logic](https://en.wikipedia.org/wiki/First-order_logic) has dominated foundations of pure mathematics,
but [Category Theory](https://en.wikipedia.org/wiki/Category_theory) has come to play a larger role in construction of mathematical languages.

In the beginning of this century, a collaboration between mathematicians resulted in [Homotopy Type Theory](https://homotopytypetheory.org/blog/).
This was based on [Dependent Types](https://en.wikipedia.org/wiki/Dependent_type), which are used in verification of computer programs and theorem proving assistants.

Extending Dependent Types, the theory of [Path Semantics](https://github.com/advancedresearch/path_semantics) has been developed.
In particular, if normal programming is 2D, then theorem proving with normal paths is 3D.

In late part of the year 2020, [Kent Palmer](https://www.researchgate.net/profile/Kent_Palmer) asked the question: What lies beyond 3D? What is the analogue of higher dimensions?

[Avatar Extensions](https://advancedresearch.github.io/avatar-extensions/summary.html) is part of the Path Semantics project,
but borrowing ideas from higher Category Theory to develop a theory about higher dimensional mathematics.
What makes Avatar Extensions special, is that a new formal logic, Avatar Logic, works by a different principle than First Order Logic.

### Tupshin Harper's Outside Argument

Tupshin Harper made an excellent argument why Inside Theories do not really makes sense, in a discussion with Sven Nilsen:

Sven imagined the universe's wavefunction as basis for the only perspective where an Inside Theory is philosophically sound,
because the solution of every unknown in the theory corresponds to some real object.
Since there exists at least one case where an Inside Theory makes sense, one can not dismiss Inside Theories as mere illusions.

However, Tupshin disagreed!

Tupshin argued for that Sven's position, where the universe's wavefunction is a basis,
assumes that one can construct a reality that way, that is complete.

The key insight is that we do not know what it means for reality to be complete in the context of a mathematical theory.

So, Sven came up with another example, seen from the perspective of a subjective theory with a distinction:

1. The symbol "dog" seems to mean something external, that can not be fully constructed in the mind.
2. The symbol "1" seems to be fully constructed in the mind.

However, Tupshin Harper disagreed, once again!

Tupshin argued for that we do not understand "1" any more than "dog".
He meant the distinction between the two is an illusion.

So, Sven argued, using path sub-types:

1. `dog : [f] x`
2. `1 : [f] x`

Even if the machine `[f] x` is known, you do not get all properties of `dog`.
(In logic, [Leibniz' law](https://en.wikipedia.org/wiki/Identity_of_indiscernibles) is an axiom for the opposite,
but this is dismissed here because when you describe a dog fully, you are not constructing the external real dog itself.)

Tupshin then used the brilliant tactic:

1. To get an entire dog is to get the entire universe.
2. To get 1 is to get the entire universe.

Since the only philosophical sound perspective for an Inside Theory is having the entire universe as basis.
This means, the meaning of the two objects are of the same nature, just looking different from a subjective perspective.

Sven argued that one could create an illusion of the universe of 1 which was smaller than the entire universe, which Tupshin agreed to.

Therefore, Tupshin Harper argued successfully that the distinction between "dog" and "1" is an illusion in the sense of Inside Theories.

Sven realised that this argument could be used recursively,
meaning that even one took the whole universe as an Inside Theory,
the universe itself would be an illusion mathematically, compared to a greater Outside Theory.

This means that even "dog" can be understood as a real object,
there are some properties of "dog", that nobody, even reality itself, has access to.

Therefore, no Inside Theory is philosophically sound, but merely illusions.

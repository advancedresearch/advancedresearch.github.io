# The Proof of `~true`
by Sven Nilsen, 2023

*In this blog post I present an important breakthrough in Path Semantics, the proof of `~true`.*

### Background

[Path Semantics](https://github.com/advancedresearch/path_semantics) is a project to re-interpret functions for expressing mathematical ideas.
The central idea in Path Semantics is something called a “normal path”:

```text
f[g] <=> h
```

Here, `f`, `g` and `h` are functions.

The left side `f[g]` is like an open box with a bottom `f` and walls `g`.
The solution `h` is the missing lid of the box.
In [Cubical Type Theory](https://ncatlab.org/nlab/show/cubical+type+theory), this is known as a Kan-filling operation.

The notation in Path Semantics focuses on a mathematical language that allows theorem proving in a point-free style.
It known that composition of normal paths do not fully satisfy the model of sets,
such that the breakdown of `f[g]` as a mathematical object requires an “imaginary inverse” `inv`:

```text
f[g] <=> g . f . inv(g)
```

The imaginary inverse is just like ordinary inverse, but it does not require a solution.
To model the imaginary inverse properly, there is an ongoing work in the [Prop](https://github.com/advancedresearch/prop) library (Propositional logic using types in Rust).
The Prop library is used for research in foundational Path Semantics.

In foundational Path Semantics, an idea has been suggested to use propositions for everything.
This is an unusual approach, since most of mathematics builds on [First Order Logic](https://en.wikipedia.org/wiki/First-order_logic).
By using propositions for everything, it means that mathematics is brought to a lower level language Zeroth Order Logic,
or [Intuitionistic Propositional Logic](https://en.wikipedia.org/wiki/Intuitionistic_logic).

This means that the functions `f, g, h` are actually propositions.
However, they are not propositions in the sense that they are `true` or `false`.
This is possible in constructive logic, where a proposition does not have to follow the rules of classical logic.
In classical logic, a proposition is either `true` or `false` and never “neither”, “both” or any other sense.
However, in Path Semantics, propositions are thought about in a very different way that allows them to be used to describe literally anything.

Similarly, `g . f` is a proposition and `inv(g)` is also a proposition.
Even a function type `A → B`, or a type judgement `x : T` are propositions.
Everything is modelled as propositions using very clever tricks in logic.
Now, there might be limitations to this approach, but so far it seems to works.

### Constructive Logic and Fundamental Physics

It is known that fundamental physics can be described using hypergraph rewriting systems.
One such ongoing project, is the [Wolfram Physics Project](https://wolframphysics.org/).
The project seeks to understand fundamental physics by constructing it from the smallest building blocks possible.

Hypergraph rewriting systems are mathematical equivalent to constructive logic.
Therefore, constructive logic and fundamental physics are related research areas.

One open problem in Path Semantics is to determine whether its core axiom might be physically real or not.
It is currently believed that the core axiom might be related to time and possibly consciousness in Wolfram models.
The reason is that the core axiom allows “causal” moments in time represented as path semantical propositional levels.
The theorems that can be proved using the core axiom might give insights into how reality works at the smallest physical scales in space and time.

The core axiom of Path Semantics is meant to model how symbols work formally in logic.
As there is a well established link in philosophy between thinking, language and consciousness,
it might happen that there is something going on in the physical reality about something like “symbols”, but more fundamental.
Although the core axiom is meant to be used at high levels of abstraction,
it could also turn out to be relevant for studying fundamental physics itself.

However, it is very difficult to establish scientific experiments to test fundamental physics,
due to the small scales of space and time.
It is even more difficult to measure complex theoretical structures that might not be direct observables.
It has been a dream to find something that is simple enough to be tested, but also deep enough to imply something about hidden observables.

The proof of `~true` might be something like this, which hopefully might be tested scientifically.

### The `~` Operator

The path semantical qubit operator `~`, is a unary operator that takes any proposition as argument.
Unlike predicates in First Order Logic, which have normal congruence, the qubit operator `~` requires tautological congruence.
This means, in order to reason properly about substitution, a stronger meta-logic theory is required which is called “Higher Order Operator Overloading Exponential Propositions” (HOOO EP).
The logic that extends Intuitionistic Propositional Logic (IPL) with the qubit operator `~` is called “Path Semantical Quantum Propositional Logic” (PSQ).

The output of the qubit operator `~` might be interpreted as “any proposition”.
This means, the truth value of e.g. `~true` is unknown in PSQ alone.
However, when modelling normal paths in Prop, there is a trick that one can use to make theorem proving more convenient:

```text
inv(id) ~~ id
```

This means, instead of saying `inv(id) == id`, the inverse of `id` is said to be “qual” to `id`.
This operator `~~` is path semantical quality, which can be defined using the path semantical qubit `~`.
The side effect of this statement is that the imaginary inverse "collapses" to some solution, proved by `~inv(id)` or `~id`.
Using this approach, one can “compute backwards” using invertible functions that are defined in a normal way.
The idea of computing backwards is also relevant for fundamental physics.

The consequence of this design is that there exists a constructive proof of `~true`.

What is surprising, is that the proof depends on several important aspects of the theory:

- The identity function
- The imaginary inverse
- The qubit operator `~`
- The core axiom

Furthermore, the proof of `~true` provides an interpretation of homotopy level 0.
This interpretation talks about which propositions that inhabits various homotopy levels.
One can also use this interpretation to prove that `true` and `false` inhabit homotopy level 1 and that `id` inhabits homotopy level 2.
This is in correspondence with the predictions given by [Homotopy Type Theory](https://homotopytypetheory.org/).

### Speculations About Consequences for Fundamental Physics

From the perspective of Path Semantics, the proof of `~true` might be the most profound and beautiful theorem found so far.
At this point in time, it is not known what the full consequences of it will be. Only further research might tell.

However, I have started speculating about the consequences for fundamental physics.
For example, there might be some mechanism that aligns quantum states physically, that take on propositional values of truth.
The motivation for this is that `~true` might be thought of as something existing in a moment in time,
but is locally taking on some state of truth.
Since the constructive proof implies that the  proposition `~true` equals `true`,
it might be interpreted as some quantum state being physically connected to a “universal state” in space-time.
With other words, physical states of particular kinds might be aligned, just by having content of truth.

In General Relativity, space and time might be curved and connect distant regions of space,
called an Einstein-Rosen bridge, or more famously a [“wormhole”](https://en.wikipedia.org/wiki/Wormhole).
It is currently being speculated by theoretical physicists that wormholes are related to quantum entanglement.
The kind of entangelment concerning `~true` is not just about connecting two places in space-time,
but connecting places in space-time with some shared universal state, that might be accessed from anywhere in space-time.

If such universally shared entangled states exist physically,
then this might be a hint at some more complex mechanism that could give the fundamental physical structure
of space-time a kind of “language” which might resemble how we use symbols in mathematics.

For example, truth content of different places in space-time might be connected to universally
shared states by using some “region of physical provability” that involves physically reversible computation.
It is difficult to speculate about how this relates to observable phenomena,
but it might help to explain some of the apparent mysteries of quantum behaviour.

An obvious candidate of a such kind might be how observation affects the behaviour of quantum states.
As long the computational reversibility is preserved in a physical state,
the quantum superposition is preserved. However, when the physical computation becomes irreversible,
the quantum superposition collapses.
The collapse might be when the state of observers are aligned with universally shared states,
such that the “region of physical provability” has reached a certain size in space-time and causes something like
`~true == true` to happen for local states.
This means, one can think about quantum systems as structures in a complex logical language which has no ability
to yet infer a simple statement about itself. Time is required to evolve the state to some level where these simpler statements can be reached.
The universally shared states determine the “truth” of the observed physical states, which appear as moments in time for observers.

For millennia, philosophers have discussed mechanisms in logic that might explain how people have subjective and personal experiences.
It is apparently a similarity between various studies in Continental Philosophy and the research in foundational Path Semantics.
The missing link has always been how these ideas relate to physics.
Could there be a way to bridge this gap by uniting these ideas through constructive logic?
I invite anyone to join our project and help figuring this out!

[Join us at Discord!](https://discord.gg/JkrhJJRBR2)

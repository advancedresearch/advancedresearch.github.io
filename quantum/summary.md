# Quantum Path Semantics

Quantum Path Semantics is a sub-field of Path Semantics that studies how people use Quantum Mechanics (QM).

One frequent misconception about QM is that it can just be "explained away".
Even some serious philosophers of physics try very hard to unravel the "mystery" of QM,
and despite that these views gain lots of followers, there are often simple logical fallacies
at the core of their argument that hides the true nature of QM.

Language biases can be very powerful in human society.
When a person is committing to particular language biases and is not allowed to be criticized,
this can result in a cult-like behavior where that person gets a lot of social power.
The human brain has evolved to follow such leaders, which makes it more attractive
for some people to waste other people's time by leading them in the wrong direction.
They promise deeper insight into the nature of the reality,
but most of the time, they are just using some language tool which they think is the solution.

This is why science as an activity depends on observation.

While humans are beings that are depending on language tools for survival,
these language tools often bias our brains toward thinking we understand something when we do not,
victimizing ourselves when being criticized to gain sympathy, and attempting to grasp more power as a result of being "attacked".
Science is designed to overcome the human biases we have, over time, and arrive at facts about reality.

### The Path Semantical perspective of Quantum Mechanics

Path Semantics as a field is not concerned about Ontology, only about how people use symbols.
This means, we are not debating whether QM is "real" or not.

Arguments that one makes about QM from the perspective of Path Semantics,
is according to semantics, by how people use QM and whether people make errors in their usage of symbols.

### Building up the intuition about Quantum Mechanics

In Path Semantics, it is easier to see Quantum Mechanics as an Avatar Extension of existential paths.

An existential path `∃f` is a function that tells what the function `f` returns.

For example, the following function:

```text
f(x : nat) = x + 1
```

This function has type `nat -> nat`.

A natural number `nat` starts at 0 and contains all whole numbers up to, but not including, countable infinity.

Since there is no natural number before 0, the function `f` does not return `0` for any input.
However, it returns all other natural numbers.

From this information, one can define the existential path of `f`:

```text
(∃f)(y : nat) = y != 0
```

To avoid ambiguity, we often write `(∃f)(x)` instead of `∃f(x)`,
since the latter might be interpreted as `∃(f(x))`.

Normal existential paths, which are existential paths of deterministic functions,
returns a bool:

```text
f : T -> U
∃f : U -> bool
```

By extending normal existential paths to return probabilities,
we can describe what non-deterministic probabilistic functions outputs,
given that the input data is uniformly distributed:

```text
f : T -> U
∃_p f : U -> prob
prob <=> ℝ & (>= 0) & (<= 1)
```

Notice that we use an underscore `p`, `∃_p`, instead of `∃`.

For every normal existential path, we can construct a probabilistic existential path:

```text
normal_to_probabilistic(ex_f : U -> bool) = \(y : U) =
    if ex_f(y) { 1.0 } else { 0.0 }
```

For every probabilistic existential path `∃_p f` that satisfies Probability Theory,
we can construct a function `g` such that `∃_p g <=> ∃_p f`.
This does not imply that we can construct `f`.
There are many functions that can have the same probabilistic existential path.

A wave function in QM is a **quantum existential path**,
which extends probabilistic existential paths with complex numbers:

```text
f : T -> U
∃_c f : U -> ℂ
```

For every probabilistic existential path, we can construct a quantum existential path:

```text
probabilistic_to_quantum(ex_p_f : U -> prob) = \(y : U) =
    sqrt(ex_p_f(y)) + 0 * 𝐢
```

This means, we do not know always the identity of the function behind a wave function,
because wave functions are not actual functions, but quantum existential paths.

For every probabilistic existential paths, we can construct **some function**
with that same probabilistic existential paths.
So, in this case we can **make sense** of what any probabilistic existential path means.

However, for quantum existential paths, we can only construct a such non-deterministic function,
if we can use `probabilistic_to_quantum` and rotate the complex amplitudes uniformly:

```text
rotate_uniformly(x : ℂ) . probabilistic_to_quantum

probabilistic_to_quantum : (U -> prob) -> (U -> ℂ)
rotate_uniformly : ℂ -> (U -> ℂ) -> (U -> ℂ)
```

With other words, when the complex amplitudes of a wave function are not aligned,
there is **no way** to construct **any function** with that same quantum existential path.
There is simply **no way** to **make sense** of what any quantum existential path means.

### Interpretations of Quantum Mechanics

The physicists that developed QM understood that the theory they worked on, did not make any sense.
Still, they developed the theory, because this was part of the scientific process of predicting observations.

While the theory overall does not make sense, it is possible to factorize a wave function
into smaller local wave functions, that independently can be approximately thought of as non-deterministic probabilistic functions.

This means, we can use classical physics as an approximation to understand quantum physics.

All valid interpretations of QM requires a non-sensical theory overall, seen from the perspective of an observer,
but by factorizing quantum phenomena into basis states, one can use sensical theory as an approximation.

There are two major interpretations of QM in physics:

- The Copenhagen interpretation
- The Everett interpretation

The Copenhagen interpretation is simply the observation that the overall theory does not make sense.
However, since classical physics can be used to make approximately sense of basis states,
people who use the Copenhagen interpretation, speaks of system as if they are in superposition.

The Everett interpretation is simply by applying the theory itself to observers,
we will get many-worlds by the observer being in superposition.
This is why it is often called the "Many-worlds interpretation" in physics.

**Most importantly:** Neither of these two interpretations "solves" how the overall theory does not make any sense.

The Everett interpretation does not attempt to "explain" QM.
It merely states that, since quantum systems can be in superposition,
the observer can also be in superposition.
It is not a deep philosophical argument about the nature of QM.
On the contrary, it is a very straight forward argument, but with many philosophical implications in Ontology.

Over time, physicists have gradually favored the Everett interpetation over the Copenhagen interpretation,
simply because it avoids the need for explaining observers as special, compared to the rest of the quantum universe.

However, QM itself is still overall non-sensical.
Nobody have given a proper explanation of QM so far, that makes it sensical.

### Unsuccessful attempts

*Notice! These people might disagree, because they often claim to have "solved it".
However, it is our duty as Path Semanticists to inform people when they have not done what they claim.*

| Project                                 | Pioneer         | Successes                                    | Why it fails                                        |
| --------------------------------------- | --------------- | -------------------------------------------- | --------------------------------------------------- |
| Wolfram physics                         | Stephen Wolfram | SI units, Relativity, Constructive logic     | Can not derive the Born rule yet                    |
| Generalized Stochastic System Framework | Jacob Barandes  | Non-Markovian causality, Hilbert integration | Masks the Born rule in the Unistochastic assumption |

Stephen Wolfram worked on cellular automata to try understand physics from a different perspective than particle physics.
He succeeded with encouragement from two theoretical physicists, Jonathan Gorard and Max Piskunov,
to find a better language bias corresponding to natural physics by applying hypergraph rewriting.
This kicked off the Wolfram physics project, where hypergraph rewriting is explored as a fundamental theory of physics.

The weakness of hypergraph rewriting is that it does not explain observer bias.
When modeling observers implicitly as part of the model, given some model of the universe (which has not been found yet),
the theory predicts that observers will exist and what they measure.
The problem with this approach is that you have to search for observers in the model to make predictions.

While Wolfram's approach is beautiful and elegant, it is currently not sufficient to do science.

Jacob Barandes figured out a way to start with general probabilistic state transitions
and work his way backwards toward the normal Hilbert formulation of QM.
This shed some light on Markovian assumptions about causality made by other physicists,
but the end result is logically equivalent to the normal Hilber formation.
The assumption of Unistochasticity implies the Born rule and vice versa.

While Barandes' approach is useful and gives some new insights, it does not produce any new scientific predictions.

Neither does Berandes' approach "explain" QM any more than the Copenhagen interpretation, despite Barandes claiming otherwise.
Barandes is making a logical fallacy, where he thinks the language bias he chooses to focus on, "forces" the theory overall to make sense.
However, from the perspective of Path Semantics, there is still no "source code" you can use to make sense of any wave function in general.

### Potential future progress

Many smart people have tried to "explain" QM, but failed.
However, in the process, we learn new tricks from each attempt,
that can help overcome some issues.

Just because somebody proposes a theory which they make wrong claims about,
does not necessarily mean that all their ideas are bad.

We need at least some theory can has some form of observer bias built into it,
so the theory can be used as a pratical language tool in science.

One way to encode observer bias into hypergraph rewriting,
is to use [Avatar Extensions](../avatar-extensions/summary.html), e.g. [Avatar Hypergraph Rewriting](https://github.com/advancedresearch/avatar_hypergraph_rewriting).

The idea is simple: We live in a complex universe.

Since the universe is complex, there must be some observer bias that on average biases observers to exist in some complex universe.
Otherwise, it would be zero probability of complex observers existing, since it is easier statistically to produce simple universes.

In the foundation of Path Semantics, one can lift biconditions `a == b` into path semantical quality `a ~~ b`,
if one can prove that `a` is symbolic distinct from `b`, written `sd(a, b)`.
Path semantical quality is designed to fix the issues with using equality `==` in the core axiom.

From the experience on working in the foundation of Path Semantics and the time interpretation of path semantical levels,
we can predict that statistically, when path semantical quality propagates in time,
it will lead to an observer bias toward complexity.
However, this is just intuition at this point, because the proof is very hard.

By applying this intuition to hypergraph rewriting and using the theory of Avatar Extensions,
we can construct a language which has an observer bias toward complexity: Avatar Hypergraph Rewriting (AHR).

The way AHR functions currently, is by applying universal rules, just like Wolfram models.
This means you have to find observers encoded implicity within the model to make predictions about measurements.

AHR has an observer bias, but only for all possible observers in the universe given some model (which has not been found yet).

However, perhaps we can make AHR more scientific useful by assigning quantum states to avatars, using the form:

```text
|Ψ> = 𝛼 |indistinct> + 𝛽 |distinct>
```

The idea is instead of only biasing toward symbolic distinction,
we allow a mixed state where a rule matching against a state can produce a superposition.

One constraint on these quantum states of avatars, is that they are symmetric:

```text
a_𝛼 b_𝛽 + a_𝛽 b_𝛼 = 0

I = indistinct
D = distinct

|Ψ_a> = a_𝛼 |I> + a_𝛽 |D>
|Ψ_b> = b_𝛼 |I> + b_𝛽 |D>

|Ψ_ab> = |Ψ_a> ⊗ |Ψ_b> = a_𝛼 b_𝛼 |I> + a_𝛼 b_𝛽 |I> ⊗ |D> + a_𝛽 b_𝛼 |D> ⊗ |I> + a_𝛽 b_𝛽 |D> ⊗ |D>
```

This is because when `x` is symbolic indistinct from `y`, `y` is symbolic indistinct from `x`.
Likewise, when `x` symbolic distinct from `y`, `y` is symbolic distinct from `x`.

We assign a quantum state to each avatar, because a rule can contain arbitrary amount of avatars.
The interaction between avatars is used to determine how to generate the quantum state by applying some rule.
This quantum state only distinguishes between symbolic indistinction and symbolic distinction.

For example, if there is a rule with 3 avatars `a', b', c'`, the quantum state of the rule becomes:

```text
|Ψ_abc> = |Ψ_a> ⊗ |Ψ_b> ⊗ |Ψ_c>
```

For example, if `a_𝛼 = b_𝛼 = c_𝛼 = 1.0 + 0.0 * 𝐢`, then the rule is applied only when the nodes being matched against are identical.

On the other hand, if `a_𝛽 = b_𝛽 = c_𝛽 = 0.0 + 1.0 * 𝐢`, then the rule is applied only when the nodes being matched against are distinct.

The above examples assume that there is only one rule.

In general, you can have multiple rules and their contributions can cancel or amplify, depending on how the experiment is measured.
All complex amplitudes that result in the same final state are summed, squared and normalized to calculate the probability.

Now, this might seem a bit strange, because we are normally using wave functions to describe the physical state,
not the laws that operate on the state.

This is not a problem, because we can just assign a wave function to a physical state,
and use it with the quantum state of a rule to get the wave function of the output of the rule.

Instead of thinking of physical systems in terms of pure wave functions, or pure hypergraph rewriting,
we can mix them, such that there are both wave functions and **Quantum Avatar Hypergraph Rewriting** (QAHR).

Finally, we impose constraints, e.g. the Schrödinger equation, to get realistic physical behavior.

### Quantum Avatar Hypergraph Rewriting does not "explain" Quantum Mechanics

QAHR, with additional realistic constraints, allows a hypergraph to be in a superposition, just like a wave function,
being rewritten using multiple rules and calculate the probability of observing new hypergraphs in different states.

This framework does not "solve" QM by making it sensical.
We are not assuming that we have to "figure out" what QM actually means, somehow.
All we do is developing the language of QM to be more universal and precise.

Putting in more quantum states allows us to describe more complex scenarios,
where e.g. the quantum state of an avatar can depend on some other physical system.
We are not trying to model the entirety of reality precisely,
but instead allow physicists to put in more constraints where they want and study the behavior of the experiment.

This might allow us to model observer bias more accurately in physical experiments.
Previously, we usually assumed that the observer has no influence beyond simple math tricks, such as the Born rule.
The potential future progress is not to get rid of the Born rule,
but use it with hypergraphs in quantum states and rewritten by rules that have quantum states,
such that we can build on the Everett interpretation, applying the theory to observers.

Trying to "explain" QM by getting rid of the Born rule,
just makes the theory less practical for scientists to use.
You can develop a very beautiful theory, but it does not help anyone.
As long nobody can get the "source code" of quantum functions to make sense of them,
we should treat QM as "obviously non-sensical" but "locally approximately sensical in the bases".

Just claiming that the Everett interpretation "explains stuff", when it does not,
or claiming that one can get rid of the multi-verse, has (so far) not been based on rational and sound arguments.
This has only produced theories where people try to squeeze all the weird stuff into one corner.
The Copenhagen interpretation made an important realization, that this theory is just non-sensical overall.
Yet, the Everett interpretation made another important realization, that the theory should be applied to observers.
We are not moving away from QM, we are moving deeper into the theory.

When you put in real probabilities or discrete states, you are just making local approximations.
That's all.

You can't "solve" QM. You can only observe whether the theory you developed predicts real outcomes of experiments.

For example, if you simulate hypergraph rewriting, then the simulation is encoded in some wave function in reality.
There is always another meta-level where what you treated as a classical physical system, ends up back in QM.

At some point, sooner or later, you have to stop and make approximations.
Or else, you can not make any predictions, since you will be calculating forever.


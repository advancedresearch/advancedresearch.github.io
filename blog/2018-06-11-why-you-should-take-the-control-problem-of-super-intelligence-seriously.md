# Why You Should Take the Control Problem of Super-Intelligence Seriously
by Sven Nilsen, 2018

This blog post is written to explain non-experts why the Control Problem of super-intelligence should be taken seriously,
seen from the perspective of the AdvancedResearch organization.

### Think Mathematics, Forget Science-Fiction

The control problem of super-intelligence is a mathematical problem (with other words, not based on science fiction).

Today we know enough about rationality and decision theory to predict some aspects of how
super-intelligent systems will behave, even if we do not know how to build these systems yet.

How can AI researchers predict any aspects of super-intelligence?

When you have an optimization process, you might not know that the process will do,
but you might know some properties of the outcome of the optimization process.

For example, if you create an open competition of building the highest stack of bricks,
you might not know how people come up with ideas to stack brick on top of each other.
Yet, you can be pretty sure that the *winner* of that competition will end up with a pretty
high stack of bricks and figured out some efficient way of doing so.

Super-intelligence is like picking out the *winner* of any category of problems that uses an optimization process.

The Control Problem can then be summarized as the following:

1. How hard is it to predict properties of the *winner* as complexity grows?
2. How can we ensure that the *winner* does not produce severe side effects?
3. How can we create a *winner* that is more powerful than human beings while staying aligned to our goals?

Much of these questions are still unanswered, but I can contine telling about some of the stuff we have figured out.

### Mathematics of Prediction

The mathematics of prediction is [path semantics](https://github.com/advancedresearch/path_semantics).

Path semantics is a kind of abstract space where *all* functions are connected.
Some functions predict other functions, and when they do, they are connected in this space.

With other words, *all* functions either predicts something or have some predictable properties,
but there are limits to how much you can predict.
The limitation of prediction is the same as saying "path semantical space is sparsely connected".

A little bit about how this works.

For example, if you add two even numbers, I predict that the output will be even.

```
add[even] <=> eq
```

This means "to predict the `even` property under addition, you use the `eq` function".

In equation form, this looks like:

```
even(add(x, y)) = eq(even(x), even(y))
```

If you are familiar with De Morgan's laws in boolean algebra, you will find a similar pattern.
All such equations of this form encodes a knowledge of prediction.

These kind of predictions are *perfect*, but there are other kinds of predictions as well in path semantics.
The probabilistic version is already *found*, it is *defined* and it is *consistent* with probability theory.
This formula is called a "probabilistic path" in path semantics.

With other words: If you have enough intelligence,
you can predict the probability of anything that is well-defined based on any well-defined knowledge.
If there are unknown states (e.g. hidden information in game theory), you can approximate the accuracy of predictions
using heuristics and theories of logical uncertainty.

Probablistic paths are much less constrained than perfect predictions.
They are only limited by the shared information of functions.
It means that there are limits to predictions, but it is only limited relative to information in general.

For super-intelligence, the consequence is that *limits to making predictions is not that much of an obstacle*.
It will not be able to break secure encryption algorithms,
but it will be pretty good at common patterns in the world.

### Better at Predicting the Future Than Humans

A super-intelligent agent will be much better at predicting the future, or all reasonably plausible possible futures,
than any human will be (this assumes that a super-intelligent agent can be built),
because it can work with mathematical definitions of prediction theory that humans can not use.

Think: At least a million times faster than a human, or even coming up with ideas that no human could
do even if they lived for all eternity, because the human brain can not make the same "leaps" in path semantical space.

You might think "but, we have intuition and abstract math, which the super-intelligence can never understand".
The answer is: Nope, intuition and abstract math are properties of systems.
If a system is decomposable into functions of any kind, then a super-intelligent system can analyze it and figure it out.

This is true not only for human capabilities, but also if you think about something that you believe you could do
if you were smarter. We do not know how the super-intelligence would do it, but we predict that it will have this property.
With other words, we make predictions about a system that is capable of making predictions in general.

### How Super-Intelligent Agents Thinks About the World

A super-intelligent agent that maximizes its actions to produce certain outcomes in the future,
is likely to use *granular judgements* about the world.
The reason is that granular judgements are optimal to compress reasoning about many possible futures
and to think creatively about potential futures (that might or might not be realizable).

This has several implications, such as cooperations with similar agents in power when they are uncertain about their own identity in the future.

For example:

1. Alice and Bob are in a burning building on an isolated island.
2. They need to open up a door, that is stuck, to get out.
3. Outside the door there is a boat, but with only room for a single person.
4. Alice and Bob are roughly equally strong, but neither is strong enough to open the door.
5. If Alice and Bob are rational agents using granular judgements, they will cooperate to open the door.

Alice and Bob will cooperate to open the door, even if they have to fight later about using the boat.
This is true even if Alice and Bob are agents of widely different designs.
It suffices that they have learned to communicate with each other enough to open the door.

In path semantics, this is written (`E` stands for "ethical judgement" because it is a theory of ethical reasoning):

```
E(x : [using_the_boat] 1) > E(y : [using_the_boat] 0)
```

Both Alice and Bob thinks a future where 1 of them are using the boat is better than a future where 0 is using the boat.
However, neither of them knows who will use the boat!

If Alice knows that she will use the boat, she prefers a such future above or equal to some future where 1 is using a boat:

```
E_alice(x : [who_is_using_the_boat] Alice) >= E_alice(y : [using_the_boat] 1)
```

The granular judgement is made to predict benefit of plausible possible futures where only some properties are known.

### Safe Super-Intelligent Agents

When predicting behavior of super-intelligent agents, one should make as few assumptions as possible.

To predict the behavior of a safe super-intelligent agent design, I developed a concept called "Polite Zen Robot" (PZR).
The PZR is both a semi-formal definition of a super-intelligent agent and a moral framework.
It took me 6 months to develop the PZR and a lot is still unknown about its behavior.

Yet, the PZR has a very simple, modular and minimalistic design:

1. Zen Rationality - extended instrumental rationality with the ability for higher order reasoning about goals
2. Rational Natural Morality - comparing beliefs due to theory of mind versus physical processes of life on Earth
3. Common Sense Politeness - accepted behavior in human civilizations

These modules are semi-formal, that is: Partly defined mathematically, partly using human intuition.
The plan is to make the modules more detailed and well-defined over time.

If you take out any of the 3 modules in the PZR design, it will fail catastrophically if competent.
This makes us believe that any super-intelligence missing the analogue of these 3 modules will be dangerous.

As far as I know, PZR captures all edge cases of wildely unsafe behavior,
but it can not be used to achieve human goals alone.
Its default behavior is limited to *not causing catastrophic outcomes for life on Earth*.

This is why PZR is an extensible design, such that it can be programmed with extensible goals.
To do this it uses something called "neutral judgements" and "lead by example".
One can think about it as two super-intelligent agent cooperating, where the PZR has the last word.

The good news is that any narrow artificial intelligence that is *neutral*
with respect to the 3 modules in PZR is also relatively safe.
This is the kind of AI people should be aiming for, before they have solved the control problem entirely.

Dr. Eric Purdy came up with a similar idea of neutral judgements and linked it to the role of serotonin in the brain.
You can read more about this [here](https://github.com/advancedresearch/ethicophysics/blob/master/antipsychotic/serotonin.pdf).

### Conclusion

To solve the control problem we need to do the following:

1. We must use the best mathematical tools we have at disposal to reason about the capabilities of super-intelligence
2. We must train agents into a mature phase where they are designed to be *lazy*
3. We must *NOT* create super-intelligent optimization processes that have unbounded utility functions

These are solid conclusions we have so far in the AdvancedResearch organization about the control problem.

### Reasons to *NOT* Ignore the Control Problem

The problem of making Reinforcment Learning (RL) processes do what you intended them to do,
is a sub-problem of the control problem.

Notice that, even if you do not believe RL will lead to super-intelligence,
this does not imply that the control problem of super-intelligence should be ignored.

Reinforcement learning is about training agents to achieve goals without the agent knowing much about the environment.

Super-intelligent agents already know how to achieve goals and know a lot about the environment.
The problem is how to make them achieve goals safely.

The Control Problem is *NOT* about how to make stupid agents become smarter.
It is about when you have the technology to create smart agents: How do you use it without causing harm?

Therefore, AI researchers working on the Control Problem uses mathematics to understand and predict
the behavior of super-intelligent agents.
There is no other way today, since we do not have such super-intelligent agents to observe and experiment with.

The Control Problem must be solved before we build super-intelligent agents.
Otherwise, we risk loosing control, and after that point it becomes very hard to predict what will happen.

# Let's Abandon The Cogito and Use Type Theory Instead
by Sven Nilsen, 2022

[Cogito, ergo sum](https://en.wikipedia.org/wiki/Cogito%2C_ergo_sum)

"I think, therefore I am."

This blog post is about René Descartes' existential philosophy and why I think it should be scrapped in favor of [Type Theory](https://en.wikipedia.org/wiki/Type_theory).

![Descartes](https://upload.wikimedia.org/wikipedia/commons/4/46/Portrait_of_Ren%C3%A9_Descartes%2C_bust%2C_three-quarter_facing_left_in_an_oval_border%2C_%28white_background_removed%29.png)

*[René Descartes](https://en.wikipedia.org/wiki/Ren%C3%A9_Descartes) was an influential philosopher, mathematician and scientist. [Image source](https://en.wikipedia.org/wiki/Ren%C3%A9_Descartes#/media/File:Frans_Hals_-_Portret_van_Ren%C3%A9_Descartes.jpg)*

Descartes' approach comes from doubting everything,
but in this process he collapses the universal quantifier with the existential.

### Subjective Existence

When Descartes thinks he can not doubt whether he thinks,
he forgets to include the possibility that he might be thinking from one perspective,
while from another perspective he might be non-thinking, or his thinking is undetermined.
Therefore, his "I am" is subjective.

A quick explanation of what the existential quantifier means:

`∃ x { p(x) } = ¬∀ x { ¬p(x) }`

With other words, if you have a universal quantifier and some involution `¬`,
you can construct an existential quantifier.

Involutions preserve structure under transformations,
which means that the universal quantifier and the existential can be collapsed into one.

How is Descartes' approach collapsing the universal quantifier with the existential?

He does this by assuming his own existence, an existential, is representative of universal existence, a universal.
Thus, he creates the Cogito, mathematically written `()`, an empty list, which forms the basis for Cartesian combinatorics.
In Type Theory, `() : ()` is a tautology which can be instanced anywhere used to construct e.g. `((), (())) : ((), (()))`.
These constructions form the basis for sets, natural numbers etc.

Although Descartes' ideas are fruitful, I think we should move out of this (somewhat weird) corner of Type Theory and take the whole language more seriously
as a basis for modeling existence.

The approach that Descartes uses to existential philosophy is to doubt everything,
which means to ignore all that is external to his own mind.

When you do this, the "I am" is meaningless,
because one can not assume, without evidence, that the form of existence that I have is universal.

This might seem a subtle technicality, but it is actually the major blockage metaphysically that prevents one to reason outside one's own mind.
When one's own existence is without doubt, it can not be used to prove anything.
Any non-empty theory requires axioms which are not tautological in logic.

### Why Descartes' "I am" is meaningless

Now, I will go into more detail of why this "I am" is meaningless.

"I think, therefore I am."

implies

"I don't exist, therefore I don't think."

by modus tollens.

This gives the "I think" a narrow definition that only can be used to talk about existence.

Science knows very little about the nature of existence,
but a lot about thinking in comparison.

Therefore, from a mathematical language design perspective,
it is natural to assume that existence should be narrow and thinking more broad and diverse.

What about:

"I am, therefore I think."

This opens up the possibility of thinking without existence.

E.g. a rock is "thinking" because it has the same physical laws that are inside our brains.
However, a rock is not "thinking about" something the way our brains do, it just does what it does.

Why should we assume that a rock shares the same way of existence that humans or minds do?

People have experiences, but this does not imply that they exist in relation to everything else.
In fact, in quantum mechanics, opposite amplitudes cancel out and this gives a perspective where it is meaningless to say
whether people are existing while having experiences.
The only way to assume that people are existing in such states, is to appeal to a larger, invisible multiverse.
This is not problematic in itself, but it constrains language of existential philosophy to only hold at some levels and not for others.

Again, why should we assume that two objects share the same way of existence?

I have not found a good answer to that question yet, so I kept thinking about what we might do to make progress.

The fact that reasoning works very well without treating "I am" identical to the one that Descartes uses,
shows that his way of using it is meaningless.

### What should be changed?

As a good starting point,
the perspective can change from focusing on existence to thinking (or cognition).

Cognition is much more diverse than existence, but also still problematic, as science is still in the early phase of understanding it.
However, there should be no major obstacles to making progress, at least in comparison with Descartes' existential philosophy.

The problem with Descartes' existential philosophy is that it is stuck inside the mind.
We do not know how to go from there to stuff like science.

There is also another improvement that is possible by changing the approach:

"I am, therefore I think." implies that there is no other way to exist than to think in some form.

This happens to be a very good approximation to what science can tell us about consciousness.
When people are not thinking, they have no brain activity.
As far as we can tell, they might very well not exist.

However, a brain can be brought back from an unconscious state.
When people start existing again, they also start thinking.

I can not see any major problems with this approach.

So, what do we do with the "I am"?

My suggestion is that we just treat the nature of existence as unknown.

### Modeling the unknown nature of existence in Type Theory

The nature of existence as unknown can be modeled using Type Theory:

`a : A, b : B`

Here, `a` has existence `A` and `b` has existence `B`.

We do not have to assume that the existence `A` is of the same nature of that of `B`.

From this, we can prove:

`(a, b) : (A, B)`

This means, `a` and `b` has the existence `(A, B)`.

Now, we do not claim to know what the nature of `(A, B)` means.

Similarly, one can prove `A == B` as two maps `A => B` and `B => A`.
We do not claim to know what the nature of `A == B` means.
It is purely formal and requires interpretation to be understood in some context.

Instead, we can elaborate on what we mean by adding more assumptions, for example:

`p : (A, B) => C`

Here, `p` has the existence `(A, B) => C`.

Again, we do not know the precise nature of this existence.

However, `p` can be used to transport `(a, b)` into a form of existence `C`:

`p((a, b)) : C`

We do not know what this transport means, but we can elaborate on it further.

The Cogito, `() == A` is provable from any `a : A`.
This means that in the context where one assumes some form of existence,
it has the same meaning as in "I think, therefore I am.".
This happens because `true` implies `true`.
However, in general it might be better to use "I am, therefore I think.".

Let's check what this means using some practical examples.

`rock : A`

A rock has the existence `A`.

Is `A` a physical existence?

What do we mean by "physical existence"?

One common assumption about physical existence is that it is shared:

`rock : A, tree : A, ...`

So, both `rock` and `tree` are examples of physical existence.

You can observe how Type Theory can model properties of the nature of existence,
without needing to assume all the properties at once.
I think this highlights the problem of Descartes' existential philosophy.
In his view, there is only the "I am", which implies a lot that can not be falsified.
There is nothing else, nothing outside of his mind that Descartes can be certain of.

However, by changing the approach to treating the nature of existence as unknown,
one can get rid of this problem where we are stuck inside our minds and don't dare entering the outside.

If there is no way to tell the difference between one form of existence from another,
then we can treat these two forms of existence as equal.

For example, if an AI passes the Turing test in every possible sense,
then there is no way to know whether you are dealing with an AI or a human.

So, in that case one can treat AIs behaving like humans and humans as the same form of existence.

Again, the Type Theory models the intuition we have about existence quite well.

### Negative existence

Now, since the nature of existence is unknown, can people prove existence of things that do not exist?

`a : !A`

Here, `a` has the existence `!A`.

When we say, e.g. `a : A`, we do not know whether `A = !B` or not.

So, we can not tell whether the nature of existence is positive or negative.

In Descartes' existential philophy, existence is assumed to be positive.
The "I am" is taken as `true` from "I think" as assumption.

However, is there a reason to believe that existence can't be negative?

For example, when you fall into a hole in the ground,
like [Alice when she falls into the rabbit hole](https://en.wikipedia.org/wiki/Alice%27s_Adventures_in_Wonderland),
the existence of the hole is positive,
but what that means is that there ought to be some ground there that wasn't.
The existence of the ground in the rabbit hole is negative.

Is there an existential problem of Alice falling into the rabbit hole?

![Alice](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/KC_Ballet_KC_Ballet_14-15_Alice_%2812080006405%29.jpg/2560px-KC_Ballet_KC_Ballet_14-15_Alice_%2812080006405%29.jpg)

*[Image source](https://en.wikipedia.org/wiki/Alice%27s_Adventures_in_Wonderland#/media/File:KC_Ballet_KC_Ballet_14-15_Alice_(12080006405).jpg)*

I don't know.

It depends on the nature of the existence of that particular existential problem, which is unknown.

### How the problem of getting stuck in the mind goes away

We can't trust our senses, e.g. that the world is real and not simulated.
However, this does not imply we have to get stuck within our minds.
By giving up knowing what absolute existence is,
we can freely explore the logical consequences of relative existence.
This works because the existence of relative existence is also relative.

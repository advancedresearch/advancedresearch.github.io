# Reinterpreting Computational Paradoxes - Part 2
by Sven Nilsen, 2023

[Link to Part 1](https://advancedresearch.github.io/blog/2023-03-13-reinterpreting-computational-paradoxes)

![Escher poster](https://upload.wikimedia.org/wikipedia/en/2/28/Escher_Poster_Dulwich_Picture_Gallery_2015.jpg)

*Poster advertising the first major exhibition of Escher's work in Britain*

In the [previous blog post](https://advancedresearch.github.io/blog/2023-03-13-reinterpreting-computational-paradoxes),
I talked about the importance of being able to put oneself in a sceptical philosophical position to what is being said.
Without being able to be sceptical, one opens oneself to [abstract corruption](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/abstract-corruption.pdf).
With other words, it is easy to believe something is true, when it is not, due to biases in languages or culture.

One important thing: Mathematical languages have biases too!

Abstract corruption is not something one can escape from entirely.
All cultures and all implementations of formal systems use abstract corruption in one way or another.
One can exploit abstract corruption, or become a victim to it, e.g. making one's life about making more money instead of living.

In this blog post, I will go more deeper into how to think formally about tautologies and paradoxes.

### Anxiety of The Whole

There is a particular emotional psychological response that is associated with paradoxical reasoning in humans.

This emotional response is called "Anxiety of the Whole".

Wikipedia describes anxiety as:

> Anxiety is an emotion which is characterized by an unpleasant state of inner turmoil and includes feelings of dread over anticipated events. Anxiety is different than fear in that the former is defined as the anticipation of a future threat whereas the latter is defined as the emotional response to a real threat.

However, Anxiety of The Whole is not about the future.

If somebody says:

"This sentence is false"

Then we can infer that this is a paradox.

However, humans do not simply think about paradoxes as paradoxes.
There is something "unsettling" in the emotional response when encountering a paradox.
This is the Anxiety of The Whole.

Anxiety of The Whole is kind of separation of the parts of a system from its total composition.
The emotional response is not due to any particular part of the system, but about the "wholeness" of it.

Paradoxes might produce this anxiety in humans due to an evolutionary trait that evolved, in order
to make humans pick the side that is most likely to win in a political conflict.

During evolution, when political conflicts appeared in a tribe,
the conflicts were often solved using violence.
The humans that survived the conflict spread their genes in the gene pool.
Those who picked the winning side, were more likely to get more offspring,
which in turn evolved traits to maximize the chance they picked the winning side.

So, when paradoxical reasoning occurs in society, it produces a signal in the brain that causes humans to look for "the winning side".

Anxiety of The Whole is just an emotional response, but it is also an emotional respone about "wholeness".
It means, human brains try to reason about the "whole conflict" and determine how to get out at the other end, surviving.

This notion of "wholeness" versus "parts" is important in paradoxical reasoning.

### Paradoxes and Tautologies in HOOO EP

A paradox in HOOO EP is expressed as:

```
false^a
```

The operator `^` is like a function pointer from a type `a` to an empty type `false`.

Here, the "wholeness" of the paradox is about `a`.

On the other hand, a tautology in HOOO EP is expressed as:

```
a^true
```

The intuiton of a tautology is that as a function pointer from a unit type `true` to a type `a`,
it is possible to construct `a` anywhere, by calling this function with `true`.

The expression `a` in `false^a` can be substituted by an arbitrary complex proposition that might also contain `^`.

For example, [Liar Paradox](https://en.wikipedia.org/wiki/Liar_paradox) can be expressed as:

```
false^((false^a)^(a^true) ⋀ (a^true)^(false^a))
```

If `a` is decidable, that is `(a ⋁ ¬a)^true`, then one can prove that the Liar Paradox is indeed a paradox.

However, when `a` is not decidable, it is not possible to determine that the Liar Paradox is a paradox.

This idea, of using decidability to determine a paradox, is important for paradoxical reasoning.

Think about it as when a human in an ancient tribe tried to figure out how to pick side in a political conflict,
the Anxiety of The Whole got triggered, filling the human's brain with emotions of feeling undecidable.

When one allows propositions to be undecidable, there is no problem with the Liar Paradox.

The proposition `(false^a)^(a^true) ⋀ (a^true)^(false^a)` can exist, in an indeterminate state without proving `false`.

However, since humans are biased, we like to make things either `true` or `false`,
such as which side to pick in a political conflict.
This bias might be due to the evolutionary trait that humans evolved to make such decisions.

It is not like humans consciously are aware of their biases.
The evolutionary trait is simply: Is this a paradox? Try pick one side.

### "Real Paradoxes" vs "Mere Paradoxes"

Anxiety of The Whole makes humans unsettled with indeterminancy.

At the same time one has to "pretend to pick side", the indeterminancy is also an important part of a paradox causing emotional response.

It is like, one can not actually determine a paradox without pretending to pick sides,
but it must also not be possible to prove `false` without pretending to pick sides, to cause Anxiety of The Whole.

Paradoxes that just proves `false` straight forward, are kind of "boring" to humans.

So, a "real paradox" is when one can not prove `false^a` without assuming decidability.

A "mere paradox" is when one can prove `false^a` without assuming decidability (constructive proof).

In the semantics of possible worlds, a paradox `false^a` is still a paradox,
since a paradox is defined by something not making sense in any possible world.

### "Real Tautologies" vs "Mere Tautologies"

Just like there are "real paradoxes" and "merely paradoxes", there are "real tautologies" and "merely tautologies".

A "real tautology" is when you can not prove `a^true` without assuming decidability.

A "mere tautology" is when one can prove `a^true` without assuming decidability (constructive proof).

Without the ability to see things from different perspectives,
one can not recognize a "real tautology".

For example, when somebody says:

"This sentence is true"

It sounds like the sentence is true.

However, *why* do you think the sentence is true?

Being sceptical is about placing oneself in relation to what is said,
in a such way that one does not believe what is said only because it sounds true.

When you have practiced thinking about "This sentence is true" as a lie,
you can see that it is a "real tautology".
It does not matter whether one is acclined to believe what is said or not,
because in either case, the interpretation confirms the position that is chosen, how one relates to what is said.

### Gödel's First Incompleteness Theorem

In Gödel's First Inompleteness Theorem, using Gödel encoding of some formal theory,
there is a sentence `G` that says no proof exists for the sentence `G`.

If one interprets `G` as a propositional statement `p`, one can not prove `p^true` nor `false^p`.

However, if one could prove `p^true`, then one can prove `false^p`, and vice versa.

This is basically the same as the Liar Paradox.

If a formal theory assumes that it is complete, that is every proposition is decidable,
then it assumes `(a ⋁ ¬a)^true` for all `a`.

One can show that such theories with Gödel encoding, containing [Robinson arithmetic Q](https://en.wikipedia.org/wiki/Robinson_arithmetic),
that they will be able to prove `false` using a Gödel sentence `G`.
Therefore, one can prove `false^p`.

However, if a such theory is constructive, which does not assume `(a ⋁ ¬a)^true` for all `a`,
then the best one can prove is `(false^p)^(p^true) ⋀ (p^true)^(false^p)`.

So, apparently, Gödel's First Incompleteness Theorem does not hold for constructive theories.

This is because this theorem was about "syntactical completeness" (decidability) and not "structural completeness" (constructive).
See [wikipedia article](https://en.wikipedia.org/wiki/Completeness_(logic)) for more information.

Now, this explains why a sceptical mathematican might not accept Gödel's First Incompleteness Theorem as a proof
that some constructive theories are incomplete. The problem is about the interpretation of the proof, not about the conclusion.

A naive mathematician and a sceptial mathematician might disagree about the interpretation of proofs,
regardless of whether the proof is sound. The ambiguity, where biases comes into play, is how proofs are interpreted.

# Reinterpreting Computational Paradoxes
by Sven Nilsen, 2023

For a couple millenia now, people have been interested and [fascinated by logical paradoxes](https://en.wikipedia.org/wiki/List_of_paradoxes).

![Escher's "Waterfall"](https://upload.wikimedia.org/wikipedia/en/e/e8/Escher_Waterfall.jpg)

*Esher's Waterfall*

However, what does it mean when we refer to a logical paradox?

Contrary to what most people believe, I believe that logical paradoxes are *boring*.
When I say that I think logical paradoxes are boring, I mean in a technical philosophical sense.
This means, I think people are exaggerating logical paradoxes to mean something that logic can not express,
simply because they misunderstand how truth in logic actually works, technically.

### Self-Referential Paradoxes

You see, the problem starts when you think `true` means "asserting a truthful situation".

Logic has never been able to assert a truthful situation.
It can only express true statements that hold in some context.

With other words:

If you have something you believe, then I can prove that there exists a context where what you believe is false.

It means, you never get to have the power over me of asserting that the situation you are in,
the context you believe proves what you believe in, is an actual truthful situation.

You see, I don't necessarily believe you even when you can claim what you believe in is true for the language bias you have chosen.

I am the one person who do not assume that what you are saying is true, unless I can prove it otherwise.
Instead, I think about what you are saying from my point of view.
It is not the same as disbelieveing you by default.
Instead, it is more like reserving both the right to biasing myself toward believing you, or biasing myself toward disbelieving you.
This is my freedom and it is not something you can take away from me.

For example, if you say:

"This sentence is false"

I claim to be able to prove that this is a paradox.

Do I care here whether the sentence is *actually* true or false? Nope!

Using my freedom to position myself relatively to the language bias you are using,
I can determine that if I am acclined to believe you, then what you say is not true.
Also, if I am acclined to disbelieving you, then what you say does not make sense according to my own position.

Thus, "This sentence is false" is a paradox.

Similarly, when you say:

"This sentence is true"

I claim to be able to prove that this is a tautology.

If I am acclined to believe you, then what you say is true.
If I am acclined to disbelieve you, then it makes sense for me to say that you are lying.
Why? Because if "This sentence is true" is a lie, then it is indeed a lie, from my point of view.

The trick that makes it sound like "This sentence is true" is asserting something truthful,
is called [Stealing the Voice](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/stealing-the-voice.pdf).

By buying into the fallacy of Stealing the Voice, one believes become open to [abstract corruption](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/abstract-corruption.pdf) by mimicry.

To reason properly about people who are liars, one must be able to imagine an information barrier between a social world
where people do not want to be able to prove anything and an internal region where people might use `false` as their assumption.

For example, I do not believe dictators, because they are empty inside.
They do not have an internal world of thought that interests me.

This is not the same as buying into the fallacy [Argument from Authority](https://en.wikipedia.org/wiki/Argument_from_authority).
If you believe me only because am the authority or because I am not the authority, then you are making this logical fallacy.

The emptiness inside dictators comes from the lack of personal growth and lack of a foundation in outlook of life through profound perspectives.
A dictator is a person who is not listening, but only giving orders.

If you are supporting a dictatorship, then I would say that you are boring person.
You believe someone just because if you do not believe them, they will threaten you?
This should be thought of as an offense to your personal dignity and freedom.
Where is the freedom where you can interpret what people are saying from different points of view?

Join me in the exercise to think about people as both liars and truth tellers!

This is what I mean when I say "Freedom of expression is important to me".

Now, it is not an unbiased position to only point your fingers on people like dictators.
What if you are like a dictator yourself? Are you empty inside sometimes?

Confronting this possible situation where one's own internal world of thought is empty,
is an important step toward personal growth.
If you can call yourself out on your own bullshit, then this gives you room to improve, personally.

You can kill the dictator from within, metaphorically, no matter which person this is, including yourself.

This is because, without personal freedom to choose how you interpret what is being said,
you will never be able to make logic mean what it means in your own life.

From this perspective, I will now turn away from self-referential paradoxes and towards *Computational Paradoxes*.

### Computational Paradoxes

A computational paradox is different from a logical paradox,
in the sense that it has additional meaning besides,
also in a such way that it can be difficult to view it as a logical paradox.

For example, [Gödel numbering](https://en.wikipedia.org/wiki/G%C3%B6del_numbering) is a method to create computational paradoxes.

Gödel showed that in any formal system that is capable of encoding arithmetic (Peano axioms with addition and multiplication),
there are statements that have no proof, nor a counter-proof. This was Gödel's First Incompleteness Theorem.

Let us go back to this sentence:

"This sentence is true"

Since the sentence can be interpreted as both a truth and a lie, it is a tautology.

What Gödel found was that formal systems capable of encoding artihmetic and self-reference contained tautologies.

- If we are inclined to believe that the statement with no proof, nor a counter-proof is true, then it sounds true
- If we are included to believe that the statement with no proof, nor a counter-proof is false, then it sounds false

So, here my perspective differs from most people who only think these tautologies sound true.
The statement with no proof, nor a counter-proof, is a mirror reflection of the reasoner.
If you say what you think about it, then you reveal some information about yourself.

This is why a dictator uses paradoxical language:

- Those who say they do not believe the dictator, become labelled as "rebels"
- Those who say they believe the dictator, become labelled as "followers"

The paradoxical language in a dictatorship is used to divide and conquer people.

A computational paradox is more difficult work with,
because you have to be aware of multiple levels of language at the same time.

Now, to an important question:

*Did Gödel show that formal systems with arithmetic were incomplete?*

- To the naive mathematician: Yes
- To the sceptical mathematician: No

It was only later when mathematicians showed that there are useful non-trivial statements with no proof, nor a counter-proof,
that made the proper argument about incompleteness in formal systems.

### Formal Treatments of Tautologies and Paradoxes

When I think about tautologies and paradoxes, I use the following formal system:

- Intuitionistic Logic
- `a^true` says "`a` is a tautology"
- `false^a` says "`a` is a paradox"
- `a^b => (a^b)^c` (HOOO power lift)
- `(a => b)^c => (a^c => b^c)^true` (tautological HOOO implication)
- `(a ⋁ b)^c => (a^c ⋁ b^c)^true` (tautological HOOO or)

The 3 last axioms make up [Higher Order Operator Overloading Exponential Propositions](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/hooo-exponential-propositions.pdf) (HOOO EP).

This formal system was designed to make sense constructively in Type Theory.

However, most logicians think about `a^true` as `□a` in Modal Logic in the sense "`a` is provable".
They use a different set of axioms:

- `□(p → q) → (□p → □q)` (distribution)
- `□(□p → p) → □p` (Löb's theorem)

This system makes up [Provability Logic](https://en.wikipedia.org/wiki/Provability_logic).

Provability Logic and HOOO EP are inconsistent together.
In particular, assuming Löb's theorem in HOOO EP, proves `false`.

This means, if you are acclined to believe what is said is meant to be true,
then you reason like in Provability Logic.

On the other hand, if you are acclined to disbelieve what is being said is meant to be true,
then you reason like in HOOO EP.

As a result of the freedom of choosing one's own perspective,
one can not simply assume that Gödel's First Incompleteness Theorem actually shows incompleteness of formal systems with arithmetic.
Only because a statement has no proof, nor a counter-proof, does not make it automatically "true" from my point of view.

Q.E.D.

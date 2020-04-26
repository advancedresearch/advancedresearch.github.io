# The Core Axiom
by Sven Nilsen, 2020

Logic can be used to model ideas.

For example, if `A` is a fact, and `B` is a fact, then `A ∧ B` is a fact.

This is a specific interpretation of logic as `true` meaning "is a fact" and `false` meaning "is not a fact".

Logic does not tell you *how* to interpret logic.

If you choose a specific interpretation, then you need to stick with it.
This causes problems when you want to combine multiple interpretations.
Why? Because each interpretation kind of "fills up" the entire logic.

Proof: There are only `true` and `false`, which each is assigned a meaning.  
In order for a logic to make sense, you have to assign different meaning to `true` and `false`.  
Therefore, in total there are 2 meanings in an interpretation of logic.  
No more, no less, hence the interpretation "fills up" the entire logic.

Anyway...

### Tautologies

A tautology is a logical fact.

Tautologies and proofs are the same.

```
f <=> \true
```

A function `f` is a proof if it returns `true` for all possible inputs.

In mathematics, one proves things to check whether they are true or false.
After the proof has been found, one can just ignore it forever,
since the knowledge that the proof exists is all we need.

Axiomatic logic concerns itself with defining rules for proofs.
Mostly, it is a technique to prove more complex things than checking every possible inputs.

A modern laptop today can easily check all proofs up to 40 bits in a few seconds.
Axiomatic logic is needed for proofs that are much more complex.

### Assumptions

When you pick assumptions, you do so because you have a particular model in mind.

For example, a machine consisting of different parts, where the parts relate to each other.

The description of the machine are assumptions that you "add to" logic.

In order to reason automatically about something,
there must be enough assumptions added in order to derive the conclusions.

This is done in the form:

```
a => b
```

Where `a` is a list of assumptions and `b` is a list of conclusions.

You can also have an assumption with its own conclusion, like this:

```
(a => c) => b
```

However, a tautology does not add new information to the assumptions.
Since a tautology is `true`, it already follows from the rules within logic itself.

Therefore, there is no such thing as a model, or list of assumptions, which also is a tautology.

### Symbols

You use symbols every day. They are everywhere.

However, what do symbols mean?

How do symbols work?

A symbol works by identification and assocation.
When two symbols are identified with each other, their associations are also identified with each other.

One might think that symbols are so fundamental that they are a tautology.

Intuitively, it feels like symbols should just be a logical consequence, without any added assumptions.

Surprise: This is not true!

Symbols are "almost" a tautology.

With other words, the semantics of symbols looks like a logical fact, but in fact, it is not a logical fact.

### Putting this together

What is the interpretation of a logic modeling symbols?

This is easy:

- `true` means "this symbol is used"
- `false` means "this symbol is not used"

For example:

```
a => b
```

This means that when `a` is used, then `b` is used.

The definition of "used" is very vague, but this is why logic is so powerful.
It does not matter which precise interpretation is used, since the same logical structure appears everywhere.

So, the expression `a => b` can be thought of as some sort of general association.

Now, here is a tautology about symbols:

```
(F0 => X0) ∧ (F1 => X1) ∧ (F0 = F1) ∧ (F0 ∨ F1) => (X0 = X1)
```

This means, when two symbols are identical,
and they associate something, if one of the symbols are used,
then the things that are associated with the symbols are identical.

With other words, each time you see a symbol,
it is intended to mean something, consistently.
It does not matter what the symbols mean.
No matter what they mean, they always mean the same thing.

Since this is always `true`, there is no need to add it as assumption.

There is just one problem: This is not the correct model of symbols!

### Undefined Symbols

A symbol that is undefined, means the same to the observer as another undefined symbol.
The observer can not associate anything with undefined symbols, or more precisely:

The observer associates *nothing* with undefined symbols.

However, you can not know what this "nothing" is, either.
It is kind of like an unknown association.

If you have to undefined symbols `A` and `B`, then you can say they mean the same to you,
but you can't say exactly *what* they mean... this is what undefined means.

An old friend of mine used to say "There is no such thing as nothing".

The tautology about symbols I used, can not prove this.

There is no structure built into logic that gives this conclusion.

### Path Semantics

The core axiom of [Path Semantics](https://github.com/advancedresearch/path_semantics) is the following:

```
(F0 => X0) ∧ (F1 => X1) ∧ (F0 = F1) => (X0 = X1)
```

Here, I just removed `(F0 ∨ F1)`.

This means, that if two things are symbols, it does not matter whether they are used or not.

As if by magic, it now provides the right model for symbols.

Well, there is a small technicality added for axiomatic logic:

```
F0 > X0
```

This is used to prevent paradoxes that are special for such theories.

This is the final form:

```
(F0 => X0) ∧ (F1 => X1) ∧ (F0 = F1) ∧ (F0 > X0) => (X0 = X1)
```

Well, I *hope*. Although, there is no big crisis if it does not stay that way forever.
I am pretty confident that the proof techniques derived from it will still work in the future.

### Ignorance is Bliss

When I wrote down the core axiom for the first time,
I had no idea what I was doing.

I just tried to write down the simplest possible thing I could.

Luckily, this saved me from "correcting" the axiom to a tautology.

I believe that if I understood more logic at that time,
I would have mistakenly thought that symbols ought to be a logical fact.

Kind of ironic, is it not? That the core axiom was a "lucky guess"?
Sometimes it is better to know too little than not enough.

It was not until very much later that I understood what this meant.

Now, I hope you can understand it too!

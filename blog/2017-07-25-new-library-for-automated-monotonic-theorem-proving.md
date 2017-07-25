# New Library for Automated Monotonic Theorem Proving
by Sven Nilsen, 2017

Link to project: https://github.com/advancedresearch/monotonic_solver

For a long time, I had two problems I would like to solve:

1. How to define inference rules for a working sub-set of path semantics
2. How to generate a story plot where you control outcome + desired events

Now, I am making some progress on both these fronts, and it is due to this library allows
me to iterate on the designs more quickly.

The difficulty of solving these problems is that they are very hard problems on their own,
but coding the underlying system is also a hard problem. So, these are double-hard problems.
Solving these two problems could be used to solve even harder problems - e.g. constraint solver for automated engineering.

### Inspiration - Natural Language Semantics

Lately, I have been diving a bit into machine learning of natural language semantics.
I find it interesting how natural language deviates from logic in the sense
that you can speak about hypothetical agent states-of-mind.

For example:

```
I believe you should stop doing that and do something else instead
```

Can be reduced to:

```
I believe X
X = you should stop doing that and do something else instead
```

Notice how the structure is nested, with semantics such as "believe", "think", "suspect", "see" etc.
You do not have to know the semantics in order to reason about it,
because I could invent a new way e.g. "I perbls X" with its own set of rules for "perbls",
independently on what existing concepts people use for reasoning about agent states-of-mind.

Breaking the structure down further:

```
I believe X
X = should Y
Y = Y1 and Y2
Y1 = stop doing that
Y2 = do Z instead
Z = something else
```

In Rust, you can write this as an AST structure using `enum`:

```rust
pub enum Expr {
    IBelieve(Box<Expr>),
    And(Box<Expr>, Box<Expr>),
    StopDoingThat,
    DoInstead(Box<Expr>),
    SomethingElse,
}
```

A proof is stored as `Vec<Expr>`. The first items are the start facts, and new inferred facts builds on previous facts,
until all goal facts are reached.

Now, you can infer new additional facts and underlying assumptions that are not directly communicated.
The challenge is to code these rules, which can get very complicated.

Sometimes, when you have a difficult language-problem, a good idea is to investigate
whether you can use the structure of the language directly for inference.

For example, in this case, when somebody says "I believe X" we usually make assumptions like:

- X could be important for the person who says it
- X is suggested as an idea to consider in a matter of uncertainty
- It could mean to be a joke, as when X is obvious

A joke can be saying "I believe I should drive on the road" after ending up in some field after a car accident.

Now, if you try to code what "obvious" means in a computer program, you will find out that it is very hard.
It is much easier to add a label "obvious" and connect it to sentences that are obvious,
and then use rules to decide what to infer from the sentences that are labeled "obvious".

```
if X is obvious, then Y
```

This means that instead of creating a deep level understanding of the world outside,
you are just connecting knowledge using the syntactical structure as a form of "code",
and then define rules in terms of this code.

There is another trick: Instead of trying to build a coherent model of what is going during a conversation
by e.g. using logic checked for consistency,
one can use context-aware anticipation goals to control how inference is directed,
then erase all inferred knowledge that is irrelevant to the goal.

For example, when a man smiles a little and then keeps his voice controlled and unemotional, you can expect he is going to tell a joke.
Half the art of telling jokes is how you tell them, not just the content.
I am sure everybody got these moments thinking "oh, he is going to tell a joke, here it comes".
The person telling the joke is giving you a signal, to activate your neural-joke-inference algorithms inside your brain.
All neural-serious-inference algorithms are turned off, or at least filtered, such that you can understand what is said.

All these things are part of what artificial intelligence researches call "common sense".
It is a complicated set of unspoken rules that it is assumed that everybody behaves as if they know it instinctively.

The key thing is that common sense must be stored in some form,
and structured such that it can be triggered by data.
Imagine common sense knowledge stored as a graph,
and you "trigger" it in a given node.
This starts an activation chain in several directions.
If you hit the goal, then the search terminates,
and the useful steps to reach the goal from the start is returned as a proof.
Most of the time, it is the proof that carries interesting information,
not the goal itself.

Now, you have the following problems:

1. Given some rule, how do you know whether you already have checked it or not?
2. How do you know what inferred knowledge a rule depends on to determine irrelevance?

This is part of the problem that makes it hard to code.
One can use a graph, but then you will have great difficulty making changes rapidly in the design.

I figured out how to solve these problems, when using Rust enums to represent the AST:

1. Re-create inferred facts all the time, quickly, and then perform checks using the `HashSet` data structure
2. After finding a solution, modify the filter and re-solve the problem to check irrelevance, working from backwards, one inferred fact at a time

For relative short chains of reasoning, this actually works pretty good.
The benefit with this approach is that dependencies between rules are implicitly known by using the inference algorithm alone.

The solver is forward-only, so it is stricly sound for monotonic logic only.
I want this for performance, because for worst-case exponentially running time problems,
I already got the [quickbacktrack](https://github.com/advancedresearch/quickbacktrack) library.

In practice it is difficult to keep to strict monotonic logic,
besides controlling the shape of the proof in story plots,
so I also added a way to control order of inferred facts, called "after-constraints".
It does not make it generally capable of solving non-monotonic logic,
because the precision of resolving such conflicts is not universal,
but it gets close enough to work with some story plots.

Another property of the solver is that when it reduces the proof,
it simultaniously removes contradictionary inferred knowledge that does not lead to the goal.

These properties means you can use it on a slightly larger class of problems than monotonic logic,
while enjoying the performance of a forward-only solver.

### Understanding Monotonic vs Non-Monotonic Reasoning

The standard example I use for natural language understanding is a very tiny sub-set for romantic plots,
which you can read about in the blog post [Slot Lambda Calculus](http://blog.piston.rs/2017/04/20/slot-lambda-calculus/).

```
Bob loves Alice.
Alice loves Carl.
Bob see Alice loves Carl.
Bob hates Carl.
Carl see Bob hates Carl.
Carl ignores Bob.
Carl see Alice.
Carl loves Alice.
Bob see Alice see Carl loves Alice.
...
```

In principle, such story plots are not monotonic, because you can have `X loves Y` then `X hates Y`,
but not introduce `X loves Y` a second time to override "hate" with "love".
This leads to inconsistency.

- It might work for short story plots, where you assume people are roughly consistent with their preferences.
If it does not work, you can modify the filter to resolve the inconsistency.
- You can add a number parameter, e.g. `X loves Y for the Nth time`.

As you can observe, the relationship between monotonic and non-monotonic is complex and depends on the kind of rules you use.

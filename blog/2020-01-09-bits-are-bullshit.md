# Bits Are Bullshit
by Sven Nilsen, 2020

This blogpost is about an idea that is extremely controversial, yet my current position is that this idea is worth thinking about.
I welcome anyone to join the discussion about this topic and how it might influence our view of computers for the future.

The invention of bits is one of the greatest in human history,
of which everybody agrees on, so when somebody comes around and says it is bullshit,
there are two likely possibilities:

1. The person understand it less than everyone else
2. The person understand it more than everyone else

This is because the position is so extreme, very few people holds it,
but it does not mean it is necessarily wrong.

It just happens that very few people have thought deeply about this topic yet.

Sometimes, an idea comes around that changes the way we think about something familiar.
These ideas comes from reasoning about and questioning stuff we think everybody knows.

The definition of a bit is that it either (XOR) can be `0` or `1`.
In programming there is a type `bool` or `boolean` named after the largely self-taught mathematician [George Boole](https://en.wikipedia.org/wiki/George_Boole).
The implementation of a boolean variable is not the same as a bit in computer memory,
but mathematically we say that these two structures are "isomorphic".
It means that a bit can be converted into a boolean and vice versa.

So, when I say that bits are bullshit, I mean all isomorphic structures to bits.

What is interesting about bullshit is that there are very few words in the english language
that describes precisely what we mean about it.
Other words that one can use are "nonsense" or "noise", but I find these a bit misleading.

Bullshit is not like noise, because noise can be useful, while bullshit can be harmful.

Bullshit is not like nonsense, because nonsense is a form of extreme, pure bullshit.
There are many forms of bullshit, but the most common form is one that carries some semantics with it.

Bullshit is used to provoke emotions or bias decisions.

When you think of bullshit, it is easy to picture a politican or someone that intentionally lies
and uses language to influence the public opinion about an important topic for personal benefits.

The way I use bullshit here is from a system view, such that bullshit has a more general and universal meaning.

Why is it that bits are bullshit?

Because bits are used to model stuff in computers, and in reality most bits we use
are either `0` or `1` semantically, forever and not changing.
I think you would have objections to this statement, but just play along and see how the argument goes.

A computer uses bits to make decisions.
For example, if a bit is `0`, it does action A and if it is `1`, it does action B.
If we knew we wanted action A, there would be no need to use the bit at all.

When I say that bits are bullshit, I mean that what we use them to figure out which action to perform,
while in reality, it is already determined which action we will perform (without the bit).

This phenomena happens because in order for a Turing machine to execute,
all choices must either be predetermined or chosen based on previous predetermined choices.

A Turing machine does not contain noise.
It has no uncertainty.

The standard definition of a Turing machine makes us think that it manipulates symbols on a tape,
yet you could construct a Turing machines that never writes to the same memory twice.
Simply: Write all new symbols to new positions on the tape.
In this model, every "bit" has either a value `0` or `1` on the tape, but never both over time.

This does not take into account the state the machine needs to keep track of new vs old symbols.
You can not construct a Turing machine in which no part operates on bits,
but you can make it use arbitrary amounts of memory which does not behave like bits.

So, in a sense Turing machines do not need bits mathematically, they could just execute.
You can record the actions that a Turing machines does for a given input.
The side effects of performing the actions is all that we need.
However, a such machine without side effects would not be useful.

You can see how the argument goes from here.
Bits are used to program Turing machines, as a method to reason about what the Turing machines will do.
The moment the Turing machine starts to execute, the bits are in a sense gone, mathematically speaking.

The computers that we use, are extended Turing machines that receives user input, measures time, generates noise and so on.
These sources of data are modeled in bits, building up the abstraction that helps us reasoning about it.

In order for us to reason about programming,
we use programming languages which builds on bits as the fundamental building block,
but the end result we want to generate, is the side effects from executing or compiling the code.

Mathematically, the definition of bits is not necessary to achieve any goal we would a Turing machine to do.
Hence, bits are bullshit. Each bit is a waste of resources.

However, a such jump to conclusion assumes that we can predict what a Turing machine will do, which we can't.
Neither does it take into account a quantum view of the universe.

One would think that the argument goes away, but the problem is much deeper:

- We often design software that is much more flexible than needed at the cost of performance
- We prove things about software using mathematics that never will be realized in practice
- We build philosophy around ideas that assumes e.g. infinite amount of memory (for example: natural numbers)

With other words, we often treat bits as an required resource and as the smallest building block of computer science.
The danger is that such hidden false assumptions can carry over to real systems.

A naive thinking about bits makes us blind to the actual smallest building block of computer science: Actions.

Actions are much harder to reason about than bits, because they deal with the real world.
A characteristic of our time is that it is convenient for people to ignore the real world, pretending it is not there.
Instead we often build abstractions that makes us think about the world in a distorted way.

When I think about actions, I do not mean just e.g. what to do next,
but also about information one should collect or pay attention to.

What I hope you get out of this post, is what seems like an obviously wrong position at first,
can say something deep about an approach to reasoning about systems.

Are bits bullshit, or not?

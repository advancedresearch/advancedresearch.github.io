# More Real Than Reality
by Sven Nilsen, 2017

This post is about an idea continuing from the line of research described in the post
[Does Nature Have Intelligence and Can We Harvest It?](https://github.com/advancedresearch/advancedresearch.github.io/blob/master/blog/2017-06-16-does-nature-have-intelligence-and-can-we-harvest-it.md)

One of the greatest invention done by mankind is the number system.
The benefit of numbers is that they are not real - they are used to predict some aspect of reality.
Being non-real makes numbers very cheap: You just need a bit of constructive imagination.

Some people object to this idea, but they usually mean the "activity of using numbers being real",
so I will leave this topic for discussion and continue assuming it is natural to at least think of different kinds
of reality, some kinds more real than others.

Formally, what I am thinking about a lot is how functions behave and relate to each other.
A function is something that takes an input and produces an output.

The weird thing about functions is that some of them predict other functions,
and they do this is in a deterministic, but highly non-trivial way.
I spent a lot of time the past few years studying how this happens,
and as a result I came across a lot of useful concepts.

Just like numbers are used to predict some aspect of reality,
one can imagine abstractly that the concept of numbers `N` and the corresponding part of reality `R`
is related by measurement `M` in a relationship like this:

```
R[M] <=> N
```

This is a valid expression in [path semantics](https://github.com/advancedresearch/path_semantics), when the variables are functions.

In practice, it is much harder to define both numbers and reality as functions,
so one must not take this relation literally,
but rather use one's imagination and think of these symbols as a more abstract concept.

However, my intuition about thinking how the worlds tell me that the same way functions of particular
kinds can be related to each other this way, is analogously similar to how e.g. reality and numbers are related.

The question is then: What is reality?

### The Butterfly Dream

昔者莊周夢為胡蝶，栩栩然胡蝶也，自喻適志與。不知周也。  
Once, Zhuang Zhou dreamed he was a butterfly, a butterfly flitting and fluttering about,  
happy with himself and doing as he pleased. He didn't know that he was Zhuang Zhou.

俄然覺，則蘧蘧然周也。不知周之夢為胡蝶與，胡蝶之夢為周與。周與胡蝶，則必有分矣。此之謂物化。  
Suddenly he woke up and there he was, solid and unmistakable Zhuang Zhou.  
But he didn't know if he was Zhuang Zhou who had dreamt he was a butterfly,  
or a butterfly dreaming that he was Zhuang Zhou.  
Between Zhuang Zhou and the butterfly there must be some distinction!  
This is called the Transformation of Things.

(pasted from https://en.wikipedia.org/wiki/Zhuangzi_(book))

Intuitively, a man dreaming of being a butterfly seems less silly than a butterfly dreaming of being a man.

The direction of such "reality" dreams are decided by the path generator function,
or the "measurement" `M` if you will.

When two functions `f` and `f'` are related to each other in both directions:

```
f[g] <=> f'
f[g'] <=> f
```

then, they are isomorphic to each other.

There exists a such relationship for every permutation of the input arguments of a function.
Transferring this meaning to the concept of reality of numbers,
it does not matter much in particular which reality we live,
because nobody can tell the difference,
but it matters which *cluster of isomorphic realities*.

While this might seem a bit strange, to suggest that "it does not matter whether there exists other identical worlds or not",
it is merely a consequence of the following pieces:

1. We start out assuming reality and numbers are related in a similar way that functions are related to each other
2. We can not encode reality as a function without picking some way of ordering the input arguments
3. The order of input arguments does not matter

For all we know there could be a world for every way of ordering the input arguments,
but right now we have no way to test this, so we have to leave this topic too and continue.

### The Reality Beneath Reality

Once upon a time, some people on a small planet called "earth" discovered the laws of light and electricity.
One of was [Michael Faraday](https://en.wikipedia.org/wiki/Michael_Faraday) who did a lot of experiments and
[James Clerk Maxwell](https://en.wikipedia.org/wiki/James_Clerk_Maxwell) who formulated the theory of classical electromagnetism.

It took a while from that point in history before some other people discovered that the laws of electromagnetism
was just a phenomena predicting aspects of a more detailed underlying theory,
which resulted in two seemingly contradictory directions: General relativity and quantum physics.

Since then, physicists have gotten used to the idea of deeper and more accurate theories.
However, what if the theory of everything is not related to laws we know in a similar way as before,
but it relates in a surprising and very different way than expected?

### The Effects of Taking Limits of the Behavior of Exponentially Growing Computers

What if the universe is governed by a set of laws that are fundamentally different from what we observe?

*What if the universe is - kind of - like a butterfly dreaming of being a man?*

A such transform is only possible under extraordinary circumstances.
It takes a totally different way of thinking about the world than the way we are used to.

However, it seems that the ingredients for justifying such extraordinary claims are justifiable:

1. The universe could undergo a rapid, eternal cosmic inflation
2. The observer selection effects, by simply existing inside the unverse, could be extreme

The problem with calculating such predictions is that they are very sensitive to
how you compute the limits. If you make a small mistake, you could end up with a complete different world.

For example, one reason some people think this idea of an inflating universe might be wrong,
is because they expect a higher temperature compared to the one we are seeing.

Other people think along the lines "there are more chineese people, so I would expect to be born chineese".
Well, this might seems strange for non-chineese people, and more right for chineese people.

Perhaps such predictions are not that helpful because they are very sensitive to small underlying assumptions.
So, what kind of predictions could be more robust?

### Kolmogorov Complexity

If the universe starts out as a uniform distribution of energy, then it is kind of like starting
drawing with an empty sheet of paper.
To create a complex object, you need more time than creating a simple object.

In computer programming, the shortest program that creates an object is called [Kolmogorov complexity](https://en.wikipedia.org/wiki/Kolmogorov_complexity).

With other words, you start out with an empty text file,
and then try every button on the keyboard,
but only adding a single character while saving to a new text file.
Some of the programs will not compile, but others will.
Once you have a program that outputs a human, you stop.

I have not figured out what predictions about Kolmogorov Complexity an inflating universe should give,
but it seems to me that the ingredients are there and this could be a less sensitive prediction.

For example, the human brain is quite complex, but how much is this attributed to brains producing observers?

Or, to put it is more simple terms:

*If I forgot that I am a human and not a butterfly, should I expect to be a butterfly?*

The strange thing is, that from the perspective of the traditional view of the universe,
it seems more likely to be an observer with a simple mind, since these could be easier to produce
by starting out with a uniform distribution of energy.

On the other hand, if we condition on living billion of years after the earliest moment of time,
then one expects to have very high complexity in an inflating universe.

So, you end up with two different conclusions based on how you reason! Which one is true?

There could be a mixture of these two effects presented in the observer selection effect.

- First, one could assume that brains have a property of producing "observerness"
- Second, once a sufficiently complex observer appears, it "takes over" the numbers of simpler observers

In a such kind of universe, one would expect to be living relative early compared to the total time of the universe,
while being complex enough to have these thoughts about the world.

This is a pretty weird idea, but the question is: Do we have the right ingredient at hand?

### Everett Branches of Yourself

*Notice: The follow is not how the Everett interpretation of quantum mechanics works,
but let us assume something similar happens for the sake of the thought experiment.*

Imagine that for a few moment ago, there was just a single copy of yourself in the entire universe.

Then, your brain has an idea: What if there exists more copies of myself?

This thought was then, for some mysterious reason we will ignore, subject to the uncertainty principle.
The next thing that happened was the particles making up your mind
came in super-position, where one version of yourself thinks "yes!" and the other thinks "no!".

As these two versions of yourself started interacting with the world,
they caused the environment to enter in a similar super-position state.
Slowly, at the speed of light, the world starts to branch off in two major directions,
one where you believe in more than copies and one where you believe in a single copy of yourself.

The brain processes information, and this has a lot in common with the nature of functions.
Some people believe you can measure how much a network of information processing mechanism will generate consciousness.

What I think can be the case, is that because small variations in thoughts can have big impacts
on the world, it could have a different effect than local low impact variations occuring in chaotic systems,
such as molecules in the ocean.

I do not believe having particular thoughts makes you more conscious than others.
However, if you imagine a large variation of thoughts, then you could expect there to be a large
variation of high impact events in the worlds that follow from that point in time.
Much more so, than e.g. a molecule moves slightly in one direction compared to another in the ocean.

The problem is, when you look at water in the ocean, you do not really see the physical state.
There are many more physical states possible that explains what you observe,
than we are able to count.

Comparing the number of physical states in one kind of system to another is very hard,
you know, because we do not have the right tools to compare them yet.

In the middle of these technical difficulties, we do not know what it means
to describe an observer as complex as the human brain moving through these possible future branches of the universe.

However, assume that this works out, then would you expect similar information networks to your brain
produce observers faster than your own brain? What happens when you are "out numbered" by other kinds of observers?
This is actually a possible experiment, by e.g. inventing an AI that is far more complex and smarter than ourselves,
that self-produces much faster than humans are capable of.

### What Happens When The Universe Inflates for Long Enough Time?

If the universe inflates at an exponentially rate, doubling at fixed intervals, for a very, very long time,
then the observer selection effect is "kind of integrating" over all possible worlds.
The ratio of any kind of objects converges to a fixed probability.

So, what you would see as an observer inside a such kind of universe,
is a result that is more like an "output" of an extremely complex function than some "temporary" compution.

It could be that this process could have resolved all these seemingly paradoxes,
by smoothly transition from one kind of information process network to another.

For example, you get born as a human baby, and slowly grows into an adult brain,
then you gradually merge with a newly discovered information technology,
until you become part of an ever-growing complex network!

Or, perhaps all incredibly unlikely technological race we observe today is just a coincidence?

### Going Deeper and More Serious About an Even More "Real" Reality

All these things are fun to think about, but what scientific predictions are there to be made?

One idea I have is that the kind of path integration used in quantum mechanics,
could be isomorphic to the kind of integration that would happen in an eternal inflation universe.

So, instead of thinking that observers live in a quantum universe that inflates eternally,
we could be living in a universe with quite different sets of laws than what we see,
but where the limit transform corresponds to the quantum behavior we observe.

With other words, I am imagining something like this:

```
R2[X] <=> R
R[M] <=> N
```

So, when I think about numbers, what happens is something like this:

```
R2[X][M] <=> N
```

Just like quantum mechanics turned out to be a more precise description of classical electromagnetism,
there could be a transform from something else to quantum mechanics.

A while ago, I did an programming experiment reading up and thinking about Feynmann path integration,
and ended up with a picture like this:

![observer-wave](http://i.imgur.com/LJA5kTy.png)

This shows the difference in probabilities compared to some classical stochastical mechanics.
Red color is higher and green color is lower.
Because probability always adds up to one, one can not increase it somewhere without decreasing it elsewhere.

It has been a while since I worked on this, so I do not remember all the details without studying the source code and my notes closer.

What I expect to find, if this works out,
is some other function that produces all states that quantum mechanics predicts,
but with different probabilities that can be transformed through minizing time,
which is caused by the observer selection effect.

You can find the source code [here](https://github.com/advancedresearch/observer_selection_effects/tree/master/obs_wave).

One problem is that when a particle bounces off a wall,
the contributions from various paths can change the symmetry of the transform,
so at the moment this seems a bit hard to make progress on without making some mistakes somewhere.

Still, I hope you like the idea!

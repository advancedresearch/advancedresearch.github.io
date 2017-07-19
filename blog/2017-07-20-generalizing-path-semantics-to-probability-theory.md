# Generalizing Path Semantics to Probability Theory
by Sven Nilsen, 2017

[Path semantics](https://github.com/advancedresearch/path_semantics) is a new field of computer science
that studies meaning of programming and mathematics by using functions as fundamental structure.
It generalizes type theory to allow arbitrary sub-types defined by functions.
Path semantics is easy to reason about by extending the syntax of mainstream programming languages,
and makes it possible to transition seamlessly from programming syntax to equations and vice versa.
The notation helps programmers to recognize equations that describe a type-to-code relationship.

Path semantics exploits the fact that many useful mathematical equations share a similar structure:

```
g(f(a, b)) = h(g(a), g(b))
```

Such equations appear when you have a function `f` which operates on objects with a property `g` you want to predict the result with `h`.

In path semantics, this is written the following way:

```
f[g] <=> h
```

We call `h` the path of `f` by `g`.

Finding paths is fundamentally a creative problem, unlike normal computation or solving equations using axioms.
There seems to be no algorithm that can find all paths easily and represent them efficiently.
It is quite surprising that this has not been widely recognized,
perhaps because of lack of axioms and the requirement of a deep theory about functions to see why this is the case.

This means path semantics is a way of working with mathematics that appeals to programmers.
It is like a puzzle where the answer is given by mathematics itself,
and you can often guess the solution by using normal programming intuition.

When `h` predicts the property `g` of `f`, it is a *perfect predictor*.
If `f` is total, a solution for `h` either exists or not.
If `f` is partial `h` can have multiple solutions.
A partial function is written `f{[g] b}` which means "arg0 is constrained such that g(arg0) = b".

The brittleness of functions makes it desirable to extend path semantics to probability theory.
Given some knowledge about the input, we would like to predict the likelihood of some property of the output.
Indeed, a path semantical algorithm is defined for this task in the new paper about [probabilistic paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/probabilistic-paths.pdf).

"Normal" paths was discovered long time before existential paths, because the connection was not obvious.
Existential paths are important for type checking in path semantics.
For example, it makes no sense to speak of a list with length -1, written `a: [len] -1`, because
the `len` function does not return any negative number, written `-1: [∃len] true`.
The function `∃len` returns `true` for all output values returned by `len`, and `false` otherwise.

Probabilistic paths builds on [probabilistic existential paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/probabilistic-existential-paths.pdf).
Unlike the discovery of paths before existential paths, the discovery of probabilistic existential paths came first.
This is because it is nearly human impossible to find probabilistic paths without breaking it
into sub-problems and find the probabilistic existential paths first.
After solving the sub-problems and putting it back into an algorithm,
it works almost as if it was magic, including when constraints are negative!

Probabilistic paths are probability distributions, that tells how likely a function is to return a value
from something you know about the input.
It is quite astonishing that it is possible at all to writing down a general algorithm, although it requires solving some sub-problems.

So, now path semantics is taking a serious step into the world of probability theory.

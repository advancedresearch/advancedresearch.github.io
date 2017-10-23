# Perfect Intelligence
by Sven Nilsen, 2017

*Disclaimer: This is based on very recent results from research on path semantics, so I will explore this more in later posts.
It uses a concept that is kind of hard to explain so be patient.*

In the paper [Universal Existential Paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/universal-existential-paths.pdf)
I created a new concept that requires path semantical sub-type constraints as first class citizens.
To fully explain it, I developed [Domain Constraint Notation](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/domain-constraint-notation.pdf).
This notation can be used seamlessly with [Asymmetric Paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/algebraic-notation-for-asymmetric-paths.pdf)
and [Cross Argument Asymmetric Paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/cross-argument-asymmetric-path-notation.pdf).

Universal existential paths is a function that takes some input constraint on the function domain and
returns a function that gives the output domain:

```
∃f{} : (A -> bool) -> (B -> bool)

f : A -> B
```

The word "universal" stands for the ability to take any domain constraint you want and receive a piece of knowledge
about the output. In some sense, this means that a universal existential paths "understand" the function `f` perfectly.

Now I am going to use the concept of universal existential paths to explain what I think about "perfect intelligence".

What is perfect intelligence? There are many definitions of intelligence. 
The particular kind of intelligence I am talking about here is problem solving.
Problem solving is a field where you have a set of constraints and try to find a solution.

The abstract algorithm (yet to be formalized) that uses universal existential path,
has a unique solution/behavior where worst case performance is equal to best case performance.
In a deep sense this defines a "perfect intelligent" system.

OK, here comes the definition of perfect intelligence:

**If you know `∃f{}` and can arrange sub-type constraints in a such way that gives you a 50% chance
for it to return `true` for some input, then this can be used as a search algorithm that takes `N` steps for `N` number of bits for input of `f`.
The best possible algorithm is optimized for 50% chance, and if this is done perfectly the worst case is `N` steps.
Since best case equals worst case the behavior is unique and therefore "perfect".**

For example: In a binary search algorithm, the data is arranged such that at each step,
the likelihood for the item searched for, is 50% for both left and right branches in the tree.
The future checks are also arranged such that there is 50% chance for moving in either direction.
This patten is also arranged such that the information gained from each step is not lost.
The result is that for a list of `N` items, the number of steps required are `log2(N)`.

A binary search algorithm is an optimal search, assuming the cost of jumping left/right and comparing items is negligable.

In the same way binary search is optimal, the concept of perfect intelligence for problem solving
is about arranging sub-type constraints such that the change of the existential path to return `true`
is 50%. On the next step, another sub-type constraint is prepared to make the change 50%,
and so on until the sub-type constraint describes two values of the type.
At the last step, if the existential path returns `true`, then one knows one has the right value,
and if it returns `false`, one knows it must be the other value.

The reason this is not formalized yet is because of the difficulty to express this idea in a formal language.

It says that a perfect intelligent system is capable of solving any problem in the same complexity class
as verifying the answer, which is simply computing the output of `f` using the solution as input.

When you compute a function, the optimal way is to take `N` steps for `N` number of input bits.
At each step, the computer decides between two directions to go.

Notice that the perfect intelligent problem solver also takes `N` steps for `N` number of bits.
This means it performs a kind of computation, but instead of answering "what is the output of this input" like normal computation,
it answers "what input satisfies this output".

You might be familiar with this major open problem in computer science:

```
P = NP
```

So far, nobody have been able to prove or disprove this theorem.

If perfect intelligence exists for any problem defined by `f`, then not only it means `P = NP`,
but that the time complexity for finding solutions is exactly `O(N)` where `N` is number of bits for input of `f`!

However, this only works if computing with the universal existential path and jumping around in memory is negligable.

This behavior corresponds to looking up a value in a table by an address of `N` bits.
A perfect intelligent computational oracle can be constructed by finding `∃f{}`
then optimize for 50% chance arrangements of sub-type constraints for searching.
It means that the oracle operates with `O(1)` complexity internally,
because the input of the oracle is the output of `f` and time complexity internally depends only on `f`'s input.

This is kind of weird, since computational oracles by definition have time complexity `O(1)`.

**Perfect intelligence defines the internal nature of computational oracles!**

I mentioned earlier that the universal existential path "knows" the function it describes "perfectly".
It is kind of an equivalent representation of the function itself.
The construction of this knowledge is transfering the complexity of the function into a "black box" oracle.
As the algorithm learns more and more about the function,
it can approximate the oracle better and better, until it is optimal.

Of course, finding such oracles depends on the complexity of finding `∃f{}`
plus the complexity of path semantics, type theory, probability theory and theorem proving!
There is no known perfect algorithm for any of those things!

This leads to a kind of paradox of intelligence.
Since perfect intelligence is a behavior for a particular formalized problem expressed as a function `f`,
if you want to solve perfect intelligence perfectly, you would need to formalize `∃f{}` for any `f`,
path semantics, type theory, probability theory and theorem proving as a function `f2`.
If you want to solve the formalization of solving perfect intelligence perfectly,
you need a new function `f3` and so on.

So, by figuring out how to create perfect intelligence,
you would also be able to solve all the goals of path semantics, understand type theory completely,
master probability theory and become the best theorem prover in the world in one go!

There is only one problem: As far as we know, the number of bits required to understand path semantics completely
seem to be infinite. Perfect intelligence could be practical on a subset of all path semantics,
but it would take infinitely long time to solve problems that are concerning all of path semantics simultaniously!

As you might have guessed already, this is extremely hard.
Another approach is to solve perfect intelligence for some simple functions
and then build on them to generalize to more and more problems.

For example, for the `sin` function:

```
∃sin{}

x' = sin(x)
```

`∃sin{}` represents a function that behaves such that, if we give it some constraints to use on `x`,
then there exists a function that tells whether there exists a value of `x` that returns `x'`.
Even for a such simple function, there is no easy way to solve `∃sin{}` entirely,
so we need to be creative and make some approximations.

The `sin` function is periodic with intervals of `2π`.
If we use a range constraint that exceeds this interval, we can replace it with a normal existential path:

```
∀k { ∃sin{range(k, k+2π)} <=> ∃sin }

∃sin <=> range_inclusive

range := \(a, b) = \(x) = (x >= a) && (x < b)
range_inclusive := \(a, b) = \(x) = (x >= a) && (x <= b)
```

Another type of constraint is `x` being equal to some value,
but this sub-existential path is just `x' = sin(x)`, so that is easy to solve:

```
∀k { ∃sin{(= k)} <=> check_sin(k) }

check_sin := \(k) = \(x) = x == sin(k)
```

A range can be contracted to a single point,
so with some work we might figure out how to interpolate between those constraints.
I suggest working through `∃sin{range(k, k+π)}`, `∃sin{range(k, k+π/2)}` and generalize.

Assuming that we solved this for contracting a range constraint to a point,
we can use the following trick: Encode any other constraint in terms of ranges!
Each range is transformed into an inclusive range by the sub-existential path,
then you take the union of the transformed ranges to get a sub-existential path for any constraint.
We have made a good approximation to `∃sin{}`!

All functions of time (e.g. signal processing) can be approximated by using a Fourier transformation.
Perhaps it is possible to use `∃sin{}` and `∃cos{}` to find `∃fourier(f){}`?
I do not know yet if this works, but let us assume this for now.
This would mean it is possible to approximate `∃f{}` where `f` describes a signal.

OK, so now you need a machine learning algorithm that learns how to split up search using a constraint `g`
such that it rougly gets 50% likelihood of `∃f{g}` returning `true` recursively.
Sounds easy, right?
I have no idea how to do this yet, but it could also be no need for any machine learning and doing basic range and split search.

However, if this can be done, then you can feed the search algorithm a function `f`,
it does a Fourier transform, and then you give it some output of `f` as `x'` and it will return a range for `x` that gives `x'`.
The longer the algorithm runs, the more accurate the search will be.
If there are no solutions, this can be detected by the first step in the search,
by checking the whole domain whether a solution exists at all.

In theory, if you are using `f64` precision, then a perfect intelligent search would take roughly 64 iterations before you have a practically accurate solution.
You can check the answer by feeding the solution to `f` and compare with the output you wanted.
This is within the same complexity class as checking the solution, which is quite mind blowing.

A such algorithm would be the closest thing possible to a computational oracle.
The ideal behavior of a such system is unique, which is why I call it a definition of "perfect intelligence".

Does it work? Is it possible? Who knows. I might also have done a mistake somewhere.
There could also be problems when generalizing to higher dimensions,
which could require "smoothing out" the co-domain of function `f` or else `∃f{}` have no meaning.
We will see what this new direction brings.

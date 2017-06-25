# New Progress on Existential Paths
by Sven Nilsen, 2017

In the [last blog post about existential paths](http://blog.piston.rs/2017/04/23/existential-paths/),
I told you how this discovery could allow the future development of a type checker for path semantics.
In this post I will summary what has happened since then.

If you do not know what path semantics is about, see [Illustrated History of Path Semantics with Stick Figures](https://github.com/bvssvni/path_semantics/blob/master/papers-wip/history-of-path-semantics-illustrated.pdf).

Path semantics is a generalization of the toolbox of type theory and logic that grounds meaning in functions.
It is a powerful and precise way of reasoning, to solve problems, come up with new definitions and prove theorems.

For example, assume you have a function `f` that takes some input of type `A` and returns some output of the same type:

```
f: A -> A
```

If I ask you "what do you know about `f`?" or "how do you measure what you know about `f`?",
most people can not give me an answer, because the standard toolbox of type theory and logic
does not give you hints of what to look for.
In order to understand what mathematicians are doing, you need to observe what mathematicians do and imitate them.
This problem, that there is no way to express where such ideas come from,
makes it very hard to learn mathematics, because you need to spend a lot of time reading and learning.

Path semantics is a new way of writing mathematics that automatically gives you goals.

For example, if you have a function `g`:

```
g: A -> B
```

You can write:

```
f[g] <=> ?
```

The question mark represents a set of functions that predicts the property `g` computed by `f`.
This is called the "path" of `f` by `g`.
For most functions, no such path exists, but sometimes it does and this knowledge is very useful.

For example, when concatening two lists, you get a new list with length by adding each input list:

```
concat[len] <=> add
```

So, if you only need to know the length of the new list, you can compute it faster:

```
\(a, b) = len(a) + len(b)
```

However, if you have a function `avg` that computes the average, there is no way
to know what the average of the concatenated list will be from the average of each input list:

```
concat[avg] <=> {}
```

So, you can not write down a faster way of computing the length of the new list,
since there is no algorithm that can do that. The algorithm does not exist!
The reason for this is just an integrated part of reality, like space and time.
Yet, there is an exact structure of this behavior, called "path semantics".

With the standard toolbox of type theory and logic, you can express all statements that
are valid path semantics, but unfortunately you can also express infinitely many other things
that have no meaning.
Functions are a very central part of modern computer science,
so we would like express these relations in a way that has clearly assigned and formal *meaning*.
Path semantics generalizes functional notation in a way that serves this purpose.

The problem is that path semantics is so powerful that checking proofs for consistency is very hard.
You can use a proof assistant, e.g. Idris or Coq, by translating path semantics into equations.
However, Idris and Coq does not know what is interesting to prove things about.
We would like to work with path semantical notation and make the computer automatically prove useful things.

A new kind of path, called "existential path", can make this possible:

```
∃f: A -> bool
```

For every function `f`, there is an existential path `∃f`, which tells whether `f` outputs some value.
It turns out that this transformation is very important when checking for consistency.

For example:

```
a: (> 2)

(> 2): nat -> bool
```

This means the number `a` is greater than 2.
A such statement can only have meaning if there exists some value of `a` such that it is greater than 2.
How do we know that a such value exists?
By using the existential path, of course!

```
∃(> 2) <=> true_1
```

Some numbers are greater than 2, so sometimes `(> 2)` returns `true`.
Some numbers are less or equal to 2, so sometimes `(> 2)` return `false`.
Since this is both `true` and `false`, the existential path `∃(> 2)` is `true_1`.

```
true: [true_1] true
```

This can be checked by simply evaluating `true_1(true) == true`, which is `true` (OK).

Here is another example:

```
a: (< 0)

(< 0): nat -> bool
```

There are no natural numbers that are less than 0, so `(< 0)` never returns `true`.
All natural numbers are greater or equal to 0, so `(< 0)` always returns `false`.
Since this is just `false`, the existential path `∃(< 0)` is `not`.

```
∃(< 0) <=> not
```

This means there is no valid value for `a`, and this will be reported by the type checker as a type error.

```
true: [not] true
```

Evaluating `not(true) == true` gives us `false`, so this is a type error.

The existential path does the type checking for us!
There is only one problem left: Finding existential paths!

In two new papers, [Existential Path of Function Composition](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/existential-path-of-function-composition.pdf) and
[Existential Path of If-Expression](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/existential-path-of-if-expression.pdf)
I started on the foundation for solving this problem.

Function composition and if-expressions are the most important building blocks in simple programming languages.
With if-expressions, it is possible to create boolean functions.
With function composition, it is possible to analyze functions used in a specific context.

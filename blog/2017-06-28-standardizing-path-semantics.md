# Standardizing Path Semantics
by Sven Nilsen, 2017

[Path semantics](https://github.com/advancedresearch/path_semantics) is a new way of reasoning about mathematics and software
that transforms seamlessly between programming and theorem proving.
It goes beyond dependently types and offers new insight into advanced mathematics.

Path semantics focuses theorem proving around the following 3 concepts:

- Functions
- Paths
- Existential Paths

I have now started to standardize functions for path semantics such that people can share proofs and become more productive
with the notation.

- [Alphabetic List of Functions](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/alphabetic-list-of-functions.pdf)
- [Alphabetic List of Paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/alphabetic-list-of-paths.pdf)
- [Alphabetic List of Existential Paths](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/alphabetic-list-of-existential-paths.pdf)

Path semantics was developed to make it quicker and easier for people without mathematical experience
to get the hands on advanced mathematics.
Unlike traditional mathematics, where searching for equations is very difficult,
path semantics offers a new expressive notation that can be organized as dictionaries of functions.

- The notation helps splitting up the problem into smaller sub-problems
- Those smaller sub-problems can often be expressed as computable functions
- When people do theorem proving, they can look up functions to save themselves from mental work
- Checking proofs for consistency depends on finding functions for all parts of the proof
- Expressiveness scales arbitrarily to modern functional programming and beyond
- Results of proofs can be reused to find new functions to enable more powerful proofs
- Using functions to compress knowledge is very efficient in both space and time

Path semantics exploits the fact that many useful mathematical equations share a similar structure:

```
g(f(a, b)) = h(g(a), g(b))
```

Such equations appear when you have a function `f` which operate on objects with a property `g` you want to predict.

In path semantics, this is written the following way:

```
f[g] <=> h
```

We call `h` the path of `f` by `g`.

If you have a function `g : A -> bool` you can use it to define a sub-type of `A`:

```
a : [g] true
```

To check the consistency of this statement, one must find the existential path of `g`:

```
true : [∃g] true
```

Repeating this process:

```
true : [∃∃g] true
```

Every computable (halting) function has only one of two double existential paths: `true_1` or `id`.
Therefore, one can terminate the search after one or two steps and use hard coded knowledge instead.

Path semantics offers similar functionality to dependently types but without the limitations that
follows from encoding information into the type:

```
concat(a : [len] na, b : [len] nb) -> [len] na + nb { ... }
```

This can also be expressed as:

```
concat[len] <=> add
```

Since this is the exact same information used to describe commonly used equations,
it makes it easy to transform from programming to equations and back.

Path semantics offset precise way of reasoning about partial functions and contractions:

```
div{(¬= 0), (¬= 0)}[unit ⨯ unit -> (¬= 0)] <=> true_1
```

The above states that if we know have `a / b` and neither `a` or `b` is zero, then we know the result is non-zero.
A `unit` function returns an empty type which is used to demonstrate that the arguments are irrelevant,
once we already know they are non-zero.


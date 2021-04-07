# A Better Fixpoint Combinator
by Sven Nilsen, 2020

In lambda calculus, there is no direct way for a function to call itself recursively,
since the identity of the function is anonymous.

For example, the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number):

```rust
f(x) = if x == 0 {0} else if x == 1 {1} else {f(x-1) + f(x-2)}
```

Assume that this was defined as a lambda:

```rust
f := \(x) = ...
```

How would you define this function as a recursive definition of the Fibonacci sequence?

There is one obvious trick one can use: Make the function take an argument that is "itself".

```rust
f := \(f, x) = if x == 0 {0} else if x == 1 {1} else {f(f, x-1) + f(f, x-2)}

println(f(f, 6)) // Prints `8`
```

Notice that this requires calling the function with itself as first argument.

Ideally, one would like to write this:

```rust
f := \(f, x) = if x == 0 {0} else if x == 1 {1} else {f(x-1) + f(x-2)}
```

There is a trick: A fixpoint combinator is a higher order function that makes it possible
to transform a function taking itself as argument into function that does not require an argument to itself.

The [Y-combinator](https://en.wikipedia.org/wiki/Fixed-point_combinator) is the most famous one.

```rust
y := \(f) = {
    g := \(x) = f(x(x))
    g(g)
}

f := \(f) = \(x) = if x == 0 {0} else if x == 1 {1} else {f(x-1) + f(x-2)}

f := y(f)

println(f(6)) // Prints `8`
```

The problem is that in languages with eager evaluation,
`x(x)` never terminates.

Let's try another combinator, calling this Y-combinator for "Y2":

```rust
y2 := \(f) = {
    g := \(x) = f(x)
    g(g)
}

f := \(f) = \(x) = if x == 0 {0} else if x == 1 {1} else {
    f := y2(f) // Create function for recursion.
    f(x-1) + f(x-2)
}

f := y2(f)

println(f(6)) // Prints `8`
```

Apparently, this works just as fine.

Now, is it perfect? No!

Why do you need to create the function for recursion *inside the function declaration*?

In the [Standard Dictionary of Path Semantics](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/alphabetic-list-of-functions.pdf),
there is an "sc" fixpoint combinator for that:

```rust
sc := \(sc, f) = \(n) = f(sc(sc, f), n)

f := \(f, n) = if n == 0 {0} else if n == 1 {1} else {f(n-1) + f(n-2)}

f := sc(sc, f)

println(f(6)) // Prints `8`
```

One difference between the "sc" combinator and the Y-kinds of combinators,
is that "sc" takes itself as argument.

You can not achieve this with the "Y2" combinator because it can not call itself.
The "sc" combinator calls itself with itself, such that it can call `f` with the `f's self`.

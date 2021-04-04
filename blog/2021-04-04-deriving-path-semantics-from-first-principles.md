# Deriving Path Semantics from First Principles
by Sven Nilsen, 2021

In this blog post I will describe how to arrive at [Path Semantics](https://github.com/advancedresearch/path_semantics) from first principles.

A [first principle](https://en.wikipedia.org/wiki/First_principle) is a basic proposition or assumption that can not be deduced from any other proposition or assumption.

How do we find first principles?

To find first principles, we need to know *what we are looking for*.

What are we looking for?

We want to find out what type systems are supposed to be doing.

There are many type systems out there, but what they all have in common are two behaviors:

1. Look up functions
2. Report errors

Maybe there is a trade-off between these two behaviors.
A type system might be very good at looking up functions, but bad at reporting errors and vice versa.

Let us focus on looking up functions first and see what happens.

Assume you have the following code:

`a + b`

You want to look up the function `+` that computes the value of the expression.

One way to do this, is to pass `a` and `b` to some function which purpose is to return a function that can be used to add these objects.

Here is some pseudocode for how that might look like:

```rust
fn how_to_add_something(a: any, b: any) -> res[fn(any, any) -> any] {
    if typeof(a) == "number" && typeof(b) == "number" {return ok(add_two_numbers)}
    else {return err("Could not figure out how to add something")}
}
```

This simple "type system" 1) looks up a function and 2) reports an error when some function is not found.

One problem with this type system is that it is extremely inefficient.

For every time we want to add two objects, we have to call `how_to_add_something`.

Another problem with this type system is that when you see `a + b`, you can not reason about it until you know exactly what `a` and `b` are.

What most programming languages do, is to make an important assumption:

*Every operation depends only on the type of arguments and the output type can be predicted from input types.*

So, using this assumption, `how_to_add_something` might be modified to something like this:

```rust
fn how_to_add_something(a: type, b: type) -> res[(type, fn(any, any) -> any)] {
    if a == "number" && b == "number" {return ok(("number", add_two_numbers))}
    else {return err("Could not figure out how to add something")}
}
```

The assumption that we used improved efficiency and reasoning.

Now, what if we want to generalise reasoning to not just include types, but anything that might be reasoned about?

To do this, there is a mathematical equation:

```
g(f(x, y)) = h(g(x), g(y))
```

This means, the `g` property of `f` can be predicted using `h` and the `g` properties of the arguments `x` and `y`.

For example, the type of something:

```
typeof(f(x, y)) = h(typeof(x), typeof(y))
```

In the case of numbers and addition:

```
typeof(add(x, y)) = h("number", "number") // Since `x` and `y` are numbers.

h = \(_, _) = "number" // `h` returns the type "number".
```

That is all!

In Path Semantical notation, one writes the equation `g(f(x, y)) = h(g(x), g(y))` as following:

```
f[g] <=> h
```

This is called a "symmetric normal path".

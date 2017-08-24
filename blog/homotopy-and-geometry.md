# Homotopy and Geometry
by Sven Nilsen, 2017

One thing I have been thinking about for a while is how to create an efficient language for constructing geometric objects.
This area of research is useful e.g. in procedurally generated content for game engines.
It is also critical aspect in studying the foundations of artificial intelligence for automated engineering.

In this post I will discuss a very promising idea that builds on overlapping topics of
homotopy and path semantics in the form of [homotopy sub-types](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/homotopy-sub-types.pdf).

Constructing geometric objects is hard because:

1. The objects we want to create are complex (the world is complex)
2. The part of the human brain that processes geometry can not speak (non-verbal expression)
3. The mathematical form is close to obvious/tautological (true by construction)

The combination of these 3 things makes it very hard to build good computer tools that help people to construct objects.
It is easy to design tools for a narrow domain or for people that already are able to express themselves geometrically.
There is a reason many people are not good at drawing or designing.

One obvious thing is that since we live in a complex and colorful world,
the things we find interesting are also complex.
Nobody wants to just create a circle, because a circle does not resemble many things in our environment.
We want to create things that are close enough to real world objects to serve as substitute in communication.

The part of the brain that processes geometry is not good at verbalizing the geometric ideas.
To do this we use rulers and circles, but there is almost none bidirectional feedback between the intuition we use
and the numeric forms of measurements.
Without graphical feedback it is almost impossible to iterate on a design.

Mathematical solvers are good at things that are not obvious or tautological.
For example, solving puzzles or designing by constraints are domains where a computer can assist more easily.
The type checker in a programming language is a typical example where the computer is of good help for
programmers to create software.
If you have a list of rules to follow and some expression that need to satisfy the rules,
then a solver is the right tool to create interactive feedback.

The problem is that we often have no idea what "rules" there are behind a e.g. a flower.
When observing and learning from the real world, we can figure out the rules bit by bit.
Usually there are some rules there, but they are not universally present or true at all times.
Real world objects can break down or be reassembled into new objects.

Instead of leaving this challenge as a mystery, I will now start from a complete different viewpoint.
Then I will build ideas from the bottom up until you start seeing the connection with geometry.

The concept of [homotopy](https://en.wikipedia.org/wiki/Homotopy) is about deforming shapes into other shapes.
[Homotopy Type Theory](https://en.wikipedia.org/wiki/Homotopy_type_theory) is a recent advancement in the last decade
using the intuition behind such deformations to reason about topological problems and theorem proving.
One fundamental idea is the connection between type theory and spaces.

In path semantics, I study sub-types defined by functions, such that even functions can have sub-types.
These sub-types describe how functions behave.
This information can be used for theorem proving.

This means that a homotopy, from a path semantics perspective, is really about a particular kind of functions.

For example, a line can be thought of a higher order function that constructs a function of type `Real -> Point`:

```
line : (Point, Point) -> (Real -> Point)
```

One can think of a line as a deformation of one point onto another.

```
line(a, b)(0) = a
line(a, b)(1) = b
```

When looking up values of `line(a, b)(x)` where `x` is between 0 and 1, one gets all points that are at the line.

It turns out that these functions have very nice properties that makes geometrical ideas easier to express.
More, it fits together with Rust dynamic trait model such that one can create high performance dynamic behavior.

OK, so one might think this is quite obvious that such functions can be constructed,
and hard to understand why this form is interesting.

Here is another example, where I make up an imaginary function `flower`:

```
flower : Real -> Point
```

Why should not a flower be a function of the same type as a line?
When looking up values of `flower(x)` where `x` is between 0 and 1, one gets all points that are on the flower.
In some sense, the flower "is" the function, even thought it is not a real flower, but an expressed aspect of it.

You see both objects, something simple as a line and something complex as a flower,
can be expressed in a similar way, without referring to concrete measurements.

This is what I mean by creating an "efficient language of geometry".
The problem of constructing a flower is reduced to constructing a function with some desirable properties.

A flower is not a homotopy, unless it is drawn without lifting the pencil from the paper.
This means that homotopy only plays a significant role in constructing the building blocks for geometry,
and this restrictuion is relaxed for complex objects.

Still, the connection between homotopy and basic geometric shapes is very important.

For example, all points that lie inside a circle can be generated by 2 coordinates: An angle and a radius.

```
circle : [Real; 2] -> Point
```

In practice it is common to generate a circle using homotopy,
because the code is naturally easier to express when the homotopy constraint is satisfied:

```
circle := \(t: [Real; 2) = [radius * t[1] * cos(t[0] * PI2), radius * t[1] * sin(t[0] * PI2)]
```

Notice that when using this algorithm to generate a circle,
the neighbor input values give neighbor output values.
So, the algorithm encodes a "secret homotopy" that feel natural to use.

One can normalize the input such that it is between 0 and 1, such that 360 degrees is angle 1 (normalized).
The output does not need to be normalized; it keeps the geometric shape.
Input is normalized only to make it easier to reason about the function.

Therefore, one can really say that such functions are constructions of the geometry they describe.
Instead of thinking "the natural algorithm of a basic geometric object is a homotopy" one starts to think
"homotopy gives a natural algorithm for a basic geometric object".

Path semantics is a very powerful framework for reasoning about functions.
A staggering observation is how directly applicable path semantics become for these algorithms.

For example, guess what the existential path of `circle` is?

An existential path is a function that tells which outputs are returned by another function.
In path semantics this is written `∃circle` for the function `circle`.

```
∃circle : Point -> bool

∃circle := \([x, y]: Point) = x^2 + y^2 <= radius^2
```

This is the inequality describing a circle that everybody learns in math classes!

What I did above is to prove that the homotopy algorithm constructs a circle using path semantics.
No matter how big computer you build, you can never prove this point by point.
You have to show the equivalence of the algorithms since they describe infinite sets.

However, I have not proved this using a formal system of rules,
but relying on the intuition of path semantics for what functions do and relate to each other.
The semantics is formal, but the mathematical rules are too complex to be written down upfront.
Perhaps you can prove it using some definition of real numbers, but for construction is probably a waste of time.
This is an example where mathematical intuition is important to formalize,
while the rules are not important at all.

OK, so this thing about circles might seem obvious? Is there really something new here?

There are 3 things that you do not learn from practicing programming with circles:

1. The algorithm generating points on a circle is naturally a homotopy
2. The existential path of the algorithm give the inequality for a circle
3. One can use the notation of path semantics to reason about circles

For example, if I want to express what points are generated by the upper right corner of unit square, I can write:

```
∃circle{[(>= 0.5), (>= 0.5)]} := \([x, y]: Point) = x^2 + y^2 <= radius^2 && x >= 0 && y >= 0
```

This is standard path semantics; using an existential path with domain constraints.
There is no need to develop a new language for reasoning specifically about geometry,
because the language of homotopy makes path semantical notation directly applicable.

Now, this might sound too good to be true, right?

Actually, one reason this approach is very promising, is that working with higher order functions is convenient
in a programming language like Rust.
There is no need to develop a new language that allows dynamic behavior,
because all we need already exists in Rust!

For example, similar types to these might be sufficient:

```rust
Arc<Fn([f64; 2]) -> [f64; 3]> // processes a single point at a time
Arc<Fn(&[[f64; 2]], &mut [[f64; 3]]> // built-in parallelism
```

Such types can be constructed from an AST (e.g. using enums).
This means that one gets a lot of flexibility at runtime for a reasonable trade-off in performance.
I like the `Arc<Fn>` type because it allows a closure to be cloned, plus it supports multi-threading.

The AST could be sufficient for tools to do proper reflection and introspection,
such that it works seamlessly with the graphical interaction of the design process.

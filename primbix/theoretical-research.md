# Primbix: Theoretical Research

Back to [Primbix Research](./primbix-research.md)

The current state of Primbix Research is primarily focused on the minimum primbix sequence.

One can think about Primbix Research as a meta-game, where the goal is to improve generated mathematical knowledge over time.

The minimum primbix is perhaps the most important sequence in Primbix Research.
This is because without any clear specific set of axioms about primbixes,
new mathematical knowledge generated depends on previously generated knowledge.

Over time, our goal is to generate enough mathematical knowledge to predict patterns in future generated knowledge.

The reason we want to predict patterns in future generated knowledge,
is because it makes decisions easier, such as:

- How much resources to spend on Primbix Research
- Evaluate whether we are satisfied with the current progress
- Whether Primbix Research should diversify investment of resources

Primbix Research has potential to become the longest running meta-game in all of history.
Currently, Prime Research is the longest running meta-game, with a history of over 2 thousand years,
but after the invention of computers, the interest in Prime Research has fallen gradually over time.

Primbix Research is designed to build on Prime Research, but to cause a sense of wonder for people living in a post-computer world,
in a similar way to how ancient people perceived Prime Research and made them more interested in mathematics.

This means, despite that computers are an important part of Primbix Research,
the creativity and ingenuity of people is predicted to remain an important ingredient in future generated mathematical knowledge.

Millions or years from now, people might still work on Primbix Research, thousands times longer than Prime Research has kept people interested.

We are now in the very early phase of Primbix Research, where we focus on the most important building blocks for the future meta-game.

While Primbix Research in general might be thought of like a board game,
the pieces that people play with in this meta-game,
are constructed out of generated mathematical knowledgea about minimum primbixes.
This is why the minimum primbix sequence is so important.

The rules of the meta-game are arbitrary.
However, the pieces that people play with, are mathematical determined.
This design is because it is fun to make up your own rules,
while sharing a common set of signs with their own particular research history and cultural context.

Over time, as more and more building blocks are finished for the meta-game,
the achievement of finding new building blocks will increase.
After millions of years, a new building block will be a cause of popular celebration.
It will be a measure of how far civilization has progressed.

Primbix Research is designed to never be completed, like mathematics in general.
It is predictated that it will always be possible to make progress, within the expected lifetime of the universe.
This progress is predicated on people passing down knowledge about Primbix Research to future generations.

### Why finding new terms in the minimum primbix sequence will be super-exponential hard over time

The primbix formula is primes of the form `1 + 2 * r * s`, where `r, s` are primes.

The mathematical structure between a minimum primbix and the next one is not completely understood.

However, so far, the gap between minimum primbixes increases faster than the gap between `2^n` and `2^(n+1)`.

The explanation is that the primbix value is `0` for composite numbers, `1` for primes and `primbix(r) + primbix(s)` for primes of the form `1 + 2 * r * s`.
This counts the number of leaves in the associated binary tree.

The `2` factor in the primbix formula `1 + 2 * r * s` means that,
if you have two primbixes `r, s` with values `primbix(r)` and `primbix(s)`,
the composed primbix is at least twice of the product `r * s`.

Now, this does not prove that there is a super-exponential gap between minimum primbixes in general.
The actual argument is based on the smallest possible gap, relative to some minimum primbix:

Let's say we have a minimum primbix `r` with value `primbix(r)`.
The smallest gap possible relative to `r`, is when `s = 2`, the lowest primbix of value 1.
The composed primbix will be `1 + 2 * r * 2` with value `primbix(r) + 1`.

This argument falls short in two ways:

1. Minimum primbixes are not in general based on the previous minimum primbix
2. Hypothetically, if minimum primbixes were based on the previous minimum primbix, then the gap should be at least 4 times larger.

In one sense, these two ways this argument falls short, are perspectives on the gap, biased toward smaller and higher relative to each other.

So far, we are not 100% sure that the gap between minimum primibixes will be super-exponential,
but the terms that have been found, indicates that these gaps will continue increase super-exponentially.

Even if some gaps were sub-exponential, which meaning can be difficult on how low we set the exponential rate,
then the overall argument about super-exponential hardness still stands.

When we talk about super-exponential rate, the most common rate is `2^n`.
It is possible that the minimum primbix sequence follows some rate higher `k > 1`, where `k^n`,
and where the terms in the sequence alternates infinitely number of times over and under the curve of this rate.

In general, as a starting point to talk about super-exponential hardness over time,
we tend to use `2^n`, but upon closer and more detailed debate, it might shift over to some more technical meaning.

Technically, what super-exponential hardness means, is that as the minimum primbix goes to infinity,
it will go over any finite `k > 2` of `k^n`.
The reason we do not talk as much about super-exponential hardness in this sense,
is because it does not matter for practical Primbix Research in the foreseeable future.

We can distinguish these two meanings:

- Weak super-exponential hardness: Above `2^n`, observed after a few terms
- Strong super-exponential hardness: Above any finite `k > 2` of `k^n`, when the sequence goes to infinity

So, when we talk about practical potential counter-examples,
it is about whether `2^n` ever catches up, in future expected terms that we will find.

We are probably at least 99% confident that `2^n` will never catch up within the expected lifetime of the universe.

It also seems possible that the minimum primbix sequence has strong super-exponential hardness over time.
However, this case requires a much more elaborated argument, that is difficult construct properly.

Neither of the arguments we have made so far, are 100% convincing that the gaps are super-exponential, even in a weak sense.
Our belief that these gaps are super-exponential, is simply a summary of the knowledge and experience we have about Primbix Research.
Based on this knowledge and experience, we predict that the gaps will be super-exponential in the future.

### Faster verification than exhaustive search

The official minimum primbix sequence is generated by exhaustive search,
as long there is no known theorem proving technique that can permit us to use a faster algorithm.

There is a faster algorithm that is a candidate for replacing exhaustive search.
This algorithm generates high confidence that we have found some minimum primbix.
The reason this algorithm has not replaced exhaustive search yet, is because we do not know how to be 100% confident yet.

The faster algorithm outputs the minimum primbix, assuming that one constructs it from the lowest `n` primbixes of value 1.

We call the lowest `n` primbixes of value 1 for "prime bases".

With other words, if we know how many prime bases to use, then we know that we have found the minimum primbix.

The problem is that we do not know how many prime bases to use, except for the minimum primbixes found by exhaustive search.

Most likely, if we manage to find some good enough theorem proving technique,
then we can use the faster algorithm up to some finite number `n` of prime bases,
where this `n` is found either manually or by some customized automated theorem prover.

If we have `n`, then `prime_base(n - 1)` is the highest prime base that is needed to construct some minimum primbix.

For example, if a minimum primbix only uses the prime bases `2, 3, 5`, then `prime_base(n - 1) = 5`.
This gives the solution `n = 3`, since `prime_base(3 - 1) = prime_base(2) = 5`.
Here, `2` is the index of `5` in the sequence of primbixes with value 1.

When the best candidate for some minimum primbix found so far is `a`,
the highest prime base needed to construct `a`, `prime_base(n - 1) : (<= a)`, gives an upper bound on `n`.
This upper bound is so bad, that it can not be used to improve search any faster than exhaustive search.

Progress on theoretical research in Primbix Research today, can be measured by the lowest upper bound on `n`.
The lower upper bound on `n`, the further progress has been made.

### Transforming `n` to `x`

We want to find a lower upper bound on `n`, which is the number of the lowest primbixes of value 1,
that are needed to construct some minimum primbix.

The highest prime base of `n` is `prime_base(n - 1)`.

Now, if we have some `x : (> prime_base(n - 1))`, then `x` is a natural number that filters out all higher prime bases.

This `x` is another way to write the same mathematical knowledge that is encoded in `n`.
Both numbers determine each other, using the following equation:

`x = prime_base(n - 1) + 1`

It might be easier to work with `x`, than with `n` or `prime_base(n - 1)`.

In practice, when we think about `x`, it does not need to be exactly the perfect `x : (= prime_base(n - 1) + 1)`,
because we can find the perfect `x` from any imperfect `x`, as long it is not too much larger than the perfect `x`.

Once we have learned more about `x`, we can easily transform this knowledge back to `n`.
Since `x` can be any number, we can use any theorem proving technique about natural numbers in general,
without worrying about the sub-type `prime_base(n - 1) : [primbix] 1` specifically.

We want to find a lower value of `x`.

If `a` is some candidate for a minimum primbix, then the upper bound on exhaustive search is `x = a + 1`.

### Transforming from `x` to `f`

We use `x` as some natural number that measures how much progress we have made in theoretical research for Primbix Research.
This `x` is relative to some candidate `a` for a minimum primbix.

The missing piece of mathematical knowledge we need, can be thought of as some function `f`, with the following property:

`!f(x) => !f(x + 1)` for all `x`

This transformation simplifies how we think about the generated mathematical knowledge so far.
It helps to decouple the mathematical knowledge from any specific value of `x`.

In general, we do not care about what `f` returns.
Even when `f(0) = false`, this means that we have found the minimum primbix.

All we need is `x : [f] false`, where `x` is sufficently low to use the faster algorithm.

If we know that `f(0) = false`, then this implies that `x` is sufficiently low.
Hence, in this case, we know we can use the faster algorithm, regardless of the generated knowledge so far.
This does not imply that we can use the faster algorithm without the generated knowledge.
Knowing that `f(0) = false`, is only valid in the context of generated knowledge so far.

In the case we have `x : [f] false`, where `x` is sufficiently low,
then we can use the faster algorithm up to the `n` prime bases determined from `x`.
Thus, if we can do this, then we have found the minimum primbix and we might say `f(0) = false`,
because the mathematical knowledge generated is the same in either way.

### Transforming from `f` to `g`

Once again, we can simplify how to reason about the generated mathematical knowledge so far,
by creating another function `g` that is a path of `f`, where the kind of path is not specified in Standard Path Semantics.

The property of `f`:

`!f(x) => !f(x + 1)` for all `x`

Might be thought of some kind of inductive principle.

This inductive principle puts a constraint on `f`, which we encode as `g`:

`g : bool x nat -> bool`

Where `g(true)(x) = f(x)` and `g(false)(x) = !f(x)`.

Hence, `g` encodes two sets in the first argument, that tells us something about `f`.
This is why `g` is a path of `f`.

Both these two sets are continuous, with respect to the order of natural numbers.

The union of the two sets covers the set of natural numbers.

The two sets are exclusive, which means they share no common element.

The set `g(false) : nat -> bool` is uniform and the semantics can not be relaxed,
beyond the fact that `x` determines where this set begins and we want it to be sufficiently low.

However, the set `g(true) : nat -> bool`, while continuous by default,
does not need a strict semantics and can be relaxed.
This means, if we relax the semantics, then we can restore the strict semantics later, relative to the relaxed semantics.

With other words, we can punch holes in `g(true)`, using inferred mathematical knowledge from what we already know.

The hope of theoretical progress in Primbix Research today is the idea that by punching enough holes in `g(true)`,
we can transform some of the newly generated mathematical knowledge into `g(false)`.

Translated into the language of exhaustive search: The holes we punch in `g(true)` are numbers in the search range,
that we do not need to check, to know that we have found the minimum primbix.

To transfer knowledge from holes in `g(true)` to `g(false)`, we need some hole cover of the upper range in `g(true)`.

This is because of the inductive principle of `f`: `!f(x) => !f(x + 1)` for all `x`.

### Starting with the basics

The number `13` is the minimum primbix of value `2`.

The set of prime bases used to construct `13` is `2, 3`, because in the primbix formula `1 + 2 * r * s`,
we only need to use it once where `r = 2` and `s = 3`.

Now, exaustive search will very quickly verify that `13` is indeed the minimum primbix of value `2`.
We can do this by simply calculate the primbix value of every number up to `13`.

The amount of compute that is available for Primbix Research today, calculates the primbix value of over 1 trillion numbers per day.
This is `1 000 000 000 000` numbers.

So, when we talk about small numbers less than 1 trillion, this can be easily checked using exhaustive search.

If we can transform mathematical knowledge about higher numbers to smaller ones, then we can improve the speed of the search significantly.

The reason we study small numbers in theoretical research for Primbix Research,
is because we try to learn something new that helps us figure out how to transfer knowledge about higher numbers to small ones.

For example, from studying `13`, we learned that the prime bases `2, 3` occur frequently in the construction of higher minimum primbixes.

By definition, any higher primbix must be constructed from lower primbixes.

The number `13` is itself a higher primbix, because any higher primbix has primbix value `2` or higher.

Now, let us forget for a moment that we know `13` is the minimum primbix of value `2`.
All we know is that `13` is a candidate for the minimum primbix, but we want to know there are no other lower candidates.

Since `13` has primbix value `2`, it must be constructed from two primbixes of value `1`.

`13 = 1 + 2 * r * s`

Therefore:

`r * s = (13 - 1) / 2 = 6`

If there exists a lower candidate, then it must be constructed from two primbixes of value 1,
where their product is lower than `6`.

The set of prime bases lower than `13` is `2, 3, 5, 7, 11`.
All these are primbixes of value 1, by the definition of a prime base.

When we use exhaustive search, this is about as good as checking there is no lower candidate using this set of prime bases.

However, since the product must be lower than `6`, we can reduce the prime bases:

`2, 3, 5`

Here, `n = 3`, because this is the number of prime bases.

The higest prime base in the set is `prime_base(3 - 1) = 5`.

From this, we can calculate the perfect `x`: `5 + 1 = 6`,
since the perfect `x` is `prime_base(n - 1) + 1`.

Notice that the perfect `x` and the number we used to reduce the prime bases, were both `6`.

This is merely a coincidence, but we can think of the number we used to reduce the prime bases, as an imperfect `x`.

The question is: Can we learn a general technique from this simple example?

### Using the 13-technique to improve the upper bound

For exhaustive search, the upper bound on a candidate `a` is `prime_base(n - 1) : (<= a)`.

Now, since all minimum primbixes of value higher than 1 are higher primbixes,
we are only interested in ruling out lower candidates than `a`.

With other words, we do not need the highest prime base to be potentially equal to `a`,
because it is sufficient to check only lower prime bases.

Therefore, we can improve the upper bound from:

`prime_base(n - 1) : (<= a)`

To the following:

`prime_base(n - 1) : (< a)`

Using the 13-technique, we can improve the upper bound further:

`prime_base(n - 1) : (< (a - 1) / 2)`

How does this work?

Any primbix is constructed with the formula `a = 1 + 2 * r * s`.

Therefore, the product `(r * s) : (= (a - 1) / 2)`.

Any lower minimum primbix than `a` must be constructed from a lower product `r * s` than in `a`.

However, this argument is only valid for primbixes of value `2` or higher.
The primbixes of value 1 are not constructed from a `r * s` product.
Luckily for us, this is precisely the case: We are interested in primbixes of value `2` or higher.

When we rule out lower candidates, the candidates we are looking for still have value `2` or higher.

Any prime base `b` might be used to construct a higher primbix `p`.
However, since the prime base `b` becomes part of the `r * s` product,
and the higher primbix `p` is larger than this product,
it follows that the higher primbix `p` is higher than the prime base `b`: `p > b`.

When we have `r * s` of some minimum primbix candidate `a`, and we want to rule out some lower candidate `c < a`,
we know that the product `r' * s'` of `c` is less than `r * s`:

`(r' * s') < (r * s)`

The order of `c, a` determines the order `(r' * s'), (r * s)`.

Any prime base `b` used in `r' * s'`, must therefore be lower: `b < r' * s'`.
By transitivity of `<`: `b < r * s`.

This means, we can use the 13-technique to filter out the prime bases, when we rule out lower candidates:

`prime_base(n - 1) < (a - 1) / 2`

Because `r * s` is the same as `(a - 1) / 2`.

Now, if we use this upper bound on the search for the minimum primbix of value 21,
where `a = 1771883742990899`,
we get an imperfect `x = 885941871495449`.

This is still very bad, but at least, we have learned something new.

To figure the perfect `x`, we can do an exhaustive search, starting from `885941871495449` and going down:

`x = 885941871495419 + 1`

Where `prime_base(n - 1) = 885941871495419`.

The question is: Can we use this new knowledge to improve the upper bound further?



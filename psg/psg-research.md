# Prime Symmetric Goldbach Research

The Goldbach conjecture states (from the perspecive of Bertrand's postulate) that for `n > 1`:

```
2n = a + b
```

Some solution exists, where `a, b` are primes.

By introducing a 1-or-prime `p`:

```
2n = (a + p) + (b - p)
```

The Prime Symmetric Goldbach (PSG) conjecture states that for `n > 1 & (n % 6) == 0`:

```
n = a + p = b - p
```

Some solution exists, where `a, b` are primes and `p` is a 1-or-prime.

For more information, see [Prime Symmetric Goldbach](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/prime-symmetric-goldbach.pdf) paper.

### Connection to the twin prime conjecture and Polignac's conjecture

The twin prime conjecture states that there are infinity many solutions for:

```
a + 2 = b
```

Where `a, b` are primes.

The twin prime conjecture is a special case of Polignac's conjecture.

Polignac's conjecture states that there are infinitey many solutions for:

```
a + 2*p = b
```

Where `a, b` are prime, with no constraints on `p` (except being some natural number).
Hence, when `p = 1`, this produces the twin prime conjecture.

Since there are infinitely many multiples of 6,
the PSG conjecture implies that there are infinitely many solutions for:

```
a + 2*p = b
```

Where `a, b` are primes and `p` is a 1-or-prime.

The solutions for PSG are two sets:

1. The twin prime conjecture `a + 2 = b`, where `a, b` are primes
2. A couple prime conjecture `a + 2*p = b`, where `a, b, p` are primes

At least one of these sets must be infinite.

Polignac's conjecture implies both sets are infinite.

Notice that 2), the prime `p` does not need to be fixed for all `a, b` by the PSG conjecture.
There could be a finite number of solutions for any `p`, yet together they make up an infinite set.

### Progress done by the Polymath group

In August 2014, the Polymath group, seeking the proof of the twin prime conjecture,
showed that if the generalized Elliott–Halberstam conjecture is proven,
one can show the existence of infinitely many pairs of consecutive primes that differ by at most 6 and as such they are either twin, cousin or sexy primes.

- Twin: `a + 2 = b`
- Cousin: `a + 4 = a + 2*2 = b`
- Sexy: `a + 6 = a + 2*3 = b`

This result means that at least one of these sets are infinite and therefore either
the twin prime conjective holds or the couple prime conjecture `a + 2*p = b` holds (since `2` and `3` are primes),
but only in the context where the Elliott–Halberstam conjecture holds.

This is stronger than what is implied by PSG, but weaker than what is implied by Polignac's conjecture.

For more information, see [wiki](https://michaelnielsen.org/polymath/index.php?title=Bounded_gaps_between_primes) entry on the Polymath project.

### The M3 conjecture and a path toward proving the twin prime conjecture

The "Minus 3" conjecture, or M3 conjecture for short, states that there is a sequence containing 1 and all primes except 2 and 3.
This sequence is given by the order of extending `n` with new values of `p` as `n` grows, such that `a = n - p` and `b = n + p`.
Each number is listed exactly once in the sequence, so only new numbers are added.
The same constraints as for the PSG conjecture holds.

Since this sequence does not contain 2 or 2, the M3 conjecture implies that there are no cousin or sexy primes in base 6 (when `(n % 6) == 0`).

In base 6, every prime number greater than 3 must end in 1 or 5, and every twin prime must be a pairing of numbers ending in 5 and 1 consecutively.
Therefore, all twin primes occur centered around base 6, except the first twin pair `3, 5`.

Now, if there are infinite pairs that differ by at most 6 centered on base 6,
then because there are none cousin or sexy primes by M3, the twin prime conjecture must be true.

However, the result from the Polymath group only holds for natural numbers in general and not for pairs centered on base 6.

If the Polymath result is modified to hold for pairs centered on base 6,
then one gets the following:

```
PSG & M3 & modified-Polymath8-GEH => twin-prime
```

This might be a viable path toward proving the twin prime conjecture, but this in turn depends on PSG and M3.

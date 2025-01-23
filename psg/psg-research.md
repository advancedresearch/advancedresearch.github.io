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

This results means that at least one of these sets are infinite and therefore either
the twin prime conjective holds or the couple prime conjecture `a + 2*p = b` holds (since `2` and `3` are primes),
but only in the context where the Elliott–Halberstam conjecture holds.

This is stronger than what is implied by PSG, but weaker than what is implied by Polignac's conjecture.

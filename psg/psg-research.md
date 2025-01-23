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

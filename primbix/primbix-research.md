# Primbix Research

Primbixes are primes of the form:

    1 + 2 * r * s

Where `r, s` are primes.

Since `r, s` are primes, they might also be primbixes, which in turn contains new primes.
The data structure one gets from a primbix this way, is a binary tree.

A primbix value counts the number of leaves in the associated binary tree.

- Composite numbers have primbix value 0
- Primes have primbix value 1 or higher
- Primbixes have primbix value 2 or higher

For more information, see [Primbix](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/primbix.pdf) paper.

### Minimum Primbix Sequence

The minimum primbix sequence is a sequence that contains the smallest natural numbers of increasing primbix values.
Due to the difficulty of theorem proving about this sequence, very little is currently known about it.

There is an ongoing effort to search for more terms in the minimum primbix sequence and these are the results so far:

```
0: 0
2: 1
13: 2
53: 3
317: 4
3407: 5
8243: 6
49459: 7
197837: 8
1187023: 9
18314419: 10
112006043: 11
491325707: 12
2047857083: 13
9869296583: 14
107478087043: 15
460785710279: 16
5075320359359: 17
```

107478087043 was found 13.06.2025 19:13 UTC.  
460785710279 was found 15.08.2025 18:48 UTC.  
5075320359359 was found 22.08.2025 18:29 UTC.

The minimum primbix with value 18 is above 5 075 000 000 000.

If you are interested in helping to reduce this bound, then you can take a look at [this example code](https://github.com/advancedresearch/algexenotation/blob/main/examples/primbix.rs).

There are currently 16 dedicated CPU cores that work on this search 24/7.

- [Minimum Primbixes per Billion up to Level 17](./level-14.md)

To make collaboration easier, the search is split into 100 billions, with the highest minimum primbix found so far in this range:

```
[5 000 000 000 000, 5 100 000 000 000): 17, 5 075 320 359 359
[5 100 000 000 000, 5 200 000 000 000): <--- 1 CPU

[6 000 000 000 000, 6 100 000 000 000): 17, 6 000 531 711 407
[6 100 000 000 000, 6 200 000 000 000): <--- 1 CPU

[7 000 000 000 000, 7 100 000 000 000): 16, 7 000 424 176 979
[7 100 000 000 000, 7 200 000 000 000): <--- 1 CPU

[8 000 000 000 000, 8 100 000 000 000): 17, 8 035 923 619 523
[8 100 000 000 000, 8 200 000 000 000): <--- 1 CPU

[9 000 000 000 000, 9 100 000 000 000): 16, 9 018 509 790 299
[9 100 000 000 000, 9 200 000 000 000): <--- 1 CPU

[10 000 000 000 000, 10 100 000 000 000): 15, 10 019 150 962 643
[10 100 000 000 000, 10 200 000 000 000): <--- 1 CPU
```

### Use of Primbixes in Galactic Communication

Primbixes have ideal properties for communication between two advanced civilization at galactic scale.
This is because it is a simple definition that might be discovered independently by two advanced civilizations without previously being in contact.
Sharing primbixes might be a way to establish common ground under first contact,
plus that the interest to keep in touch, despite other difficulties of getting in contact such as extreme large distances,
can be kept up by collaboration on primbix research.

### Use of Primbixes to get children interested in mathematics

Primes have fascinated mathematicians for over 2 millenia.
However, with the invention of computers, primes are no longer as exciting they once appeared to be.
Both efficient algorithms and theoretical advancements means we know a lot more about primes now than in the past.

Primbixes increases the difficulty compared to primes,
in a way where the advantage of computers can be balanced with human intuition and creativity.
A new discovery by a supercomputer can be used in combination with human knowledge that can compete with each other using secrets.

This way, primbixes are designed to let people become engaged as a hobby,
in addition to expert researchers working in this field to advance human knowledge.

### List of open problems

- Is the minimum primbix sequence infinite?
- Can all primes be held in a single infinite-primbix?
- Does the set of all primes held by the minimum primbix sequence cover all primes?

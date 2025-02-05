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
```

The minimum primbix with value 15 is above 19 007 000 000 and less or equal to 370 837 765 219 (which has primbix value 15).

If you are interested in helping to reduce this bound, then you can take a look at [this example code](https://github.com/advancedresearch/algexenotation/blob/main/examples/primbix.rs).

There are currently 16 dedicated CPU cores that work on this search 24/7.

To make collaboration easier, the search is split into billions, with the highest minimum primbix found so far in this range:

```
[19 000 000 000, 19 200 000 000): 12, 19 152 460 403
[20 000 000 000, 20 000 240 000): 8, 20 000 050 319
[21 000 000 000, 21 060 000 000): 11, 21 053 058 659
[22 000 000 000, 23 000 000 000): 13, 22 610 227 247
[23 000 000 000, 23 000 080 000): 7, 23 000 045 063
[24 000 000 000, 24 000 080 000): 7, 24 000 006 203
[25 000 000 000, 25 500 000 000): 13, 25 048 480 819 <-- 8 CPUs
[26 000 000 000, 26 008 080 000): 10, 26 007 356 003
[27 000 000 000, 27 008 160 000): 9, 27 001 785 523
[28 000 000 000, 28 008 352 000): 10, 28 001 796 863
[29 000 000 000, 29 001 040 000): 8, 29 000 202 467
[30 000 000 000, 30 001 040 000): 8, 30 000 184 283
[31 000 000 000, 31 001 056 000): 9, 31 000 906 907
[32 000 000 000, 32 002 608 000): 9, 32 000 689 283
[33 000 000 000, 33 000 160 000): 9, 33 000 002 939
[34 000 000 000, 34 000 080 000): 6, 34 000 033 819
[35 000 000 000, 35 005 200 000): 10, 35 003 957 147
[36 000 000 000, 36 000 200 000): 7, 36 000 120 019
[37 000 000 000, 37 000 200 000): 6, 37 000 040 387 <-- 8 CPUs
[38 000 000 000, 38 000 160 000): 8, 38 000 043 143
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

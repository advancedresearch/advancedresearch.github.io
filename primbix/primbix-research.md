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

The minimum primbix with value 15 is above 31 001 056 000 and less or equal to 176 297 511 683 (which has primbix value 15).  
This is based on the assumption that the next minimum primbix is at least twice as large as the previous one (this has not been proven yet).

If you are interested in helping to reduce this bound, then you can take a look at [this example code](https://github.com/advancedresearch/algexenotation/blob/main/examples/primbix.rs).

There are currently 16 dedicated CPU cores that work on this search 24/7.

To make collaboration easier, the search is split into billions, with the highest minimum primbix found so far in this range:

```
[19 000 000 000, 20 000 000 000): 13, 19 523 734 163 (done)
[20 000 000 000, 21 000 000 000): 14, 20 221 905 659 (done)
[21 000 000 000, 22 000 000 000): 13, 21 063 309 803 (done)
[22 000 000 000, 23 000 000 000): 13, 22 610 227 247 (done)
[23 000 000 000, 24 000 000 000): 13, 23 460 041 299 (done)
[24 000 000 000, 25 000 000 000): 14, 24 270 247 487 (done)
[25 000 000 000, 26 000 000 000): 13, 25 048 480 819 (done)
[26 000 000 000, 27 000 000 000): 14, 26 311 925 327 (done)
[27 000 000 000, 28 000 000 000): 13, 27 487 985 267 (done)
[28 000 000 000, 29 000 000 000): 14, 28 031 439 523 (done)
[29 000 000 000, 30 000 000 000): 14, 29 582 478 467 (done)
[30 000 000 000, 31 000 000 000): 12, 30 093 953 423 (done)
[31 000 000 000, 31 001 056 000): 9, 31 000 906 907 <--- 8 CPUs
[32 000 000 000, 33 000 000 000): 13, 32 255 212 643 (done)
[33 000 000 000, 34 000 000 000): 13, 33 047 302 427 (done)
[34 000 000 000, 35 000 080 000): 13, 34 140 614 999 (done)
[35 000 000 000, 36 000 000 000): 13, 35 208 863 003 (done)
[36 000 000 000, 37 000 000 000): 13, 36 409 064 987 (done)
[37 000 000 000, 38 000 000 000): 13, 37 211 568 323 (done)
[38 000 000 000, 39 000 000 000): 13, 38 158 619 903 (done)
[39 000 000 000, 40 000 000 000): 13, 39 637 041 707 (done)
[40 000 000 000, 41 000 000 000): 13, 40 095 103 943 (done)
[41 000 000 000, 42 000 000 000): 13, 41 448 637 739 (done)
[42 000 000 000, 43 000 000 000): 12, 42 181 308 083 (done)
[43 000 000 000, 44 000 000 000): <--- 8 CPUs
[44 000 000 000, 45 000 000 000): 13, 44 037 007 667 (done)
[45 000 000 000, 46 000 000 000): 12, 45 018 664 253 (done)
[46 000 000 000, 47 000 000 000): <--- 2 CPUs
[47 000 000 000, 48 000 000 000): <--- 2 CPUs
[48 000 000 000, 49 000 000 000): <--- 2 CPUs
[49 000 000 000, 50 000 000 000): <--- 2 CPUs
[50 000 000 000, 51 000 000 000): 14, 50 593 408 883 (done)
[51 000 000 000, 51 200 000 000): 13, 51 049 692 047

[60 000 000 000, 60 000 100 000): 7, 60 000 082 343

[70 000 000 000, 70 000 100 000): 6, 70 000 028 507

[80 000 000 000, 80 000 100 000): 7, 80 000 001 227

[90 000 000 000, 90 000 100 000): 7, 90 000 043 499

[100 000 000 000, 100 000 100 000): 5, 100 000 024 547

[110 000 000 000, 110 000 100 000): 10, 110 000 011 007

[120 000 000 000, 120 000 100 000): 6, 120 000 012 239
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

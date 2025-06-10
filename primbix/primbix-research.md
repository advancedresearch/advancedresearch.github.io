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

The minimum primbix with value 15 is above 43 000 000 000 and less or equal to 176 297 511 683 (which has primbix value 15).

If you are interested in helping to reduce this bound, then you can take a look at [this example code](https://github.com/advancedresearch/algexenotation/blob/main/examples/primbix.rs).

There are currently 16 dedicated CPU cores that work on this search 24/7.

To make collaboration easier, the search is split into billions, with the highest minimum primbix found so far in this range:

```
[0, 1 000 000 000): 12, 491 325 707 (done)
[1 000 000 000, 2 000 000 000): 12, 1 027 760 099 (done)
[2 000 000 000, 3 000 000 000): 13, 2 047 857 083 (done)
[3 000 000 000, 4 000 000 000): 13, 3 410 832 779 (done)
[4 000 000 000, 5 000 000 000): 13, 4 671 906 587 (done)
[5 000 000 000, 6 000 000 000): 12, 5 093 513 903 (done)
[6 000 000 000, 7 000 000 000): 13, 6 379 061 603 (done)
[7 000 000 000, 8 000 000 000): 13, 7 696 274 087 (done)
[8 000 000 000, 9 000 000 000): 13, 8 412 786 287 (done)
[9 000 000 000, 10 000 000 000): 14, 9 869 296 583 (done)
[10 000 000 000, 11 000 000 000): 13, 10 089 537 083 (done)
[11 000 000 000, 12 000 000 000): 13, 11 046 928 547 (done)
[12 000 000 000, 13 000 000 000): 13, 12 239 338 733 (done)
[13 000 000 000, 14 000 000 000): 13, 13 259 283 623 (done)
[14 000 000 000, 15 000 000 000): 13, 14 584 191 563 (done)
[15 000 000 000, 16 000 000 000): 13, 15 008 809 763 (done)
[16 000 000 000, 17 000 000 000): 13, 16 001 431 163 (done)
[17 000 000 000, 18 000 000 000): 14, 17 913 014 507 (done)
[18 000 000 000, 19 000 000 000): 12, 18 099 433 019 (done)
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
[31 000 000 000, 32 000 000 000): 13, 31 195 729 667 (done)
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
[46 000 000 000, 47 000 000 000): 14, 46 850 738 027 (done)
[47 000 000 000, 48 000 000 000): 13, 47 033 867 723 (done)
[48 000 000 000, 49 000 000 000): 13, 48 658 282 187 (done)
[49 000 000 000, 50 000 000 000): 13, 49 021 505 459 (done)
[50 000 000 000, 51 000 000 000): 14, 50 593 408 883 (done)
[51 000 000 000, 52 000 000 000): 13, 51 568 193 639 (done)
[52 000 000 000, 53 000 000 000): 13, 52 082 576 867 (done)
[53 000 000 000, 54 000 000 000): 13, 53 152 075 343 (done)
[54 000 000 000, 55 000 000 000): 13, 54 047 183 899 (done)
[55 000 000 000, 56 000 000 000): 13, 55 026 244 187 (done)
[56 000 000 000, 57 000 000 000): 13, 56 147 597 147 (done)
[57 000 000 000, 58 000 000 000): 13, 57 088 349 387 (done)
[58 000 000 000, 59 000 000 000): 14, 58 868 152 667 (done)
[59 000 000 000, 60 000 000 000): 13, 59 228 779 067 (done)
[60 000 000 000, 61 000 000 000): 13, 60 152 410 523 (done)
[61 000 000 000, 62 000 000 000): 14, 61 189 469 203 (done)
[62 000 000 000, 63 000 000 000): 13, 62 127 795 263 (done)
[63 000 000 000, 64 000 000 000): 14, 63 298 441 103 (done)
[64 000 000 000, 65 000 000 000): 14, 64 068 721 103 (done)
[65 000 000 000, 66 000 000 000): 14, 65 858 650 787 (done)
[66 000 000 000, 67 000 000 000): 14, 66 203 883 203 (done)
[67 000 000 000, 68 000 000 000): 14, 67 123 528 523 (done)
[68 000 000 000, 69 000 000 000): 14, 68 912 114 963 (done)
[69 000 000 000, 70 000 000 000): 14, 69 091 969 307 (done)
[70 000 000 000, 71 000 000 000): 14, 70 990 350 323 (done)
[71 000 000 000, 72 000 000 000): 13, 71 313 184 379 (done)
[72 000 000 000, 73 000 000 000): 13, 72 242 159 723 (done)
[73 000 000 000, 74 000 000 000): 14, 73 195 221 503 (done)
[74 000 000 000, 75 000 000 000): 14, 74 283 398 879 (done)
[75 000 000 000, 76 000 000 000): 13, 75 399 157 403 (done)
[76 000 000 000, 77 000 000 000): 13, 76 030 752 719 (done)
[77 000 000 000, 78 000 000 000): 13, 77 291 624 843 (done)
[78 000 000 000, 79 000 000 000): 13, 78 605 486 423 (done)
[79 000 000 000, 80 000 000 000): 13, 79 034 299 307 (done)
[80 000 000 000, 81 000 000 000): 13, 80 184 069 863 (done)
[81 000 000 000, 82 000 000 000): 13, 81 101 693 579 (done)
[82 000 000 000, 83 000 000 000): 13, 82 415 464 819 (done)
[83 000 000 000, 84 000 000 000): 13, 83 530 471 373 (done)
[84 000 000 000, 85 000 000 000): 13, 84 123 658 643 (done)
[85 000 000 000, 86 000 000 000): 13, 85 315 438 739 (done)
[86 000 000 000, 87 000 000 000): 14, 86 024 144 483 (done)
[87 000 000 000, 88 000 000 000): 13, 87 160 741 979 (done)
[88 000 000 000, 89 000 000 000): 13, 88 391 170 619 (done)
[89 000 000 000, 90 000 000 000): 13, 89 448 484 991 (done)
[90 000 000 000, 91 000 000 000): 12, 90 000 568 499 (done)
[91 000 000 000, 92 000 000 000): 13, 91 008 196 427 (done)
[92 000 000 000, 93 000 000 000): 13, 92 168 614 739 (done)
[93 000 000 000, 94 000 000 000): 13, 93 175 427 339 (done)
[94 000 000 000, 95 000 000 000): 14, 94 503 472 643 (done)
[95 000 000 000, 96 000 000 000): 13, 95 004 006 827 (done)
[96 000 000 000, 97 000 000 000): <--- 8 CPUs

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

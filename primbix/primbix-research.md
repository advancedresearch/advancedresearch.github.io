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

The minimum primbix with value 18 is above 7 900 000 000 000 and below or equal to 12 279 094 871 663 (which has primbix value 18).

If you are interested in helping to reduce this bound, then you can take a look at [this example code](https://github.com/advancedresearch/algexenotation/blob/main/examples/primbix.rs).

There are currently 16 dedicated CPU cores that work on this search 24/7.

- [Minimum Primbixes per Billion up to Level 17](./level-17.md)

To make collaboration easier, the search is split into 100 billions, with the highest minimum primbix found so far in this range:

```
[5 000 000 000 000, 5 100 000 000 000): 17, 5 075 320 359 359
[5 100 000 000 000, 5 200 000 000 000): 16, 5 192 828 199 059
[5 200 000 000 000, 5 300 000 000 000): 17, 5 250 348 266 447
[5 300 000 000 000, 5 400 000 000 000): 16, 5 306 837 484 379
[5 400 000 000 000, 5 500 000 000 000): 16, 5 411 676 151 103
[5 500 000 000 000, 5 600 000 000 000): 16, 5 509 910 014 859
[5 600 000 000 000, 5 700 000 000 000): 16, 5 623 660 701 707
[5 700 000 000 000, 5 800 000 000 000): 16, 5 738 446 226 659
[5 800 000 000 000, 5 900 000 000 000): 16, 5 810 259 532 523
[5 900 000 000 000, 6 000 000 000 000): 16, 5 970 675 841 019
[6 000 000 000 000, 6 100 000 000 000): 17, 6 000 531 711 407
[6 100 000 000 000, 6 200 000 000 000): 17, 6 169 592 401 283
[6 200 000 000 000, 6 300 000 000 000): 16, 6 202 072 686 947
[6 300 000 000 000, 6 400 000 000 000): 16, 6 302 214 026 419
[6 400 000 000 000, 6 500 000 000 000): 17, 6 486 083 735 519
[6 500 000 000 000, 6 600 000 000 000): 17, 6 504 169 709 267
[6 600 000 000 000, 6 700 000 000 000): 16, 6 629 101 791 107
[6 700 000 000 000, 6 800 000 000 000): 16, 6 729 691 846 463
[6 800 000 000 000, 6 900 000 000 000): 16, 6 814 028 708 563
[6 900 000 000 000, 7 000 000 000 000): 16, 6 901 591 761 563
[7 000 000 000 000, 7 100 000 000 000): 16, 7 000 424 176 979
[7 100 000 000 000, 7 200 000 000 000): 15, 7 112 747 013 899
[7 200 000 000 000, 7 300 000 000 000): 16, 7 280 067 685 823
[7 300 000 000 000, 7 400 000 000 000): 16, 7 305 170 903 923
[7 400 000 000 000, 7 500 000 000 000): 17, 7 469 188 000 223
[7 500 000 000 000, 7 600 000 000 000): 16, 7 500 396 956 939
[7 600 000 000 000, 7 700 000 000 000): 15, 7 607 964 662 483
[7 700 000 000 000, 7 800 000 000 000): 16, 7 766 604 995 483
[7 800 000 000 000, 7 900 000 000 000): 16, 7 827 996 478 859
[7 900 000 000 000, 8 000 000 000 000): <--- 1 CPU
[8 000 000 000 000, 8 100 000 000 000): 17, 8 035 923 619 523
[8 100 000 000 000, 8 200 000 000 000): 16, 8 177 439 634 499
[8 200 000 000 000, 8 300 000 000 000): 16, 8 293 993 398 623
[8 300 000 000 000, 8 400 000 000 000): 16, 8 376 095 432 219
[8 400 000 000 000, 8 500 000 000 000): 16, 8 478 391 052 987
[8 500 000 000 000, 8 600 000 000 000): 16, 8 582 465 376 803
[8 600 000 000 000, 8 700 000 000 000): 16, 8 600 502 436 523
[8 700 000 000 000, 8 800 000 000 000): 16, 8 703 103 586 399
[8 800 000 000 000, 8 900 000 000 000): 16, 8 815 751 553 803
[8 900 000 000 000, 9 000 000 000 000): <--- 1 CPU
[9 000 000 000 000, 9 100 000 000 000): 16, 9 018 509 790 299
[9 100 000 000 000, 9 200 000 000 000): 16, 9 168 620 371 763
[9 200 000 000 000, 9 300 000 000 000): 17, 9 265 990 640 339
[9 300 000 000 000, 9 400 000 000 000): 17, 9 301 168 121 387
[9 400 000 000 000, 9 500 000 000 000): 16, 9 404 520 262 463
[9 500 000 000 000, 9 600 000 000 000): 16, 9 501 084 416 003
[9 600 000 000 000, 9 700 000 000 000): 17, 9 696 876 319 979
[9 700 000 000 000, 9 800 000 000 000): 15, 9 719 399 066 987
[9 800 000 000 000, 9 900 000 000 000): 16, 9 810 941 720 939
[9 900 000 000 000, 10 000 000 000 000): <--- 1 CPU
[10 000 000 000 000, 10 100 000 000 000): 15, 10 019 150 962 643
[10 100 000 000 000, 10 200 000 000 000): 17, 10 155 303 877 007
[10 200 000 000 000, 10 300 000 000 000): 16, 10 231 921 512 467
[10 300 000 000 000, 10 400 000 000 000): 15, 10 300 318 172 003
[10 400 000 000 000, 10 500 000 000 000): 16, 10 427 916 600 659
[10 500 000 000 000, 10 600 000 000 000): 16, 10 514 132 253 707
[10 600 000 000 000, 10 700 000 000 000): 17, 10 613 055 347 387
[10 700 000 000 000, 10 800 000 000 000): 17, 10 708 009 897 787
[10 800 000 000 000, 10 900 000 000 000): 17, 10 827 008 955 923
[10 900 000 000 000, 11 000 000 000 000): <--- 1 CPU
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

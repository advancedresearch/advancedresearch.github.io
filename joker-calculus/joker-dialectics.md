# Joker Dialectics

[Back to summary page about Joker Calculus](./summary.md)

Joker Dialects extends Joker Calculus with new operators, used to trace philosophical stances and dynamics:

- combination `+`
- equality `==`
- inequality `!=`
- movement `->`
- recursion `^n`

Based on notation used in the paper [Dialectical Masks: Hegel's Philosophy through the Lens of Joker Calculus](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/dialectical-masks.pdf).

| Expression               | Description                                                       | Philosophers        | Examples |
| ------------------------ | ----------------------------------------------------------------- | ------------------- | -------- |
| 0                        | Platonism/Rationalism/Pure concept                                | Pl, De, Sp, Le, Ka  |          |
| 1                        | Seshatism/Empiricism/Lived experience                             | Ar, Lo, Be, Hume    |          |
| ?0                       | Empirical appearances structures by reason/Intellectual intuition | Ka, Sc2             |          |
| ?1                       | A-priori intuitions/Transcedental poetry/Rational mask            | Ka, Sc1             |          |
| 0 1                      | Synthesized cognition/Fragmentary thinking/Determinate Being      | Ka, Fi, Sc1, He     |          |
| ?1 + 0 -> 0 1 -> ?0      | Criticial philosophy (Kant)                                       | Ka                  |          |
| !0 == 1                  | The thing-in-itself/Noumenon/Ground of Being                      | Ka, Sc2, He         |          |
| 0 == 1                   | Non-dualism                                                       | Sc2, He             | [1](#example-1) |
| !0                       | Not-I                                                             | Fi                  |          |
| !0 -> 0 1                | Negation and sublation                                            | Fi, He              |          |
| 0 -> !0 -> 0 1           | Act of positing                                                   | Fi                  |          |
| ?0 ?1                    | Irony as philosophy                                               | Sc1                 |          |
| (?0 ?1 + 0 1)^n          | Infinite oscillation (Schlegel)                                   | Sc1                 |          |
| 0 1 + ?0                 | Schelling's early philosophy                                      | Sc2                 |          |
| 0 1 -> !0 -> 1           | Schelling's late philosophy                                       | Sc2                 |          |
| 0 != 0                   | Immanent contradiction                                            | He                  |          |
| (0 != 0 -> !0 -> 0 1)^n  | Spirit                                                            | He                  |          |
| ?0 1                     | Absolute knowing                                                  | He                  |          |
| Spirit -> ?0 1           | Negation to reflection                                            | He                  |          |
| Spirit -> ?0 1 -> 0 == 1 | Logic becomes ontology (Hegel)                                    | He                  |          |

| Code  | Philosopher | Born - Died                        |
| ----- | ----------- | ---------------------------------- |
| Pl    | Plato       | 428/427 or 424/423 BC - 348/347 BC |
| Ar    | Aristotle   | 384 BC - 322 BC                    |
| De    | Descartes   | 1596 – 1650                        |
| Sp    | Spinoza     | 1632 – 1677                        |
| Lo    | Locke       | 1632 – 1704                        |
| Le    | Leibniz     | 1646 – 1716                        |
| Hu    | Hume        | 1711 - 1776                        |
| Ka    | Kant        | 1724 – 1804                        |
| Fi    | Fichte      | 1762 – 1814                        |
| He    | Hegel       | 1770 – 1831                        |
| Sc1   | Schlegel    | 1772 - 1829                        |
| Sc2   | Schelling   | 1775 – 1854                        |

### Example 1

Expression:

```text
0 == 1
```

This statement expresses non-dualism, where Platonism (`0`) and Seshatism (`1`) become one.

In Schelling's early philosophy, this means reason and nature are one and the same.

In Hegel's philosophy, this means Logic is the same as Being.

In Path Semantics, Platonism and Seshatism can be viewed as the same thing by viewing
the difference between the two as an internal difference.
An internal difference in philosophy from a path semantical perspective happens in some language.
It is something that can not be distinguished by a non-speaker of the language.
Only speakers of the language know the internal difference.

For example, you generate a random bit vector (a sequence of bits) and decide whether to flip them or not before sending.
The receiver of the bit vector can not tell whether you flipped it or not.
This can be used to hide the knowledge of the flipping operation and use this to control information.

On the other hand, if you have a bit vector where there are more 0s than 1s,
then you can determine whether it has been flipped by counting 0s and compare them to the expected number of 0s.
This is not an internal difference, because it can be distinguished externally by a non-speaker.

The unification of Platonism and Seshatism happens when the knowledge about internal differences are erased.
E.g. an action that does not depend on knowledge of internal difference.

This means, when people live their lives without distinguishing between Platonism and Seshatism,
they are practicing non-dualism.

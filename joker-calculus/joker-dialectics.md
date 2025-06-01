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
| 0                        | Platonism/Rationalism/Pure concept                                | Pl, De, Sp, Le, Ka  | [2](#example-2) |
| 1                        | Seshatism/Empiricism/Lived experience                             | Ar, Lo, Be, Hume    | [5](#example-5) |
| ?0                       | Empirical appearances structures by reason/Intellectual intuition | Ka, Sc2             | [6](#example-6) |
| ?1                       | A-priori intuitions/Transcedental poetry/Rational mask            | Ka, Sc1             | [7](#example-7) |
| 0 1                      | Synthesized cognition/Fragmentary thinking/Determinate Being      | Ka, Fi, Sc1, He     | [8](#example-8) |
| ?1 + 0 -> 0 1 -> ?0      | Criticial philosophy (Kant)                                       | Ka                  | [9](#example-9) |
| !0 == 1                  | The thing-in-itself/Noumenon/Ground of Being                      | Ka, Sc2, He         | [10](#example-10) |
| 0 == 1                   | Non-dualism                                                       | Sc2, He             | [1](#example-1) |
| !0                       | Not-I                                                             | Fi                  | [11](#example-11) |
| !0 -> 0 1                | Negation and sublation                                            | Fi, He              | [12](#example-12) |
| 0 -> !0 -> 0 1           | Act of positing                                                   | Fi                  | [3](#example-3) [4](#example-4) |
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

*Notice! When `0` and `1` are taken as truth values in propositional logic or as natural numbers modeled by the Peano axioms,
then `0 == 1` leads to absurdity (inconsistency by being able to prove `false`).
Absurdity is the strongest sense of contradiction (in a weaker notion of contradiction, two things can contradict without being able to prove `false`).
This problem happens due to treating the two sides as propositionally equal.
One can fix this problem e.g. by using normal paths generated by `not`.
It is possible to unify the two sides in some sense without causing absurdity.*

### Example 2

Expression:

```text
0
```

This statement expresses Platonism, Rationalism or Pure concept.

Usually, philosophers think about this as eternal truths.

In theology, it is common to think about it as something existing outside space and time.

Sometimes, philosophers can treat it as something existing in space only, as embedded geometry.
However, it is also possible to think of geometry as a pure logical theory with axioms and theorems, but without any physical space.
There is an ambiguity in use of language whether logic can be a space or not.
This depends on the interpretation of logic.

Simplified, one can think about `0` as a general notion of space.
This generalized notion of space is not necessarily without time, but it can be.
With other words, `0` is not always in opposition to `1`, but sometimes it can, depending on context.

In Joker Calculus, `0` is authentic in sense of Heidegger, since it does not contain any Jokers after being evaluated in the Closed variant.

### Example 3

Expression:

```text
0 -> !0 -> 0 1
```

Consider the dialectical relationship between rationalism and empiricism in philosophy:

- `0` (Rationalism): Knowledge is grounded purely in reason, independent of sensory experience. Rationalism asserts the primacy of logical and innate concepts as the basis for understanding reality.
- `!0` (Empiricism): Knowledge is derived exclusively from sensory experience. Empiricism rejects innate ideas, emphasizing empirical evidence as the sole foundation of knowledge.
- `0 1` (Transcendental Idealism): The synthesis arises through Kantian transcendental idealism, combining elements of rationalism and empiricism. Knowledge emerges through an interaction of innate cognitive structures (rationalism) and sensory experiences (empiricism).

### Example 4

Expression:

```text
0 -> !0 -> 0 1
```

Consider the dialectical interplay between freedom and determinism:

- `0` (Freedom): Human actions are based on free will, independent of deterministic forces. Individuals possess genuine autonomy and moral responsibility.
- `!0` (Determinism): Human actions are entirely determined by causal factors and external conditions. Freedom is perceived as an illusion, and choices are predetermined.
- `0 1` (Compatibilism): A synthesis emerges through compatibilism, proposing that freedom and determinism coexist. Free will is understood as the capacity to act according to one's internal desires, even within deterministic structures.

### Example 5

Expression:

```text
1
```

This statement expresses Seshatism, Empiricism, or the concept of lived experience.

Usually, philosophers view this as contingent truths grounded in sensory perceptions.

In epistemology, it is common to understand this as knowledge that arises directly from experience, subject to change and revision based on new evidence.

Occasionally, philosophers interpret this concept strictly as empirical facts and observable phenomena within physical reality. However, it can also encompass subjective experiences and individual perceptions that resist purely objective measurement.

Simplified, one can conceive of `1` as a general notion of time or temporality, emphasizing change, process, and concrete events. This temporality may or may not explicitly involve spatial references. Thus, `1` is not necessarily always opposed to 0, though it may sometimes be, depending on context.

In Joker Calculus, `1` represents an authentic mode of existence since it does not contain any Jokers after being evaluated in the Closed variant.

### Example 6

Expression:

```text
?0
```

This expression signifies Empirical Idealism or a state of experience structured by rational concepts.

Philosophically, it typically represents phenomena or appearances that are conditioned by an underlying rational framework or conceptual structure.

In epistemological terms, it can be understood as the empirical content of experience, shaped by a priori categories or mental structures, such as those articulated by Kant.

Occasionally, this is interpreted as reality being encountered through conceptual filters, meaning our direct experience is always mediated by our conceptual understanding.

Simplified, `?0` captures the idea that sensory experience is never purely empirical but inherently influenced by rational or conceptual conditions, making it fundamentally conditional and somewhat dependent on an underlying rational structure.

In Joker Calculus, `?0` represents an inauthentic state due to its dependence on other positions, resulting in persistent unresolved tension or opposition upon evaluation in the Closed variant.

### Example 7

Expression:

```text
?1
```

This expression signifies Transcendental Poetry or a state characterized by intuitive insights or a priori imaginative structures.

Philosophically, it typically represents poetic or creative intuition independent of immediate empirical verification but still grounded in subjective experience.

In aesthetic terms, it can be understood as artistic or poetic imagination operating through spontaneous, intuitive insights rather than empirical evidence or purely logical structures.

Occasionally, this is interpreted as a form of knowledge or insight emerging from creativity or intuition, highlighting the subjective, spontaneous nature of imaginative experiences.

Simplified, `?1` embodies the idea that certain truths or insights are accessible through intuitive, imaginative, or poetic means rather than empirical observation or purely rational argument.

In Joker Calculus, `?1` represents an inauthentic state due to its dependence on other positions, resulting in persistent unresolved tension or opposition upon evaluation in the Closed variant.

### Example 8

Expression:

```text
0 1
```

This expression signifies Hegelian Dialectics, Fragmentary Thinking, or a state of synthesized cognition that integrates both pure conceptual reason and empirical lived experience.

Philosophically, it typically represents the synthesis of rationalist and empiricist traditions, capturing how abstract conceptual structures interact dynamically with concrete experiential data.

In epistemological terms, it can be understood as knowledge that arises from the interplay of abstract reasoning and concrete sensory experience, neither entirely determined by innate concepts nor solely by empirical observation.

Occasionally, this is interpreted as a holistic or dialectical mode of thinking, emphasizing the integration and mutual dependence of theory and practice, universality and particularity.

Simplified, `0 1` embodies the idea that authentic cognition emerges from the creative synthesis of pure reason and experiential diversity, thus maintaining openness rather than closure or unresolved opposition.

In Joker Calculus, `0 1` represents an authentic state since it remains free of Jokers after evaluation in the Closed variant.

### Example 9

Expression:

```text
?1 + 0 -> 0 1 -> ?0
```

This expression encapsulates Kant's critical philosophy, representing the dialectical transition from transcendental intuition and rational concepts toward synthesized knowledge, and ultimately, empirical experience structured by reason.

Philosophically, it begins with the union of transcendental poetic intuition (`?1`) and pure rational concepts (`0`), progressing toward a synthesis (`0 1`) of these elements into structured cognitive judgments.

Epistemologically, this signifies how Kantian cognition combines intuitive and conceptual components, establishing a priori structures that shape empirical phenomena (`?0`).

Occasionally, this is understood as illustrating Kant’s critical method: starting from intuition and reason, forming conceptual synthesis, and finally resulting in structured empirical understanding—highlighting reason’s role in shaping experience.

Simplified, this expression captures Kant’s view that genuine knowledge arises by critically synthesizing intuitive insight and rational concepts, which then structures empirical reality.

In Joker Calculus, the progression demonstrates how intuitive and rational faculties produce synthesized cognitive structures, conditioning empirical phenomena and resulting in an inauthentic yet structurally coherent experiential framework.

### Example 10

Expression:

```text
!0 == 1
```

This expression represents the Thing-in-itself, the Noumenon, or the Ground of Being.

Philosophically, it captures a point of absolute identity between negation and appearance—where what is fundamentally unknowable (`!0`) is equated with the manifold of experience (`1`). This identifies the origin or grounding of appearances in something that cannot itself appear.

In metaphysical terms, it expresses the paradox of a reality that conditions all phenomena yet cannot be directly known. This is the transcendental condition that gives rise to appearances but is not itself an appearance.

Occasionally, this is interpreted as a moment of ontological grounding, where negation does not stand in opposition to something else, but instead coincides with the generative multiplicity of the world.

Simplified, `!0 == 1` captures the insight that the ground of experience is not a separate object but an indeterminate condition that becomes indistinguishable from the flow of empirical reality.

In Joker Calculus, this is a relation of identity between two seemingly opposed positions, revealing a deep structural equivalence that suspends contradiction.

### Example 11

Expression:

```text
!0
```

This expression represents the Not-I in Fichte’s philosophy—the principle of negation or limitation that makes the self-conscious I possible.

Philosophically, !0 stands for the negation of the absolute I (`0`). It is not simply the opposite of the I, but rather a necessary condition for its development. The Not-I introduces resistance, finitude, and differentiation, enabling the I to define and assert itself.

In Fichtean terms, the I posits itself absolutely, but in order to be self-conscious, it must also posit the Not-I—something external or limiting—which becomes the condition for self-awareness and activity.

Occasionally, this is interpreted as the grounding of objectivity or alterity: the world that appears as other is not independent of the I, but co-constituted by its self-limiting act.

Simplified, `!0` expresses the active negation that allows for differentiation, self-consciousness, and relational identity—an essential tension in idealist thought.

In Joker Calculus, `!0` is not an inauthentic negation of `0`, but a productive, generative movement that introduces difference without being reduced to simple opposition.

### Example 12

Expression:

```text
!0 -> 0 1
```

This expression captures the dialectical motion of negation and sublation, as used in both Fichte's and Hegel's philosophies.

Philosophically, `!0` begins as the negation of the I (or of pure concept), an externalization or differentiation that introduces otherness. The transition to `0 1` represents sublation (Aufhebung), the process by which contradiction is overcome and preserved within a higher synthesis.

In Fichte, this captures the dynamic self-positing of the I, which encounters the Not-I as a limit, only to incorporate it into its ongoing striving toward unity and self-realization.

In Hegel, this is the logic of dialectical development itself: contradiction and negation (!0) are not dead ends, but necessary movements toward greater totality and conceptual integration (`0 1`).

Occasionally, this is read as the generative motion of spirit—through opposition, division, and eventual reconciliation, reality unfolds itself in richer structures.

Simplified, `!0 -> 0 1` expresses the essential power of negation to generate synthesis, not by erasing difference, but by preserving and reconfiguring it into a higher form.

In Joker Calculus, this movement illustrates an authentic transformation: from negation to structured openness, without reverting to pure unity or collapsing into contradiction.

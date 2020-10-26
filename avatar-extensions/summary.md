# Avatar Extensions

This page is for organizing all important ideas about Avatar Extension in one place.

[Reading Sequence of papers](https://github.com/advancedresearch/path_semantics/blob/master/sequences.md#avatar-extensions)

### Avatar Logic

Avatar Logic replaces predicates with binary relations with some additional axioms:

```text
p(a, b)         b : p           p(a) = b
p(a, q'(b))     q'(b) : p       p(a) = {q'(_)} ∈ q'(b)
```

This means that `(a, b)` contains all information needed to represent a labeled edge.

```text
p(a) = q'(b)      the `p` property of `a` is `b`
p(a) => q'(b)     the `p` property of `a` has `b`
```

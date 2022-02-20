# Path Semantical Quality

Path Semantical Quality is a partial equivalence relation that lifts biconditions with symbolic distinction.

This page is for organizing all important ideas about quality in one place.

[Paper](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/path-semantical-quality.pdf)

The model of Path Semantical Quality is formalized in [Prop](https://github.com/advancedresearch/prop).

### Notation

A quality between `a` and `b` is written:

```
a ~~ b
```
In Prop, this is written `Q<A, B>`.

### Path Interpretation

A [homotopy path](https://en.wikipedia.org/wiki/Homotopy) is a path between paths such that one path can be deformed into another.

![homotopy path](https://upload.wikimedia.org/wikipedia/commons/7/7e/HomotopySmall.gif)

`a ~~ b` means that there is a path between two paths `a` and `b`.

Notice that there is a slight difference in terminology between "homotopy path" and "path":

- `(a => b) => (a ~~ b)` a homotopy path in univalence foundations (`Hom<A, B>` in Prop)
- `a ~~ b` a path between `a` and `b` (`Q<A, B>` in Prop)

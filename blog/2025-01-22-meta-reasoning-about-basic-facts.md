# Meta-Reasoning about Basic Facts
by Sven Nilsen, 2025

How can we reason correctly about basic facts that we normally assume are correct for all other work otherwise that we engage in?

If we do this wrong, then we risk losing everything we've worked for in the future.
Humanity currently sucks at meta-reasoning about basic facts. Let's improve this!

### Thesis

We *should* (in a particular sense detailed in the argument below) do meta-reasoning about basic facts `a0, a1, a2, ...` combined with `&` using
not stronger than tautological excluded middle `excm(a0)^true, excm(a1)^true, excm(a2)^true, ...` to do meta-reasoning about basic facts properly.

There is an open problem of whether this `excm(a)^true` of a basic fact `a` should be weakened to `excm(!a)^true` (like in Existential Logic where this holds for all propositions).

Notice that this does not mean doing this for all propositions, just propositions that model basic facts.

### Argument

Normally, a basic fact `a`, that is an assumption for all other work, might be thought of as tautology `a^true`.
However, if we reason about tautologies when doing meta-reasoning about basic facts,
then we might arrive at conclusions that depend on the specific choice of basic facts.

With other words, meta-reasoning about basic facts should not depend on any particular choice of basic facts.
Yet, because basic facts are assumed as tautologies, this is hard to avoid.
We have to construct a language isolated from the general language we use when assuming a set of basic facts.

At the same time, one must also understand this isolated language as telling us something about how to do reasoning about basic facts,
without actually containing any of the basic facts we normally assume. At what level of language do we understand this connection?

I argue that, currently, we only understand this connection intuitively and not formally.
We can think of this as two languages, L and M, where L is the language used for meta-reasoning and M is the language normally used.
M is stronger than L, since it contains assumptions of basic facts.

Now, are there some constraints we should put on L? If there are none constraints,
then we run into the trouble of [rule-free logic](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/rule-free-logic.pdf),
which nobody can identify at this moment.
That would put us in a situation where we don't even know what we are talking about.

However, on the other side, if we put too strong constraints on L, then we risk reasoning wrongly (about how to reason about basic facts).
So, L has to be a weak language, but strong enough to give us a clue what we are talking about here.
L does not have to be a unique language, though.

There can be exceptional difficult situations of M that requires specific choices of L to fulfill expectations of correct reasoning.
I am exploiting here that the connection between L and M is intuitive and not formal, so it can be changed by demand.
So, I can say "we *should* do this" at most.

Now, if L and M are constructive, they satisfy constructive logic (IPL = Intuitionistic Propositional Logic).
If we choose a stronger logic, e.g. classical logic, we lose the ability to reason about IPL.
Yet, IPL is not strong enough for meta-reasoning, so I suggest adding
[HOOO EP](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/hooo-exponential-propositions.pdf) axioms.

There are other logics such as orthologic (that does not have constructive implication and is not distribute),
but to get through this argument without getting lost in the weeds, I will just assume we are working in a constructive universe.

From here, there are still some issues, such as whether to use quantifiers of sym-blocks (like in [Hooo](https://github.com/advancedresearch/hooo)).
I regard these issues as design problems and not particularly relevant for the core of my argument.

Anyway, one immediate problem is to prove the following theorem in L:

```
(a1 & a1 -> b) -> (!b -> !a1 | !a2)
```

Under normal reasoning in M, the theorem above holds for all basic facts.

Intuitively, if something is true `!b` that contradicts `b` that is provable from the set of basic facts `a1 & a2`,
then at least one of the basic facts must be wrong.
Either `a1` is wrong, or `a2` is wrong, or both.

The problem is that one can not prove this without adding additional assumptions.

The sense basic facts might be wrong is by assuming them, not due to them necessarily be untrue or false.
This might be a challenge for some people when interpreting the theorems provided by L.

With other words, when correcting a basic fact it might be sometimes removed as assumption.

It is possible to prove the following in L:

```
(a1 & a2 -> b) -> (!b -> !(a1 & a2))
```

By adding assumptions of the excluded middle of the basic facts `a1, a2`, I can prove the following (using [Hooo](https://github.com/advancedresearch/hooo)):

```
fn proof : (a1 & a2 -> b) & excm(a1)^true & excm(a2)^true -> (!b -> !a1 | !a2) {
    use std::pow_modus_tollens;
    use std::hooo_imply;

    x : a1 & a2 -> b;
    y : excm(a1)^true;
    z : excm(a2)^true;

    fn f : (!(a1 & a2) => !a1 | !a2)^(!b & excm(a1) & excm(a2)) {
        use std::or_from_de_morgan;

        x : !b;
        y : excm(a1);
        z : excm(a2);

        lam f : !(a1 & a2) => !a1 | !a2 {
            x2 : !(a1 & a2);

            let r = or_from_de_morgan(x2, y, z) : !a1 | !a2;
            return r;
        }
        return f;
    }

    fn g : a^(b & c & d) & c^true & d^true -> a^b {
        use std::refl;
        use std::tauto_reduce;
        use std::hooo_rev_and;
        use std::pow_transitivity;

        x : a^(b & c & d);
        y : c^true;
        z : d^true;

        // (b & c & d)^b
        let x2 = refl() : b^b;
        let x3 = tauto_reduce(y) : c^b;
        let x4 = tauto_reduce(z) : d^b;
        let x5 = hooo_rev_and(x3, x4) : (c & d)^b;
        let x6 = hooo_rev_and(x2, x5) : (b & c & d)^b;

        let r = pow_transitivity(x6, x) : a^b;
        return r;
    }

    let f2 = g(f, y, z) : (!(a1 & a2) => (!a1 | !a2))^(!b);
    let f3 = hooo_imply(f2) : (!(a1 & a2))^(!b) => (!a1 | !a2)^(!b);

    let x2 = pow_modus_tollens(x) : !b -> !(a1 & a2);
    let r = f3(x2) : !b -> !a1 | !a2;
    return r;
}
```

The benefit of this approach by using tautological excluded middle
is that it is not possible to prove theorems that depend on specific choice of basic facts,
while being able ot prove some theorem that hold for basic facts in general.

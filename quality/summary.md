# Path Semantical Quality

Path Semantical Quality is a tautological congruent partial equivalence relation that lifts biconditions with symbolic distinction.

While Path Semantical Quality is a highly technical topic, the idea is very simple: To enable modeling mathematics in language design.
To new people unfamiliar with Path Semantics, it might seem very surprising that this highly technical definition
is very central to a modern understanding of mathematics.
The research on Path Semantics has resulted in many breakthroughs and deep results,
that gives insights into the nature of existence from a language design perspective.

The theory about Path Semantical Quality is the logical foundation of Path Semantics.
This foundation is famous for being minimalistic in design, while bridging to an enormous body of mathematical knowledge.
For example, Algebra, Set Theory, Group Theory, Category Theory, Homotopy Type Theory, Topology, Avatar Extensions,
interpretation of metaphysical time and quantum behavior.
Basically, everything that people think of as standard mathematics and computation, plus a lot more.

This page is for organizing all important ideas about quality in one place.

The model of Path Semantical Quality is formalized in [Hooo](https://github.com/advancedresearch/hooo) and [Prop](https://github.com/advancedresearch/prop).

### Inside vs Outside Theory and the Logi Circle

![Logi Circle](https://github.com/user-attachments/assets/e25b7bac-d778-43bb-a517-8918f4934264)

- L: Local
- O: Outside 
- G: Global
- I: Inside
- C: Center/Core (the core axiom of Path Semantics)

[Slides of the talk that introduced the Logi Circle](https://github.com/advancedresearch/path_semantics/blob/master/lectures/introduction-to-path-semantics/transcript-of-introduction-to-path-semantics.pdf)

The Local vs Global distinction is well familiar to mathematicians, but the Inside vs Outside distinction was recently developed.

An Inside Theory is some language where unknowns have a model in some grammar.
This means, when copying all information to the Inside Theory,
one can reason about that mathematical object without needing to communicate with the outside world.
The original object can be destroyed without impacting further reasoning.

An Outside Theory contains at least one symbol which is intrinsically unknown.
This means, the language has to interact with the outside world continuously over time to achieve truth.
Any even in the outside world that can influence the language's ability to interact,
might be seen as a threat by the agent that speaks the language using Outside Theory.

This has philosophical consequences for AGI safety:

- Agents who use Inside Theory might accidentally destroy the world,  
  after collecting all information that is need to simulate the world perfectly
- Agents who use Outside Theory might accidentally destroy the world,  
  due perceiving events it can not control as a threat to its own continuous existence

Mathematics as a whole is classified by Inside vs Outside theory, which together with Local vs Global perspectives gives the Logi Circle:
Some authors, e.g. Kent Palmer (PhD), calls the Inside vs Outside theory distinction for "Nilsen theories" (e.g. [this paper](https://www.academia.edu/45073917/Asymmetries_of_Complementary_Nilsen_Theories)), after Sven Nilsen, the founder of Path Semantics and the first person who used this distinction to classical mathematical language design.

### Path Interpretation

A [homotopy path](https://en.wikipedia.org/wiki/Homotopy) is a path between paths such that one path can be deformed into another.

![homotopy path](https://upload.wikimedia.org/wikipedia/commons/7/7e/HomotopySmall.gif)

For simplicity's sake, one can avoid using the words "point" and "homotopy" and instead talk only about paths.  
So, there are only paths and paths between paths.  

For example, when one says `a`, this can be a path.  
The kind of path that `a` is, depends on its mathematical properties.  

Our intuition of paths gives a nice semantics to mathematical proofs.
Therefore, this idea of paths is very important in mathematical language design.

The name "Path Semantics" comes from interpreting semantics from the perspective of paths for various domains.
Path Semantics is a new field and discipline being establised to bridge all domains of human knowledge,
connecting all domains to one central theory: The fundamental theory of advanced civilizations.

### Standard Fundamental Path Operators

![Foundation of Path Semantics Cheat Sheet](https://github.com/user-attachments/assets/7daebd5d-f04b-4ccc-acb4-388516571b67)

[Link to Cheat Sheet](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip/path-semantics-cheat-sheet.pdf)

Depending on the theory one might wish to design, there are various needs for different notions of paths.

- Weak: A path that assumes less. With other words: It has fewer mathematical properties.
- Strong: A path that assumes more: With other words: It has more mathematical properties.

In Path Semantics, there is a hierachy of standard path operators that goes from the fundamental path semantical qubit operator `~` (weakest) to the strongest equality (strongest):

| Symbol | Name                    | Definition                        | Properties                            | Paper                                |
| ------ |  ---------------------- | --------------------------------- |  ------------------------------------ | ------------------------------------ |
| qu     | Qubit                   | `~a := <fundamental>`             | Tautological congruent + Sesh[*]      | [Path Semantics](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/path-semantical-qubit.pdf) |
| qi     | Qualitative Implication | `(a ~> b) := (a => b) & ~a & ~b`  | Transitivity                          | [Path Semantics](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/qualitative-implication.pdf) |
| q      | Quality                 | `(a ~~ b) := (a == b) & ~a & ~b`  | Symmetry + Transitivity               | [Path Semantics](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/path-semantical-quality.pdf) |
| eq     | Equality                | `(a == b) := (a => b) & (b => a)` | Reflexivity + Symmetry + Transitivity | [nLab](https://ncatlab.org/nlab/show/equality#propositional_equality) |

[*] *The Sesh axiom, `(!~a == ~!a)^true`, is used by default in standard Path Semantics. Non-standard Path Semantis might not use it.*

All the standard fundamental path operators are valid notions of paths.

For example, one can use `a ~~ b` to express that there is a path between two paths `a` and `b`.

However, some people might say `a == b` to express that there is a path between two paths `a` and `b`.

To avoid ambiguity, one can say "quality" instead of "path" when using `a ~~ b` and "equality" when using `a == b`.

### Logical relationships between the standard path operators

From any of the three operators qubit `~`, qualitative implication `~>` and quality `~~`,
one can derive the other three:

1. `~` first is the standard method in Path Semantics
2. `~>` first, defines `~`using `~a := a ~> a`, the rest using the standard method
3. `~~` first, defines `~` using `~a := a ~~ a`, the rest using the standard method
 
Therefore, logically, it does not matter which of these operations one starts with.
However, for simplicity's sake one starts with `~` in standard Path Semantics.
One reason this is the standard method, is because `~` requires modeling in PSQ (Path Semantical Quantum Propositional Logic).

### Overview of Logical Languages

Path Semantics has an abundance of logical languages in the foundation. Here is an overview:

| Abbreviation | Name                                               | Constructions          | Algebra         |
| ------------ | -------------------------------------------------- | ---------------------- | --------------- |
| IPL          | Intuitionistic Propositional Logic                 | -                      | Heyting algebra |
| EL           | Existential Logic                                  | IPL + `excm(!a)^true`  | -               |
| PL           | Classical Propositional Logic                      | IPL + `excm(a)^true`   | Boolean algebra |
| PSI          | Path Semantical Intuitionistic Propositional Logic | IPL + `~` + core axiom | -               |
| PSEL         | Path Semantical Existential Logic                  | PSI + `excm(!a)^true`  | -               |
| PSL          | Path Semantical Classical Propositional Logic      | PL + core axiom        | -               |
| PSQ          | Path Semantical Quantum Propositional Logic        | PL + `~`               | -               |

### Space and Pieces

A space is a mathematical structure, which is a set, sometimes called a "universe",
with some added structure.

A piece is a part of a space that is connected by paths.

For an introduction, see lecture by Vladimir Voedvodsky ["An Intuitive Introduction to Motivic Homotopy Theory"](https://www.youtube.com/watch?v=b4BlA7NymIE).

Mathematicians often study mathematical spaces and their properties.
From a perspective of mathematics, is sometimes easy to view everything as some kind of space.

### Path Semantics is not about spaces

In Path Semantics, it is not common to think about something as a space.
Path Semanticists try to avoid such biases, because they are often studying language biases and how to leverage them in designs.

When working with design, it is important to not assume too much about what a thing is.
The easiest way to do that, is simply to avoid talking about it,
but instead talk about the technicalities that are required to build stuff.

To Path Semanticists, the use of language is more important, than to pretend language makes us know what a thing is.

The difference in philosophy from most of mathematics to Path Semantics,
is required to distinguish Path Semantics as its own field,
since Path Semanticists might work outside the foundations of normal math.
There are expectations in the community of Path Semanticists of what produces high standards of mathematical knowledge,
that can be sometimes a higher standard than what is commonly accepted by the mathematical community.

### Introduction to the Qubit operator

The path semantical qubit operator `~` might be thought as introducing a new proposition that is "seeded by" its argument.

This means, `~a` can be thought of as some proposition which is not equal to any other proposition in normal logic.
It is possible to implement this functionality by using a randomly generated truth table,
that changes every time one checks a proof.
However, while checking the proof per iteration cycle, the generated truth table stays fixed,
to give coherence to the truth value of the new proposition, wherever it appears in expressions.

The power of the qubit operator `~` comes from the ability of logic to assume things arbitrarily.
With other words, the new proposition can mean absolutely anything.
This gives users great flexibility, without needing to code stuff entirely from scratch for every new project.

Due to how the truth table is generated, the qubit operator is not normal congruent, but tautological congruent.
That is almost the only property.
Still, most Path Semanticists prefer to use the Sesh axiom `(!~a == ~!a)^true` because it is practical.
Together with the Excluded Middle `(a | !a)^true`, this models sequences of bits `a, ~a, ~~a, ~~~a, ...`.

- Standard Path Semantics uses the Sesh axiom
- Non-standard Path Semantics might choose to not use the Sesh axiom

The classical model of PL that introduces `~`, PSQ, is an infinite-valued logic.
With other words, it is infinitely more complex than normal classical logic.

### Path Semantical Levels

As complex PSQ is, this logic does not introduce path semantical levels by default,
which are layers of propositions that behave locally like normal logic,
but using the symmetry of the core axiom between themselves.
This symmetry is taken advantage of to optimize brute force theorem provers, becoming exponentially faster.

Path semantical layers makes it even more complex than infinite-valued logic.
In some theories, one can think about these layers as moments in time,
and sequences of bits are streams of information that are processed and influenced by a model of some abstract computation.

For example, a laptop that would spend hours on theorems using 40-50 propositions in normal logic,
might with path semantical levels process 60-70 proposition in the same time span.
The difference can seem small, but for every extra proposition, one can model twice the complexity.
Only 20 more propositions means solving problems that are over 1 million times more complex.

### The core axiom of Path Semantics

The entire field of Path Semantics is built on one simple idea,
which is to fix meaning of symbols such that all paths from them are the same when the symbols are identical.

For example, a blue object `x` might be written formally as `x : [color_of] blue`.

On the left side of `:`, `x` is the object in question, while on the right side,
one can use sub-types to describe properties about the object.
However, if the symbol of `x` is not fixed in some sense, then it becomes difficult to talk about what it means.

When there are two objects `x, y` with meanings `a, b` respectively, a quality between `x` to `y`
implies some quality between `a` and `b`:

```text
(x : a) & (y : b) -> (x ~~ y : a ~~ b)
```

This is the core axiom of Path Semantics (there are more technical details, but this is the gist of it).

In the field of Path Semantics, all Path Semanticists agree among themselves to use this approach for collaboration.
The only thing required for something to count as "Path Semantics" is to use the core axiom or the idea behind it.
This means, no other mathematical foundation is required for people to call themselves Path Semanticists.
Nor do you have to follow journals, lectures or belong to any other mathematical community (that is irrelevant, but can be useful).

For example, a Path Semanticist might not accept First Order Logic for their current research project.
From a path semantical perspective, First Order Logic has deep flaws in its design that can not be easily avoided.
To clearly understand when First Order Logic is unsuitable, is a highly technical debate among Path Semanticists.
As a consequence, Set Theory, which uses First Order Logic, might not be acceptable either.
However, all Path Semanticists agree that from some perspective, First Order Logic might be suitable.

The core axiom of Path Semantics is not up for debate, although it is still being explored heavily and discussed a lot.
One reason is that the core axiom is what makes Path Semantics different from other fields.
A logician for example, does not need to assume the core axiom and is therefore not working in Path Semantics.
However, when assuming the core axiom or related axioms sharing the same core principle, the logician can be called a Path Semanticist.
This is a strict expectation by the community of Path Semanticists, kind of like doctors in medicine are expected to work on forms of medicine related treatments.
Also, nobody wants help from a doctor that learned medicine on their own without interacting with some community.
You can not study Path Semantics without engaging with the professional community of Path Semanticists.
This is how the field of Path Semantics distinguishes itself in excellence from other fields.
With other words, you can not call yourself a Path Semanticist simply by being a logician, a mathematician or a theoretical physicist.
As a Path Semanticist, you are expected to meet the highest standards of mathematical knowledge,
and other fields, while they might do something that looks like Path Semantics, might not always meet the expectations.

### Path Semantical Quantum Propositional Logic (PSQ)

PSQ is easy to implement in a brute force theorem solver for classical logic.

Here is the operation how it is defined in the Rust implementation [Pocket-Prover](https://github.com/advancedresearch/pocket_prover):

```rust
/// Prepares a qubit using a proposition as seed.
pub fn qubit(a: u64) -> u64 {
    use rand::{Rng, SeedableRng};
    use rand::rngs::StdRng;
    let r = unsafe {&*current::Current::<u64>::new()};
    if a & 1 == 1 {
        let mut rng = StdRng::seed_from_u64(not(a) ^ *r);
        not(rng.gen())
    } else {
        let mut rng = StdRng::seed_from_u64(a ^ *r);
        rng.gen()
    }
}
```

With PSQ, people can immediately check simple theorems themselves, without knowing anything about formal theorem proving.
They can just follow the standard method and build a mathematical language tool to help themselves reason about Path Semantics.

However, one should be careful when using this model of PSQ, because in principle it can not prove true conjectures as theorems.
This solver can only prove when a conjecture is false.
Just like in science, one must be able to construct a test in this PSQ model to try falsify a theory.
As a philosophical consequence, the mathematical foundation of the scientific method is PSQ.

This is why Path Semanticists never debate science itself as problematic in this sense.
PSQ is already a convincing argument that shows why science works like it does.
It means, people who deny science can not be called Path Semanticists.

### PSQ is an Outside Theory of Mathematics

It is impossible to build a complete model of `~` within PSQ without the HOOO EP axioms.
However, it is possible to build a model up to some finite limit of applying `~` recursively.

This means, that PSQ is Outside theory of mathematics, in the sense of [Avatar Schema Theory](https://advancedresearch.github.io/avatar-extensions/summary.html#avatar-schema-theory).
The reason is that PSQ contains a symbol, which is `~`, that does not refer to the theory of PSQ.

### Path Semantical Classical Propositional Logic (PSL)

PSL is special, because it can model the core axiom implicitly by exploiting a symmetry in brute force theorem proving.

The worst case performance in Big-O notation for two layers of propositions `F, X`:

```text
O(|F|, |X|) = 2^(1+|F|) + (1 + |F|) · (2^|X| – 2)
```

This is an exponential speedup in performance, but it has still exponential complexity (EXP in computer science).

If you want to prove a theorem `f` in PSL of two propositions `a, b` such that it corresponds to PSQ,
you need to use `f(a, b) & f(a, a) & f(b, b)` (the theorem needs to be proven for the end points too, not just the path).

### Tautological congruence

The qubit operator `~` is tautological congruent.

Most operators in mathematics are normal congruent:

```text
cong'(f) := sym(f, all((a == b) => (f'(a) == f'(b))))(f)
```

A tautological congruent operator has the following property:

```text
tauto_cong'(f) := sym(f, all((a == b)^true => (f'(a) == f'(b))))(f)
```

All normal congruent operators are tautological congruent.
However, not all tautological congruent operators are normal congruent.
When an operator is tautological congruent, but not normal congruent,
one says that it is tautological congruent.
In some languages, one can add axioms to make a tautological congruent operator normal congruent.

So, there is no incompatibility with normal congruence,
it is just that normal congruence is not high enough standard of mathematical knowledge.
The difference is that in language design, one must either separate
the universes of operators that are not normal congruent from the others,
or: Introduce axioms or prove congruence explicitly for each operator.

- In the Prop library, the universes are separated for ease of use.
- In the Hooo theorem prover, which is designed for foundational research,
  congruence has to be assumed or proved for each operator

Ergonomically, proving congruence for each operator is a pain for the user.
This is why many fields of mathematics accept assuming normal congruence everywhere.
However, these people are not Path Semanticists, and fail to meet the highest standards of mathematical knowledge.
All Path Semanticists have to make this design choice deliberately by design.
It is acceptable to assume normal congruence sometimes, but one should learn to understand why.

### There is no escape from Path Semantics

There is no such thing as avoiding Path Semantics as a field for advanced civilizations.
Path Semantics is the foundation that all advanced civilizations are building upon.
You can pretend they are not, but that is just faulty reasoning.

For example, it is not possible to design a mathematical language where normal congruence covers every aspect of math.
This is just a fact of reality, that has to be accepted by everyone that wants to build an advanced civilization.
As a private person, you are free to believe in anything you want.
However, that does not make you a Path Semanticist.
Path Semanticists must meet the expectations of the highest standards of mathematical knowledge.

On the other hand, this does not mean that Path Semanticists e.g. produce formal proofs of all their work.
That is completely irrelevant, but might be useful sometimes.
It is all about agreeing upon the principles for mathematical language design according to the core axiom.
This can be informal tacit knowledge and still welcomed by the community.

Therefore, from the perspective of Path Semantics,
any civilization without Path Semanticists is not an advanced civilization,
because that would not result in expectations of the highest standards of mathematical knowledge.

There is simply no escape.

#### Higher Order Operator Overloading Exponential Propositions (HOOO EP)

To handle tautological congruence properly, one uses the HOOO EP axioms in Path Semantics:

```text
pow_lift : a^b -> (a^b)^c
tauto_hooo_imply : (a => b)^c -> (a^c => b^c)^true
tauto_hooo_or : (a | b)^c -> (a^c | b^c)^true
```

Here, `^` means the same as `->`, but with different operator presedence.

- The `^` operator has the highest presedence
- The `->` operator has the lowest presendence

The HOOO EP axioms are not constructive in the sense they have an underlying source.
Hence, HOOO EP when added to IPL (Intuitionistic Propositional Logic), becomes Negative Philosophy.
Negative Philosophy is reasoning about the world prior to its creation.

For example, in IPL plus HOOO EP you can prove some true theorems in PSQ,
that the classical model of PSQ, for brute force theorem proving, can never prove.
Thus, such theorems can never be known from certain perspectives of math.

Therefore, since mathematics is extensible toward weaker theories,
mathematics can never be complete.
This is a result acceptable for Path Semanticists.

Path Semanticists do not waste their time debating about what is "true" in some ultimate sense.
Theorems are simply "true" when they can be proved in some language.
Hence, the theorems are always relative to use of language.
Since use of language requires symbols and symbols are modeled by the core axiom,
there is no other foundation that is acceptable to Path Semanticists than Path Semantics.
In practice though, people are not obligated to be Path Semanticists, all the time.
You should not confuse the personal side with the professional side of Path Semantics.
This is one of the reasons Path Semanticists do not talk about things as e.g. spaces,
like they tend to do in other mathematical communities.
Why? Because it is obviously depending on which language one uses, or what language one desires to create.
That is the end of that discussion.
Of course, as Path Semanticist, you can criticize this and study more in depth what this really means.
Yet, in the end this is how stuff works and there is not much people can do about it.

### Kurt Gödel was wrong

Path Semanticists do not accept Kurt Gödel's original work on incompleteness.

While this is a major result in mathematics and computer science,
in Path Semantics this considered heading in the wrong direction.
One reason is that HOOO EP is the correct notion of provability,
which constrains language to Directed Acyclic Graphs (DAGs).

A Gödel sentence uses an argument-free predicate to become self-referential.
If it had arguments, then the Gödel number would be greater than the predicate he wants to refer to,
thus he would not prove incompleteness, unless he made the predicate argument-free.
This is a cyclic graph, which is inexpressible in HOOO EP.

The notion of provability that Gödel used was Provability Logic, which contains Löb's axiom.
Löb's axiom is absurd when interpreted naively in HOOO EP.
Provability Logic is a modal logic that can be modeled in HOOO EP, but not vice versa.
Therefore, HOOO EP is more fundamental and a more correct notion of provability than Provability Logic.

This is not a debate about what "mathematics really means".
It is simply a matter of what mathematics looks like from the perspective of the core axiom of Path Semantics.
Conclusion: Kurt Gödel was wrong, according to the view of Path Semanticists.

There is nothing personal against Gödel or claiming that he made mistakes in his proof.
The proof is perfectly fine, but the interpretation of it fails to meet the highest standard of mathematical knowledge.
Do not try to over-think this too much, it is only a perspective from a particular use of language.

### Path Semanticists are not trying to pick fights

The kind of reasoning that Path Semanticists depend on, might seem strange sometimes.
However, this just use of language and should be interpreted that way.

For example, when a biologist uses latin names for species,
this is not because the biologist hate normal people or something.
It is just more convenient to use latin names, since everybody does the same in biology.

In a similar way, Path Semanticists are not debating stuff, such as, about rephrasing terminology that sounds less provoking for normal people.
When somebody says Kurt Gödel is wrong and can show why it is wrong according to Path Semantics,
this becomes an acceptable argument, regardless of how you can interpret it when not seeing math through that lens.
Path Semanticists do not care about what people think of it.
This is the only way to do Path Semantics: When it is valid according to Path Semantics, it is a valid argument for Path Semanticists.
Otherwise, nobody would be able to tell the difference between Path Semantics and other fields.

Therefore, the way of talking in the community of Path Semanticists, is kind of like when biologists use latin names for species.
There is nothing you can do about it, because if one can not talk about something being wrong in the sense of Path Semantics,
then the entire point of Path Semantics is gone: The point is to figure out what stuff means.

When some idea is inexpressible in some language, Path Semanticists do not debate whether that idea is "really true" or not.
An inexpressible idea that is unthinkable from the perspective of some language, is simply unthinkable.
It is not true or false or anything like that.
There is simply no opinion to be had about that idea.
Of course, you can take another perspective where "really true" makes sense in the way you want to talk about.
This is obviously depending on how you use language.

If you can not accept this, then do not call yourself a Path Semanticist.
Do whatever you like, but that is not what Path Semantics is about.
However, if you have a criticism of this argument and can show Path Semanticists why, then that criticism is very welcomed.

### Quality and Inquality in Logic

In the context of logic, Path Semanticists use the terms "quality" and "inquality" to make the language more precise.
This means, "quality" and "inquality" refers to the logical structure without any interpretation.

- Quality: `a ~~ a` (Self-Quality) or `a ~~ b` (Other-Quality)
- Inquality: `!(a ~~ a)` (Self-Inquality) or `!(a ~~ b)` (Other-Inquality)

However, it is common for tactics to use "sesh" as a shorthand for inquality, which comes from Seshatism.
This is easier to read than "inquality" and reminds Path Semanticists of philosophical consequences of Seshatism vs Platonism.

### Seshatism vs Platonism

The core axiom in Path Semantics is biased toward Platonism.
This means, the use of symbols in language tends to be biased toward Platonic thought,
which can result in bias against causality in actual reality.

To elaborate, remember that neither qualitative implication `~>` nor quality `~~` is reflexive.
The underlying normal logical operators `=>` and `==` are reflexive.
Therefore, the language bias is toward reflexivity even though it is technically not the case.

This means, when negating reflexivity with either `!(a ~> a)` or `!(a ~~ a)`, this departs from the Platonic language bias.
Both these terms, Self-Inqualitative Implication and Self-Inquality, are logical equivalent to `!~a`.
This propositional value is philosophically associated with Seshatism, the dual of Platonism.

In Path Semantics, Seshatism is an entire philosophy, that is authentic in sense of Heidegger on its own.
Technically, one says that Seshatism is one of the fundamental bases for Joker Calculus.
To be authentic in sense of Heidegger means an expression in Joker Calculus contain no Jokers when evaluated in the Closed variant.

- Seshatism credits knowledge by causality
- Platonism credits knowledge by abstraction

Therefore, there is an entire branch of Path Semantics that focuses on Seshatic mathematical knowledge.
This is a very different perspective than most of mathematics,
but every modern mathematical education leverages training in Seshatic knowledge,
because that knowledge is very attractive on the job market.
With other words, mathematicians are not in general opposed to Seshatism,
but most of them are not doing Path Semantics and fail to mention this duality explicitly in their own research.
Since they are not doing this properly, no Path Semanticist care about it, because that is just human behavior.
As a Path Semanticist, you are expected to know the difference between Seshatic and Platonic knowledge.
Again, because this builds on the knowledge in the community about the core axiom of Path Semantics.

Now, you might start to see how **causality** is the reason why Path Semanticists are more careful about how they use language.
They are simply applying Path Semantics to their own field.

### Quality and Inquality in Topology

In topology, quality and inquality is related to connectedness of pieces:

- Other-Quality implies topological connectedness (paths)
- Other-Inquality implies topological disconnectedness (holes)

Holes are absence of paths between pieces of spaces.
This *does not* imply that the truth value of the pieces are inequal.
In fact, one must use symbolic distinction to convert a hole into inequality.
This means that when two pieces are disconnected and no symbolic distinction is used,
any hole between them does not enforce the truth value of each piece.

Self-inquality `!(a ~~ a)` implies a hole `!(a ~~ b)` for any proposition `b`.

### Holes or Absence in Philosophy

In most of the history of humanity, in most cities women had the important role of bringing water to homes.
The lack of water pumps and electricity has shaped how people think about women today.

Generally speaking, women have been discredited knowledge that they actually produced.
There is a tendency that men are credited things they did not accomplish themselves,
while women are discredited even things they clearly accomplished.

From a Path Semantical perspective, this difference is caused by influence of language bias.
The role of philsophers, which comes from Ancient Greek, was mostly attributed to males.
It was because in most places of Ancient Greek the demographics was skewed, as much as 1 woman per 10 men.
1/3 of women died by childbirth, so their average age was much lower than men.
Many sexual relationships in the ancient world would today be illegal.
By all standards of measuring quality of life, it was horrible to live in the ancient world, particularly for women.

Yet, there were women that were warriers and some who lived by human trafficking in the ancient world.
Most of modern religions are reactions to collapse and instability with judgemental reasoning toward these groups in the ancient world.

Just like a Path Semanticist can call Self-Inquality for Sesh, it can also mean a hole or absence of some history.
This absence of history can influence and shape history equally much as particular events that get remember by later generations.

### Internal Difference in Philosophy and Mathematics

An Internal Difference in philosophy happens when some idea in language is dualistic seen from within the language,
but non-dual for speakers who do not speak that same language.

For example, the word "cow" in English is used both for the mother of a calf, but also for cattle in general.
In the case of "cowboy", the "cow" part of this word refers to cattle, therefore "cattle-boy", not "mother-of-the-calf-boy".

To people who do are learning English for the first time, this difference can seem confusing.
The speakers of English do not even think about these things.

Another example: It sounds silly to say that "submarines can swim" (Alan Turing),
but not when saying "airplanes can fly" (Noam Chomsky).
It is not easy to explain, but there are such biases in language that most people learn without even knowing why.
They absorb these language biases unconsciously.

A more mathematical example of Internal Difference is a random string of bits.
By inverting each bit in the string, it still looks completely random.
Therefore, a hidden involution of this kind before sending a message is only known to the speaker of that language.
To receivers that do not get this information of involutions, this looks like non-duality.

### The Sesh Axiom: The Qubit Operator has Internal Difference

The Sesh axiom is the following:

```text
(!~a == ~!a)^true
```

In the brute force model of PSQ, one uses involution of a string of bits to achieve this property.
As a consequence, the qubit operator `~` has an Internal Difference in standard Path Semantics.

Now, qualitative implication `~>` and quality `~~` are defined using qubit, so they too have an Internal Difference.

This means, the core axiom of Path Semantics can be interpreted in the lens of Seshatism.
It is possible because from the outside, one can choose a radically different perspective on this non-duality.

### The Time Interpretation of the Core Axiom

If the only thing the core axiom of Path Semantics modeled was use of symbols,
then that would be excellent all by itself.
However, the math does not stop there:
The core axiom can be interpreted as propagating propositions between moments of time.

This means, Path Semanticists can work on the Seshatic branch of Path Semantics which credits knowledge by causality.
It is not just a simple and narrow domain, but it opens up an entirely different world of math.

### PSQ - Path Semantical Quantum Propositional Logic

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

PSQ extends PL (Classical Propositional Logic) with a `~` operator (called a "qubit"),
which is used to define `~~` and `hom_eq`.

You can find an implementation in the [Pocket-Prover](https://github.com/advancedresearch/pocket_prover) library.

Technically, one can use `~~` only, but the implementation is easier to understand in terms of the `~` operation.

List of theorems:

| Name | Formula |
| ------------ | ------------------------------------ |
| Aqual-Definition | `(a ~¬~ b) == ((a == b) ⋀ ¬~a ⋀ ¬~b)` |
| Qual-Imply-Definition | `(a ~> b) == ((a => b) ⋀ ~a ⋀ ~b))` |
| Qual-Imply | `a ~> a` |
| Qual-Imply-Transitivity | `(a ~> b) ⋀ (b ~> c) => (a ~> c)` |
| Contra-Qual-Antisymmetry | `((a ¬~~ b) ⋀ (b ¬~~ a)) => (a == b)` |
| Contra-Qual-Asymmetry | `(a ¬~~ b) => ¬(b ¬~~ a)` |
| Contra-Qual-Definition | `(a ¬~~ b) == ((a == b) ⋀ ¬~a ⋀ ~b)` |
| Contra-Qual-Contrapositive | `(a ¬~~ b) == (¬b ¬~~ ¬a)` |
| Contra-Qual-Irreflexivity | `¬(a ¬~~ a)` |
| Eq-Catuskoti | `(a == b) == ((a ~~ b) ⋁ (a ~¬~ b) ⋁ (a ¬~~ b) ⋁ (b ¬~~ a))` |
| Hom-0 | `hom_eq(0, a, b) == true` |
| Hom-1 | `hom_eq(1, a, b) == (a == b)` |
| Hom-2 | `hom_eq(2, a, b) == ((a == b) ⋀ (~a == ~b))` |
| Hom-2-Qual | `hom_eq(2, a, b) == ((a ~~ b) ⋁ (a ~¬~ b))` |
| Hom-Lim | `lim n -> ∞ { ¬hom_eq(n, a, b) }` |
| Hom-N | `hom_eq(n, a, b) == ∀ i n { qubit^i(a) == qubit^i(b) }` |
| Hom-Reflexivity | `hom_eq(n, a, a)` |
| Hom-Symmetry | `hom_eq(n, a, b) => hom_eq(n, b, a)` |
| Hom-Transitivity | `hom_eq(n, a, b) ⋀ hom_eq(n, b, c) => hom_eq(n, a, c)` |
| Hom-Xor | `hom_eq(2, a, b) == xor(a ~~ b, a ~¬~ b)` |
| Qual-Definition | `(a ~~ b) == ((a == b) ⋀ ~a ⋀ ~b)` |
| Qual-Hom | `(a ~~ b) => hom_eq(2, a, b)` |
| Qual-Platonism-Product | `(a ~~ b) => ((a ~~ a) ⋀ (b ~~ b))` |
| Qual-Seshatism-Sum | `(¬(a ~~ a) ⋁ ¬(b ~~ b)) => ¬(a ~~ b)` |
| Qual-Symmetry | `(a ~~ b) => (b ~~ a)` |
| Qual-TransiTivity | `((a ~~ b) ⋀ (b ~~ c)) => (a ~~ c)` |
| Qual-TransPort | `((a ~~ a) ⋀ hom_eq(2, a, b)) == (a ~~ b)` |
| Qubit-Excluded-Middle | `~a ⋁ ¬~a` |
| Qubit-0 |  `qubit^0(a) == a` |
| Qubit-1 | `qubit^1(a) == ~a` |
| Qubit-Not | `~¬a == ¬~a` |
| Qubit-Qual | `~a == (a ~~ a)` |

#### Translation from PSQ into Homotopy Type Theory

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

| PSQ | HoTT |
| ------------ | ------------------------------------ |
| `a` | `x : isContr(A)` |
| `¬a` | `x : isContr(A) -> ⊥` |
| `~a` | `x : A` |
| `a => b` | `f : isContr(A) -> isContr(B)` |
| `a => ~a` | `f : isContr(A) -> A` |
| `a => ~b` | `f : isContr(A) -> B` |
| `~a ⋀ (a => ~b)` | `(x, f) : (A, isContr(A) -> B)` |
| `~a => a` | `f : A -> isContr(A)` |
| `~a => b` | `f : A -> isContr(B)` |
| `~a => ~b` | `f : A -> B` |
| `a ~> b` | `f : (isContr(A) -> isContr(B), A -> B)` |
| `a == a` | `refl{A} : Id(A, A)` |
| `a == b` | `p : Id(A, B)` |
| `a ~~ b` | `q : (Id(A, B), A, B)` |
| `~a == ~b` | `f : A <-> B` |
| `hom_eq(2, a, b)` | `f : (Id(A, B), A <-> B)` |
| `a ⋀ b` | `(x, y) : (isContr(A), isContr(B))` |
| `~a ⋀ ~b` | `(x, y) : (A, B)` |
| `a ⋀ ~a` | `(x, y) : (isContr(A), A)` |
| `~a ⋀ ~~a` | `(B, x) : (A, B)` |
| `a ⋁ b` | `x : isContr(A \| B)` |
| `~a ⋁ ~b` | `x : A \| B` |
| `false` | `x : ⊥` |
| `true` | `x : ⊤` |
| `¬~a` | `x : A -> ⊥` |
| `~¬a` | `x : A -> ⊥` |

#### Homotopy Level 0

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

In PSQ `~~a` is to `~a` what `~a` is to `a`.
However, there is no way to go from `a` to something else.
The idea that there is no way to go from `a` to something else,
makes it natural to use `a` as Homotopy Level 0, or `isContr(A)` in HoTT.

#### Continuous Maps

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

In PSQ a continuous map is written `a ~> b`, which connects a space `a` to a space `b`.
By Cont-Definition, `a ~> b` is equal to `(a => b) ⋀ (~a => ~b)`.
In HoTT `a ~> b` is a type `(isContr(A) -> isContr(B), A -> B)`.

In PSQ `a => b` projects arbitrary small loops in a space `A` to arbitrary small loops in space `B`.
In HoTT this is the type `isContr(A) -> isContr(B)`.

In PSQ `~a => ~b` projects points in space `A` to points in space `B`.
In HoTT this is the type `A -> B`.

#### Propositional Equality, Id and the Pointcaré conjecture

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

In PSQ, `(a => b) ⋀ (b => a)` is equal to `a == b`.
In HoTT this means that `(isContr(A) -> isContr(B), isContr(B) -> isContr(A))` equals `Id(A, B)`.
When arbitrary small loops in space `A` are projected to `B` and vice versa,
it follows that `A` and `B` are topologically equivalent up to homotopy.

Another way to think about this is by using the [Pointcaré conjecture](https://en.wikipedia.org/wiki/Poincar%C3%A9_conjecture).
Wherever in `A` is locally contractible, then `A` has the same local topology as a hypersphere.
Wherever in `B` is locally contractible, then `B` has the same local topology as a hypersphere.
When `A`'s contractibility is equal to `B`'s contractibility, they both have same topology by some shape.
This shape can be constructed by hyperspheres, using a glue operation.

#### Higher Homotopy Levels and Type Universe Polymorphism

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

In PSQ, `~~a` is tricky to imagine as a type in HoTT.
However, one can use `~a ⋀ ~~a` translated as `(B, x) : (A, B)` to help the intuition.
To make `B : A` and `x : B`, it requires `A` to have a higher type universe than `Type(0)`.
This means `~~a` naturally describes `A` as `Type(1)` or higher.
Since any two proofs of `Type(0)` are propositionally equal (Homotopy Level 1),
it means that `Type(1)` has the structure of sets (Homotopy Level 2).

Similarly, `~~~a` naturally describes `A` as `Type(2)` or higher.

Since PSQ treats type universes this way, it corresponds naturally to type universe polymorphism in HoTT.

To turn on type universe polymorphism in Coq, use the flag `Set Universe Polymorphism.`.

### Translation into Hegel's Philosophy

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's philosophy is centered on interpretation of history and existence through time.
In Path Semantics, there are two kinds of "moments" in the sense of Hegel:

1. Moments distinguished by repeated application of self-quality/qubit `a, ~a, ~~a, ...`
2. Moments distinguished by path semantical layers using the core axiom

Physically, the first kind might be thought of as unstructured relativistic time (clocks in local space-time),
since `~a` comes after `a` but it is unknown whether `~a` comes after `~b`.
The second kind might be thought of as Newtonian time (universal clock),
where order in time is determined by path semantical layer.

Unstructured relativistic time happens prior to the observer, where order of events can be undefined.
It is the observer that relates events by order,
such that from the perspective of a single observer,
the universe appears to have a universal clock (the time in local space-time projected onto the universe).

Hegel did not distinguish the two kinds of time physically,
because at his time the only notion was in terms of Newtonian time (universal clock).
Relativistic time appeared later through the work of Einstein.

This means, when reading Hegel's "Science of Logic",
one should be aware that he expresses his ideas ambiguously in relation to modern physics,
viewed through the lens of Path Semantics.
The easiest way to solve this ambiguity is to use the first kind by default
and the second kind by mentioning it explicitly.

#### Self-Quality

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's notion of self-quality can be translated directly to self-quality/qubit in Path Semantics:

```text
~a    self-quality of `a`
```

#### Ground

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's notion of ground is how the appearance of an object is related to previous moments by thought or by itself.

```text
`a` is the ground of `~a`
```

#### Being

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's notion of Being is a constructive proposition.

```text
a    `a` is Being of `a`
```

Being-In-Itself and Being-For-Itself are movements of Being into self-quality
through two different ways.

```text
a ~~ a                  Being-In-Itself as movement through direct self-quality
(a ~~ b) => (a ~~ a)    Being-For-Itself as movement to self-quality through an Other
```

In [Avatar Witness Theory](https://advancedresearch.github.io/avatar-extensions/summary.html#avatar-witness-theory),
it is common to call Being-In-Itself for "Loop Witness" and Being-For-Itself for "Product Witness".

#### Essence and Shine

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's notion of essence is a potential in relation to Being.
Essence can be though of as a type where the type operator is shine.

```text
a : T    `T` is the essence of Being `a` and `:` here is the shine
```

Notice that Being `a` here is dialectically biased toward a proof of Being `a : ...`.
Therefore, essence implies bias toward "proof sense" which for Hegel is shine.
The unbiased Being is `a` as constructive proposition `a`.

In Path Semantics, this is equal to:

```text
(a => T) ⋀ (a < T)
```

Where `<` is order of path semantical layer.
Therefore, essence and shine are in relation to the observer.

#### Indeterminancy

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

For Hegel, self-quality is indeterminate.

In Path Semantics, one can say that:

- Classically, `~a` is a random proposition seeded by `a`
- Constructively, `~a` is not provable but has congruence by tautological equality

These are technical ways of stating the precise indeterminate properties of self-quality.
Notice that the form of indeterminacy depends on the mathematical language in question.

One important consequence is that self-quality is not a predicate,
because predicates have congruence by normal equality.
This undermines First Order Logic in philosophy,
which is a predicate logic.

#### Absolute Knowing

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's notion of absolute knowing is ambiguous,
since there are two forms of absolute knowing in relation to self-quality:

1. Absolute knowing through congruence by tautological equality
2. Absolute knowing through the proof of `~true`

Congruence by tautological equality means that from `~a` one can prove `~b` if `(a == b)^true`.
This means, if there is absolute knowledge that `a == b`, there is absolute knowing by self-quality.
In some sense, absolute knowing is the ability to recognize absolute knowledge.
It does not grant absolute knowledge directly, only the means of making it familiar using self-quality.

The proof of `~true` uses the core axiom and a  functional model of the identity map `id`.
Hegel was inspired by Fichte's `a = a`, which in functional notation is `id(a) = a`.
This might be interpreted as the possibility of thinking true statements `true` within time `~true`.
Thus `~true` is a proof of possible absolute knowledge, or absolute knowing.

#### Justification for Hegel's Ideas

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Histocially, Hegel took inspiration from Leibniz, which came with some ideas that later resulted in topology.

Hegel's notion of self-quality is today understood in Path Semantics to be a generalization of open sets,
which are required in topology to define continuous maps.
The technical term for the functional model, using path semantical quality, is [Open Morphisms](https://github.com/advancedresearch/path_semantics/blob/master/papers-wip2/open-morphisms.pdf).

Open Morphisms allows termination of higher bimorphisms in n-categories.
The insight is that the contravariant property of the imaginary inverse is proof theoretically valid,
even though the imaginary inverse has no underling model for specific morphisms.

Since the imaginary inverse maps to the dual category,
Open Morphisms are important philosophically in all applications of mathematical duality.

#### Bad vs Good Infinity: Where Hegel's Ideas Fail

*NOTICE: THIS SECTION IS OUTDATED AND NEEDS SOME REWORK*

Hegel's idea of Being does not account for physical consciousness.
The reason is that, in fundamental physics, [observer bias in Wolfram models 
requires a mechanism that favours complex worlds](https://github.com/advancedresearch/path_semantics/blob/master/sequences.md#consciousness-in-wolfram-models).
Hegel's notion of quality is merely a philosophical approximation of this mechanism.

Hegel described this as a "bad infinity" vs "good infinity":

- Bad infinity is lifting from equality with symbolic distinction to quality
- Good infinity is direct quality

To account for physical consciousness in fundamental physics,
it requires a precise model for the bad infinity.
Logically, there is an axiom to lift equality into quality.
However, there is no physical interpretation of how this happens in time.

For example, Hegel's ideas can not account for whether there is a certain fixed number of operations
determining forms of symbolic distinction.
This would mean an upper bound of self-knowledge built into the universe.
E.g. under eternal cosmic inflation, the observer bias might be bounded to some computational class of complexity.
There might be axioms about symbolic distinction that are unreachable from any well-defined class of complexity.
Hegel does not elaborate on complexity bounds of bad infinity.
In any case, such bounds might not be scientifically falsifiable.

Hegel's ideas builds on top of quality and therefore lacks a precise model.
One can say Hegel's ideas are constrained to some language similar to quality in the foundation of Path Semantics.

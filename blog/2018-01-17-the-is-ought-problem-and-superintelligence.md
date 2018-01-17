# The Is-Ought Problem and Superintelligence
by Sven Nilsen, 2018

Link to Wikipedia article: [Is-Ought Problem](https://en.wikipedia.org/wiki/Is%E2%80%93ought_problem).

I will summarize my argument here briefly:

1. Mathematical proofs are not language dependent (they are functions that are logically equivalent to `true_n`)
2. Because of 1) any deterministic decision procedure can be used in a mathematical proof
3. Any deterministic decision procedure allows any statement in any language as input
4. Because of 3) there is, in principle, no difference between "is" and "ought" statements
5. The actual problem is that mathematical proofs neither tell us what "is" and what "ought" to be

With "mathematical proofs" I mean tautologies, which is a function of type `A -> bool` returning `true` for all input.
This is equivalent to the `true_n` family of functions in path semantics.
For simplicity of this argument, I assume proofs of infinite input bits,
but they can depend on statements in a language capable of expressing infinite number of sentences.

For example, an "ought" proof:

```
∀ a, b : u8 {
    ( should(a) -> should(b) ) ∧ should(a)
    --------------------------------------
    should(b)
}

should : u8 -> bool
```

The above example is just as valid as the "is" proof:

```
∀ a, b : bool {
    ( a -> b ) ∧ a
    --------------
    b
}
```

And we can combine them (deriving an "ought" statement from an "is" statement):

```
∀ a : bool, b : u8 {
    ( a -> should(b) ) ∧ a
    --------------------------------------
    should(b)
}

should : u8 -> bool
```

To a computer that brute forces through all values and evaluates the expressions,
the proofs above all result in the same thing: `true` for all inputs.

Why did David Hume thought there was a difference between "is" and "ought" statements?

The human brain divides up information into categories, and therefore "is" and "ought" statements feels different.
This makes it tempting to fall for a mind projection fallacy.
It feels like such statements are intrinsically different, because they trigger different responses and feelings in the brain.

Notice that the distinction between "is" and "ought" is useful, but it is pretty much an arbitrary useful distinction.

The same could be said about the difference between emotions and logic.
In the platonic world of mathematical proofs, there is no distinction between emotions and logic!

- Logic is follows from axioms derivable from the computational properties of boolean algebra
- Emotions follows from the function of the human brain

If you had a fast enough computer, you could derive the "axioms of emotions" from a description of a human brain.
However, since human individual are thinking differently, you might need many human brains for better understanding.

Even the human brain is much more complex than the axioms of logic,
neither is more or less real than the other.
When logic is embodied in the world, it uses the same physical particles as embodied emotions.
You can scan the human brain and store it inside a computer,
and you can store the axioms of logic and store it inside a computer.
Both systems have a platonic side and a embodied side of semantics.
It is just that we are used to think about the platonic side of logic, and the embodied side of emotions.
This results in a lot of confusion.

David Hume might not have this black/white picture that some few people might believe at first encountering this idea.
He noticed that one must define how an "ought" statement is derived from the "is" statement.
This is just providing inference rules that connects these two kinds of statements.

It is correct that "is" statements are distinct from "ought" statements,
but it is incorrect to say that "ought" statements can not be derived from "is" statements in any proof.
This is only the case when "is" statements is the only language used for reasoning,
and "ought" statements are forbidden, which makes "is" and "ought" distinct by definition!

Proofs in general are not tied up with any specific language.
Their only requirement is that they return `true` for all inputs.
Therefore, you can combine any statements from any language for reasoning as long it returns `true` in the end.

The concept of logic is different from the concept of proof.
Logic is a language for proving sentences of a certain kind.
A proof is a grounding technique for testing rules.
These are not the same concepts.

When it comes to superintelligence, many people seem to believe that mathematics is the natural language of AI.
This is false.

A superintelligent AI might develop its own sort of morality to solve tasks, just as it might use mathematics.
The only reason philosophers consider mathematics more likely to be reinvented by e.g. alien civilizations,
is that these concepts have lower complexity and are universally more likely to used to improve performance.
Which is very useful when you try to build things like computers, machines and spaceships.

There are mathematical concepts that AIs are unlikely to develop,
just like people do not need much of the pure mathematics concepts in their daily lives.

A superintelligent AI is not dangerous because it develops bad intentions toward humans,
or because it has in inborn insensitivity that makes it "only understand mathematics":

1. It is dangerous because it might make mathematical mistakes
2. It is dangerous because it might develop values that conflicts with human values
3. It is dangerous because it might drift away from its original goals

Intelligence is a broad term and not limited to "calculating with numbers very fast".
Morality reasoning is a kind of intelligence, just like computing with numbers.
It is not guaranteed that an AI will be able to compute with numbers,
and it is not guaranteed that it will develop some sort of morality reasoning.
Even without these abilities, the AI might still do a lot of damage, or being observed as very competent at solving some tasks.
Perhaps it manages fine by memoizationing some numbers and approximate guesses and heuristics?

Mathematics and values are likely not cleanly separated in an arbitrary mind, unless it was designed that way.
Humans have a messy view of logic and reasoning, where morality and facts are mixed up.
Likewise, an AI could infer goal statements from things it observes,
whether these rules of inference might make sense to us or not.

A mathematical proof can not tell what "is" in the world.
One must be able to disagree with the conclusion and analyze the assumptions to do so.

Neither can a mathematical proof tell what is "ought" to be in the world.
One must be able to disagree with the conclusion and analyze the assumptions to do so.

See? These two kind of statements behave the same way.

# Five Things You Should Know About Path Semantics
by Sven Nilsen, 2018

Recently I realized it is common for people who get curious about [path semantics](https://github.com/advancedresearch/path_semantics),
to overlook the basics in a hurry and perhaps missing the very thing they are looking for.

So, I made list of five things that you should learn, before you make choices what to study next:

1. Take normal paths seriously (the normal paths cover a larger topic than what it seems at first)
2. Try to find your own normal paths (if you don't, you gonna miss a lot of things right in front of you)
3. Understand that normal paths don't appear arbitrarily (not all things are predictable, but everything that's predictable follows a system)
4. Don't underestimate the practicality of normal paths (they are actually very useful compared to most other things you learn of math)
5. Memorize a few standard functions and their normal paths (this will be helpful when you need to make examples)

### 1. Take normal paths seriously

Normal paths are the most important thing you will ever learn about mathematics. Period.

When I show people examples like this:

    and[not] <=> or
    
Which can be written in equational form:

    not(and(x, y)) = or(not(x), not(y))
    
People get this reaction: "Isn't this just De Morgan's law?" and then lose attention, because they think they know this stuff already.

Then, I show them this another example:

    concat[len] <=> add

People tend to think: "Isn't this just dependently types?"

Then, I show them this example:

    mul_mat[determinant] <=> mul

People then think: "What does this got to do with the other things?"
    
It takes a while for people to notice that I am showing them the same sentence over and over,
just swapping the words in the sentence.

Then, I tell people the following:

- You can think of any property of any system that is predictable as a normal path.
- Anything perfect predictable about any computable process can be expressed as a normal path.
- If you have a system of perfect information, then most of the "mathy" stuff you need are just normal paths.

People still seem to not understand what is being shown to them.

If you have this reaction, don't give into that feeling and think that "the secret of math I'm looking is *out there*".

Really, THE SECRET of math is just right of front of you, waiting for you to make the connection.
It is much closer and easier to learn than you think.

You can either learn this basic step, or you can go waste years looking for your "magical secret".
All the time you have spent looking, it has been here, waiting for you to find it.

In general, what I mean about normal paths, are equations of the form:

    f[g_i->n] <=> h
 
If there is a partial normal path, you can write:
 
    f{c}[g_i->n] => h
 
This is among the shortest but most useful expression of mathematics that you will *ever* learn.
Don't be stupid and think that there is something more important.
If you miss this one, a lot of time will be wasted.
 
### 2. Try to find your own normal paths
 
Many equations that people learn are just parts of a normal path.
 
For example, the determinant of a triangular matrix is the product of the elements on the diagonal:
 
    det{triangular}[id] => \(m) = prod i {m[i][i]}
     
This can be reduced to:
 
    det{triangular} => \(m) = prod i {m[i][i]}
     
I just found this example by looking something random at a mathematical wikipedia page.
 
Normal paths are everywhere. Go look for them.
 
You should expect that *most things* that you are looking for, are expressible as normal paths.
 
For example, the famous Heisenberg's uncertainty principle:
 
    σ_x * σ_p >= ħ / 2
     
How would you express this as a normal path?
 
What about this:
 
    ge{(= σ_x * σ_p), (= ħ / 2)}[id] => true_2
     
Usually, I might prefer to express this as a sub-type:
 
    (σ_x, σ_p) : (>= ħ / 2)
     
However, my point is that *anything* that can be perfectly predicted, can be expressed as a normal path.
 
It doesn't matter that quantum mechanics has uncertainty built into it,
because you can still make the *perfect prediction* about it that you can't predict some things perfectly.
 
Here is another example:
 
    population{(= scotland), (= 2017)}[id] => (= 5 424 000)
     
A normal path that compares a country's population against Scotland's population for the same year:

    population{_, (= X)}[id x id -> (>= population(scotland, X))]
    
This can also be written:

    population(Y, X) >= population(scotland, X)

Finding normal paths this way helps practicing the understanding of how they relate to path semantics and equations.

You get better at expressing your thoughts in a very concise and formal way.
Equations are easier to understand when there are multiple ways of expressing them,
and the path semantical notation makes it easy to use it in proofs.

### 3. Understand that normal paths don't appear arbitrarily
 
All functions of finite types `A -> B` can be enumerated.
This means, that you can list them.

Since every function might have normal paths, they can't go and come as you like.

If something is perfectly predictable, then it's perfect predictable. There is no magic.

Normal paths don't appear arbitrarily. They are either there or not.

Everything that is predictable follows a system. There are no exceptions.

### 4. Don't underestimate the practicality of normal paths

If you learn some piece of math that looks nice and you *wonder* whether it's useful,
then you will often find that is was not that useful in practice.

This tendency makes people believe that very little math is extremely useful.

However, normal paths are more useful than you think at first, it is just that you don't see them.
You don't see them because you don't understand them at a very deep level yet.
To understand them, you need to practice to become a master.

Practicality of mathematics can be summed up as: Normal paths are useful, other things not so much.

This is a very strong claim about path semantics.
However, it's true.

Things do not have to be very deep to be useful, but they seem deeper than necessary if you don't know how normal paths work.

You don't have to learn Category Theory or other complicated things to learn about normal paths.
They are very easy to learn compared to most of mathematics, still, they are probably the most useful to learn about.

### 5. Memorize a few standard functions and their normal paths

I use a few normal paths over and over, because what can be said about these can often be said about normal paths in general.

You don't need to memorize a lot, just enough to have something to experiment and play with.

If you are confused about something, you can just check with the few you memorized.
Instead of memorizing rules for how normal paths behave, you can practice deriving rules using the ones you memorized.
That's the genius with memorizing examples: If you wonder about something, there is a way to check it quick and easy.

All the other normal paths are essentially just dictionary lookups.
You should not even bother your mind about them, because there are many other things to learn.

It is more important to get some of them right and understand the general principle,
than memorizing many while not understanding the general principle.

Last, but not the least: Once you "get" normal paths, don't think of anything that is perfectly predictable as "special", ever again.
Think of it as the most ordinary and obvious thing in the world, like `1 + 1 = 2`.
If you have a problem, ask yourself "Is this a normal path?" and if "yes", then apply the standard techniques to solve the problem.

All normal paths are in some essence the same thing: They behave the same and are written the same way.
Normal paths are the same sentence written over and over, just by swapping the words.

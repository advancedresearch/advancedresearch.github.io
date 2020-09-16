# Quickbacktrack 0.7 Released
by Sven Nilsen, 2020

The [Quickbacktrack](https://crates.io/crates/quickbacktrack) library v0.7 is released!

From Wikipedia, [Backtracking](https://en.wikipedia.org/wiki/Backtracking) is a general algorithm for finding all or (some) solutions to computational problems,
notably constraint satisfaction problems, that incrementally builds candidates to the solutions,
and abandons a candidate ("backtracks") as soon as it determines that the candidate cannot possibly be completed to a valid solution.

The Quickbacktrack library uses a `Puzzle` trait to specify the problem,
which then can be solved using the following solvers:

- BacktrackSolver ("normal" backtracking)
- MultiBacktrackSolver (solves with multiple strategies at the same time)
- EntropyBacktrackSolver (new!)

In this blog post, I will talk about the new `EntropyBacktrackSolver`.

### Why Entropy?

[Entropy](https://en.wikipedia.org/wiki/Entropy_(information_theory)) is a measure of the uncertainty of a variable.

The [WaveFunctionCollapse](https://github.com/mxgmn/WaveFunctionCollapse) algorithm showed that entropy is a useful measurement for constraint solving,
together with a "wavefunction" that models the probabilities of the puzzle pieces in super-position.

Here is an animation of the WaveFunctionCollapse algorithm in action:

![illustration](https://camo.githubusercontent.com/dc39c61e02aa67abd0f923628cf241120d14f517/687474703a2f2f692e696d6775722e636f6d2f734e75425653722e676966)

The algorithm works like this:

1. A cell with the least entropy is picked
2. The cell is "collapsed" into a concrete value
3. Constraints are propagated from the cell to other cells, updating their measure of entropy
4. Repeat 1).

The `EntropyBacktrackSolver` generalizes the WaveFunctionCollapse algorithm to any puzzle that can be solved with backtracking.

- The `SolveSettings::max_iterations` controls how deep the solver should try before making new attempt
- The experience from previous attempts is transferred to new attempts by reusing weights
- One can shuffle the order of choices randomly, controlled by `EntropySolveSettings::noise`
- If no solution is found, then a final attempt can be made with customized maximum number of iterations

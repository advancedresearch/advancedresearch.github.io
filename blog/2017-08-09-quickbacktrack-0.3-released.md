# Quickbacktrack 0.3 Released
by Sven Nilsen, 2017

The [Quickbacktrack](https://crates.io/crates/quickbacktrack) library v0.3 is released!

This library was started because I needed an easy way to compare different strategies for solving constraint satisfaction problems.

A lot of such problems can be described solving a puzzle by composing two sub-strategies:

1. Which part of the puzzle to focus on next
2. How to prioritize the possible choices for a given part of the puzzle

This design guarantees that any strategy of kind 1) is compatible with any strategy of kind 2).

Let me illustrate the importance of testing strategies in Sudoku:

```
 ___ ___ ___
|   |   |   |
|   | 34|   |
|   |   |   |
 ---+---+---
|96 | 5 | 87|
|2  |   |  6|
|71 | 2 | 45|
 ---+---+---
| 2 |  9| 78|
| 4 |61 |5  |
|  8|   | 13|
 ---+---+---
 ```
 
 The naive backtracking strategy to solve this puzzle is the following:
 
 1. Pick the first empty slot
 2. Order choices from 1 to 9
 
 This strategy solves the puzzle in 295 992 moves (trivial moves included).
 
 Now, try the following strategy:
 
 1. Pick the empty slot with least number of possible moves
 2. Order choices from 1 to 9
 
 This strategy solves the puzzle in 59 moves.
 
 Why is the second strategy so much more efficient than the first one?
 
 The reason is that when you focus on the part of the puzzle where you have highest chance of failing,
 it is more likely to avoid early wrong assumptions that need to be corrected later.
 
 A backtracking algorithm is not good at fixing early mistakes.
 One way to avoid regretting decisions is to try making mistakes as soon as possible.
 
 ### Maximizing Potential
 
 Today I had a new idea of how to improve strategies of kind 2).
 This came about when I was thinking of the backtracking algorithm tends to get stuck in a sub-space
 where there are no solutions.
 
 The problem is when the solver is "looking for trouble" by focusing on where the puzzle has highest chance of failing.
 It happens often that a single bad choice is enough to get stuck for a while.
 
 What can you do to pick the best choice out of a few alternatives?
 
 The inspiration came after working on the [new library for automatic theorem proving of monotic inference](https://github.com/advancedresearch/monotonic_solver).
 The kind of rules I use in the monotonic solver adds new knowledge, e.g. `A did B with C`.
 
 Then I started thinking what happens when you add knowledge that tells that something can not happen.
 This makes the solver non-monotonic if you have another rule that can infer it can happen before it knows it can not happen.
 
 A backtrack algorithm has no problems with non-monotonicity because it can just undo any previous assumptions.
 Still, the reason it gets stuck has something to do with non-monotonicity.
 
 When you make a choice and later get stuck by it, then it is because you could not predict the consequences of that choice.
 We want to predict the future in a such way that the amount of unforeseen consequences are minimized.
 
 With other words, one can think of this as a kind of potential of the future, which we want to maximize.
 
 In a puzzle solver strategy, one can do this by measuring how much the sum of all possible moves are reduced
 by a given choice. To maximize the potential, you give higher priority to moves that have less reduction in future moves.
 
 For example, if `A` leads to 407 possible moves next time,
 and `B` leads to 1056 possible moves, then `B` should get priority because there is less chance to get stuck on average.
 
 This leads to a battle between strategies of kind 1) and 2):
 
 - Good strategies of kind 1) look for places that needs attention, because not paying attention can mean getting stuck
 - Good strategies of kind 2) look for ways to get out of situations that are uncomfortably constrained
 
 By changing the strategy of kind 2) to one that orders choices descending by the sum of possible moves next turn,
 it reduced the number of moves to solve the Sudoku puzzle from 59 to 57.
 
 However, if I change strategy of kind 1) back to finding the first empty slot,
 the number of moves to solve the puzzle becomes 4 895 159.
 This is much worse than the original 295 992 moves.
 
 ### Combining Strategies
 
 If you have multiple algorithms that recommend different orders of choices for a given part of the puzzle,
 then you can construct a new order that combines the suggestions from the algorithms.
 
 One way to do this is to just sum up the indicies of each received order, and then order the choices by the sum.
 
 I added this to the library through the `combine` function.
 
 ### Picking Best Strategy
 
 Very often, there is no single strategy that is better than all others in all possible situations.
 However, there is way to find a solution using the best strategy at hand.
 
 This algorithm is simply to evaluate each strategy a single step at a time,
 then as soon as any strategy finds a solution, you can terminate the search.
 
 This way of solving a puzzle is brilliant because of two things:
 
 1. The overhead is a constant multipled with the minimum number of steps, relative to the best strategy at hand
 2. Using the best strategy usually triumphs improving the performance of each step
 
 When the worst-case of any strategy grows exponentially,
 it does not matter how fast that strategy computes,
 because the exponential blow-up in running time destroys any performance gain.
 
 On the other hand, solving a puzzle using multiple strategies requires lot of memory.
 Still, because computers already have a lot of memory available,
 and the memory required grows linearly with the number of strategies,
 the trade-off is pretty good.
 
 I added this to the library as `MultiBackTrackSolver`.

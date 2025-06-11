# Theory Proving Research

Theorem proving is a huge and interesting field.

### Introduction to theorem proving

Basically, theorem proving is about using data.
From the data one can answer questions people like to know the answer to.
Data can be both real or fictional.

For example, when people navigate using maps, they are using data.
The tools they use for navigation helps people receive useful answers,
such as which direction to go to reach some destination.

Theorem proving is the process where one extracts answers from data.
This is usually done by computers.

### Basic theorem proving

In the Computer Stone Age, people used to do theorem proving by hand without automatic checks.
Since then, we have developed tools that make theorem proving much more faster and reliable, which resulted in a new era of computing.

The AdvancedResearch community is focusing on basic theorem proving research,
because we believe multiple tools are needed for research in general, due to various tradeoffs in design.

### Logical design distinctions

- The word "generic" means you can program a solver using any grammar you like
- The word "classical" means you propositions are either true or false, always
- The word "constructive" means you need proof of a proposition, where two proofs of a proposition are equal

### Solver design distinctions

- The word "brute force" means that the solver enumerates and checks every case
- The word "monotonic" means the solver can only add facts, but not remove them
- The word "linear" means the solver can add and remove facts, seeking a minimum fix-point in a cycle

### Reproducibility

- The word "determinstic" means that the output is the same when input is the same
- The word "non-deterministic" means that the output can change when input is the same

### Automation

- The word "automatic" means that proofs are done automatically
- The word "assistant" means that you have to prove manually, but proof check is automated

### Example solvers

| Solver   | Keywords |
| -------- | -------- |
| [Pocket-Prover](https://github.com/advancedresearch/pocket_prover) | Cl, Bf, Det for PL, NDet for PSQ, Au |
| [Monotonic-Solver](https://github.com/advancedresearch/monotonic_solver) | Ge, Mo, Au |
| [Linear-Solver](https://github.com/advancedresearch/linear_solver) | Ge, Li, Au |
| [Hooo](https://github.com/advancedresearch/hooo) | Co, Det, As |

| Keyword | Description       |
| ------- | ----------------- |
| Ge      | Generic           |
| Cl      | Classical         |
| Co      | Constructive      |
| Bf      | Brute force       |
| Mo      | Monotonic         |
| Li      | Linear            |
| Det     | Deterministic     |
| NDet    | Non-deterministic |
| Au      | Automatic         |
| As      | Assistant         |

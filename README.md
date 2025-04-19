# Simulation Engine for Mutated Stable Marriage Problem

## Objective

To develop a simulation engine in Python which can mimic complex mutations of the simple one‑to‑one stable marriage problem initially envisioned by Gale‑Shapley. Specifically, this engine should be able to adapt Gale and Shapley’s game‑theoretic constructs to incorporate practical heuristics and assumptions about the ways in which marriage/dating markets actually function.

The engine should eventually be able to handle and adopt additional constraints on preference orderings:

- Similarity between subsets of preference orderings  
- Varying degrees of non‑transitivity  
- Groups of preference orderings that obey certain probability distributions  
- Other scenarios to be determined  

It should also handle constraints on the matching market itself:

- Dynamic allocation of proposers/proposees throughout the algorithm  
- Failure to reach a stable matching within a finite number of steps  
- Modeling the cost of switching partners  
- Finding points of equilibrium without a strictly stable matching  
- Uneven numbers of proposers/proposees  

> **Note:** [This video](https://www.youtube.com/watch?v=h8MCtdYS0vo&ab_channel=selcukozyurt) provides an excellent overview of the type of thinking that this engine will attempt to mimic.

---

## Implementation and Design

Because the engine must support a wide variety of edge cases and research questions, its development will follow an **iterative** & **modular** process:

1. **Iterative Development**  
   - Each iteration tackles a specific variant or edge case of the stable marriage problem.  
   - Modular design ensures minimal refactoring is needed when adding new features.

2. **Core Design Principles**  
   - **Object‑Oriented Modeling** for all data quantities (e.g., Agents, Preferences, Markets).  
   - **Functions‑as‑Objects** to represent and mutate processes (e.g., proposal rules, cost functions).  
   - **Python Advantages**:  
     - Native support for classes and first‑class functions.  
     - Rich ecosystem for probabilistic and cost‑modeling libraries.

### Simulation Entrypoint

- A single `Simulation` class/method serves as the common entrypoint for all scenarios.  
- **Mutations** can be applied to:
  - **Data objects** (e.g., adding “empty set” to preference lists)  
  - **Data processes** (e.g., custom proposal order)  
  - **Interactions** between data and processes  
- Mutations may be introduced:
  - **Pre‑execution** (compilation‑time)  
  - **During execution** (runtime)

### Output & Analytics

The engine must support viewable metrics such as:

- Matching results at any iteration  
- Property values of any object (e.g., current partner, cost incurred)  
- Outputs of any process function (e.g., total switching cost)

The engine remains **agnostic** to implementation specifics beyond these core inputs and outputs.

---

## Starting Point

A practical first scenario to implement:

1. **Empty‑Set Preferences**  
   Insert an “empty set” option into each agent’s preference ordering to model preferring singlehood over undesirable matches.

2. **Fixed Partner‑Switching Cost**  
   Define a cost function \( f(n) = c \) where each downward step in an agent’s preference list incurs a constant cost \( c \).

> Focusing on this scenario will exercise the core abstractions (agents, preferences, mutations, and analytics) and provide a solid foundation for more advanced extensions.


# Environment
To activate environment, type `conda activate shapleyEnv ` and to deactivate type `conda deactivate`
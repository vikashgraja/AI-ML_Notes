# AI

### Search

**1. Informed Search:**
- **Definition:** Uses problem-specific knowledge to find solutions more efficiently than uninformed search.
- **Types:**
  - **Greedy Best-First Search:** Chooses the node that appears to be closest to the goal based on a heuristic function.
    ```python
    from queue import PriorityQueue
    def greedy_best_first_search(start, goal, h):
        frontier = PriorityQueue()
        frontier.put((h(start), start))
        while not frontier.empty():
            _, current = frontier.get()
            if current == goal:
                return current
            for neighbor in neighbors(current):
                frontier.put((h(neighbor), neighbor))
    ```
  - **A* Search:** Uses both the cost to reach the node and the heuristic to estimate the cost to the goal.
    ```python
    from queue import PriorityQueue
    def a_star_search(start, goal, h):
        frontier = PriorityQueue()
        frontier.put((0, start))
        came_from = {start: None}
        cost_so_far = {start: 0}
        while not frontier.empty():
            _, current = frontier.get()
            if current == goal:
                return current
            for neighbor in neighbors(current):
                new_cost = cost_so_far[current] + cost(current, neighbor)
                if neighbor not in cost_so_far or new_cost < cost_so_far[neighbor]:
                    cost_so_far[neighbor] = new_cost
                    priority = new_cost + h(neighbor)
                    frontier.put((priority, neighbor))
                    came_from[neighbor] = current
    ```

**2. Uninformed Search:**
- **Definition:** Searches without any domain-specific knowledge.
- **Types:**
  - **Breadth-First Search (BFS):** Explores all nodes at the present depth before moving on to nodes at the next depth level.
    ```python
    from collections import deque
    def bfs(start, goal):
        frontier = deque([start])
        while frontier:
            current = frontier.popleft()
            if current == goal:
                return current
            for neighbor in neighbors(current):
                frontier.append(neighbor)
    ```
  - **Depth-First Search (DFS):** Explores as far as possible along each branch before backtracking.
    ```python
    def dfs(start, goal):
        frontier = [start]
        while frontier:
            current = frontier.pop()
            if current == goal:
                return current
            for neighbor in neighbors(current):
                frontier.append(neighbor)
    ```

**3. Adversarial Search:**
- **Definition:** Used in games and scenarios where opponents are trying to defeat each other.
- **Types:**
  - **Minimax Algorithm:** Assumes both players play optimally to minimize the opponent's maximum payoff.
    ```python
    def minimax(node, depth, maximizingPlayer):
        if depth == 0 or is_terminal(node):
            return evaluate(node)
        if maximizingPlayer:
            maxEval = float('-inf')
            for child in children(node):
                eval = minimax(child, depth - 1, False)
                maxEval = max(maxEval, eval)
            return maxEval
        else:
            minEval = float('inf')
            for child in children(node):
                eval = minimax(child, depth - 1, True)
                minEval = min(minEval, eval)
            return minEval
    ```

### Logic

**1. Propositional Logic:**
- **Definition:** Deals with propositions which can be either true or false.
- **Syntax:**
  - **Literals:** Basic propositions (e.g., $\ P, Q $).
  - **Operators:** NOT ($\\neg$), AND ($\\land$), OR ($\\lor$), IMPLIES ($\\to$), BICONDITIONAL ($\\leftrightarrow$).
- **Example:** $\ \neg P \land (Q \to R) $

**2. Predicate Logic:**
- **Definition:** Extends propositional logic by dealing with predicates and quantifiers.
- **Syntax:**
  - **Predicates:** Functions that return true or false (e.g., $\ P(x), Q(x, y) $).
  - **Quantifiers:** Universal ($\\forall$) and existential ($\\exists$).
- **Example:** $\ \forall x (P(x) \to Q(x)) $

### Reasoning Under Uncertainty

**1. Conditional Independence Representation:**
- **Definition:** Two variables $\ A $ and $\ B $ are conditionally independent given a third variable $\ C $ if $\ P(A, B \mid C) = P(A \mid C) P(B \mid C) $.

**2. Exact Inference through Variable Elimination:**
- **Definition:** An algorithm for exact inference in Bayesian networks.
- **Steps:**
  - **Eliminate:** Sum out variables not in the query or evidence.
  - **Multiply:** Combine factors by multiplication.
- **Example:**
  ```python
  def variable_elimination(bn, query, evidence):
      for var in bn.variables:
          if var not in query and var not in evidence:
              factors = [f for f in bn.factors if var in f.variables]
              new_factor = multiply_factors(factors)
              summed_out = sum_out(new_factor, var)
              bn.factors = [f for f in bn.factors if var not in f.variables] + [summed_out]
      return normalize([f for f in bn.factors if query in f.variables])
  ```

**3. Approximate Inference through Sampling:**
- **Definition:** Uses random samples to estimate the distribution of variables in a Bayesian network.
- **Types:**
  - **Monte Carlo Sampling:** Generates random samples to approximate the distribution.
  - **Gibbs Sampling:** Iteratively samples from the conditional distribution of each variable given the current values of the other variables.
- **Example:**
  ```python
  import random
  def gibbs_sampling(bn, query, evidence, num_samples):
      samples = []
      for _ in range(num_samples):
          sample = {var: random.choice([0, 1]) for var in bn.variables}
          for var in bn.variables:
              sample[var] = sample_from_conditional(bn, var, sample)
          samples.append(sample)
      return estimate_distribution(samples, query)
  ```

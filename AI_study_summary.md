# Artificial Intelligence – Study Summary

**Based on:** Russell, S. J., & Norvig, P. (2021). *Artificial Intelligence: A Modern Approach* (4th ed.). Pearson.

This is a simplified revision guide. It follows the course learning outcomes (R1–R5, R8–R10, R12). Chapter numbers refer to the 4th edition. It is a study aid, not a replacement for the textbook, so use the book for proofs, full algorithms and exercises.

## Table of contents

1. [R1 – Historical background of AI](#r1--historical-background-of-ai)
2. [R2 – Ethical considerations](#r2--ethical-considerations)
3. [R3 – State space of a problem](#r3--state-space-of-a-problem)
4. [R4 – Brute-force (uninformed) search](#r4--brute-force-uninformed-search)
5. [R5 – Heuristic (informed) search](#r5--heuristic-informed-search)
6. [R8 – Logic as knowledge representation](#r8--logic-as-knowledge-representation)
7. [R9 – Probabilistic reasoning](#r9--probabilistic-reasoning)
8. [R10 – Bayes theorem and Bayesian networks](#r10--bayes-theorem-and-bayesian-networks)
9. [R12 – Neural networks](#r12--neural-networks)
10. [Cheat sheets](#cheat-sheets)
11. [Self-check questions](#self-check-questions)

---

## R1 – Historical background of AI

*(Textbook: Chapter 1, "Introduction")*

### What is AI?

There are four classic ways to define AI, depending on whether we care about **thinking vs. acting** and **human-like vs. rational**:

| | Human-like | Rational |
|---|---|---|
| **Thinking** | Thinking humanly (cognitive modelling) | Thinking rationally ("laws of thought", logic) |
| **Acting** | Acting humanly (Turing Test) | Acting rationally (rational agent) |

The book adopts the **rational agent** view. An agent is something that perceives its environment and acts. A **rational agent** acts to achieve the best expected outcome, given what it knows. This is more general than imitating humans and is also easier to define mathematically.

### The Turing Test (1950)

Alan Turing proposed an "imitation game". A human interrogator chats (by text) with a hidden human and a hidden machine. If the interrogator cannot reliably tell which is which, the machine passes. To pass, a machine would need natural language processing, knowledge representation, automated reasoning and machine learning. The *total* Turing Test adds computer vision and robotics.

### Foundations of AI (other disciplines that contributed)

- **Philosophy:** logic, reasoning, the mind–body problem, rationalism vs. empiricism.
- **Mathematics:** formal logic, computation (algorithms, Turing machines), probability, decidability, tractability (NP-completeness).
- **Economics:** decision theory, utility, game theory.
- **Neuroscience:** how brains process information (neurons, synapses).
- **Psychology:** behaviourism, cognitive psychology.
- **Computer engineering:** hardware powerful enough to run AI.
- **Control theory:** systems that optimise behaviour over time via feedback.
- **Linguistics:** language and knowledge representation.

### Timeline of AI

| Period | What happened |
|---|---|
| **1943** | McCulloch & Pitts: first mathematical model of an artificial neuron. |
| **1950** | Turing's paper "Computing Machinery and Intelligence". |
| **1950s** | Early neural network machines; early game-playing programs (e.g. checkers). |
| **1956** | **Dartmouth workshop**. The term "Artificial Intelligence" was coined (John McCarthy). Considered the birth of AI as a field. |
| **1956–1969** | "Look, Ma, no hands!" era. Early successes: Logic Theorist, General Problem Solver, Lisp language, the first perceptrons. Optimism was very high. |
| **1966–1973** | **Reality check.** Programs worked only on toy problems. Machine translation failed. Combinatorial explosion became clear. The Lighthill report (UK) cut funding. Minsky & Papert (1969) showed limits of single-layer perceptrons. |
| **1969–1986** | **Expert systems** (e.g. DENDRAL, MYCIN): rule-based systems that capture the knowledge of human experts. Commercial boom in the early 1980s. |
| **1986–present** | **Return of neural networks.** Back-propagation was rediscovered. Connectionism became popular. |
| **Late 1980s–1990s** | **AI winter**: expert systems proved brittle and costly to maintain, and funding collapsed. Rise of the **probabilistic approach** (Bayesian networks, Judea Pearl), hidden Markov models, and a more scientific, statistical methodology. |
| **2001–present** | **Big data.** Large datasets mattered more than clever algorithms. |
| **2011–present** | **Deep learning.** GPUs plus big data plus better algorithms. Breakthroughs in image recognition (ImageNet 2012), speech recognition, machine translation, game playing (Deep Blue 1997 in chess, AlphaGo 2016 in Go), and later large language models and generative AI. |

### Key ideas to remember

- AI went through **cycles of optimism and disappointment** ("AI summers and winters").
- Early AI focused on **symbolic, logic and rule-based methods**. Modern AI is dominated by **statistical, data-driven learning**.
- The field moved from "build one general intelligence" to many **specialised, useful applications** (search engines, recommendation, vision, speech, robotics, medicine).
- Today's debate includes the **standard model** (build machines that optimise a fixed objective) and its problems, such as the **value alignment problem**: a fixed objective may not capture what humans really want.

---

## R2 – Ethical considerations

*(Textbook: Chapter 27, "Philosophy, Ethics, and Safety of AI"; also Chapter 28)*

### Philosophical background

- **Weak AI hypothesis:** machines can *act as if* they were intelligent.
- **Strong AI hypothesis:** machines can *actually think* (have a mind, consciousness).
- **Chinese Room argument (Searle):** following symbol-manipulation rules is not the same as understanding. Syntax does not give semantics.
- **Consciousness and qualia:** it is unclear whether machines could ever have subjective experience.

### Main ethical issues

| Issue | Short explanation |
|---|---|
| **Lethal autonomous weapons** | Weapons that select and attack targets without human control. Questions about accountability, escalation, and the ability to follow the laws of war. |
| **Surveillance and privacy** | AI makes mass surveillance cheap (face recognition, tracking). Risks to civil liberties and data protection. |
| **Fairness and bias** | Models learn from historical data, which may contain human prejudice. They may discriminate (hiring, credit scoring, policing, sentencing). Bias can come from the data, the labels, the features or the objective. There are several mathematical definitions of fairness, and they cannot all be satisfied at once. |
| **Trust, transparency, explainability** | Many models (e.g. deep networks) are "black boxes". People affected by decisions may have a right to an explanation. |
| **Accountability** | Who is responsible when an AI system causes harm: the developer, the owner, the user? |
| **Impact on employment** | Automation may remove some jobs and create others. It raises questions of inequality and retraining. |
| **Safety and robustness** | Systems can fail in unexpected situations, be fooled by adversarial examples, or be attacked. |
| **Misinformation and deepfakes** | Generative AI can produce convincing fake text, images, audio and video. |
| **Copyright and data use** | Training on human-made works raises legal and ethical questions. |
| **Environmental cost** | Training large models consumes a lot of energy. |
| **Human–AI interaction** | Over-reliance on AI, manipulation, relationships with robots and chatbots. |
| **Existential and long-term risk** | Concern that very capable systems pursuing the wrong goals could be dangerous. |

### Principles of ethical AI

Many organisations publish similar guidelines. Common themes:

- **Fairness** (non-discrimination)
- **Transparency** and **explainability**
- **Accountability** and human oversight
- **Privacy** and data governance
- **Safety**, security and robustness
- **Beneficence**: AI should benefit humanity
- **Human control** and respect for human rights

### Value alignment and the "King Midas problem"

If we give a machine a goal that is slightly wrong, a very capable machine can pursue it in harmful ways (like King Midas, who wished everything he touched turned to gold). The book argues for **provably beneficial AI**: machines that are *uncertain about human preferences* and learn them by observing humans, so they remain open to correction.

### Key ideas to remember

- Ethics is not an add-on. It should be considered **at design time**.
- Bias in, bias out: **data quality and representativeness matter**.
- Technical fixes (e.g. fairness metrics) help but do not replace social and legal discussion.

---

## R3 – State space of a problem

*(Textbook: Chapter 3, "Solving Problems by Searching", sections 3.1–3.2)*

### Problem-solving agents

A **problem-solving agent** works in an environment that is (usually) **fully observable, deterministic, known, discrete and static**. It:

1. **Formulates a goal.**
2. **Formulates the problem** (what states and actions to consider).
3. **Searches** for a sequence of actions that reaches the goal.
4. **Executes** the solution.

### Formal definition of a search problem

A problem is defined by five components:

1. **Initial state**, where the agent starts.
2. **Actions** `ACTIONS(s)`: the actions available in state `s`.
3. **Transition model** `RESULT(s, a)`: the state that results from doing action `a` in state `s`.
4. **Goal test**: is this state a goal? (Either an explicit list of goal states or a property.)
5. **Action cost** (path cost) `c(s, a, s')`: how expensive a step is. Path cost is the sum of step costs.

### State space

> The **state space** is the set of all states reachable from the initial state by any sequence of actions.

It can be viewed as a **graph**:

- **Nodes** = states
- **Edges** = actions (transitions)

A **path** is a sequence of states connected by actions. A **solution** is a path from the initial state to a goal state. An **optimal solution** has the lowest path cost.

### Examples

| Problem | State | Actions | Goal | Cost |
|---|---|---|---|---|
| **Route finding (Romania map)** | Current city | Drive to a neighbouring city | Reach Bucharest | Distance |
| **8-puzzle** | Arrangement of 8 tiles + blank | Move blank up/down/left/right | Tiles in order | 1 per move |
| **Vacuum world** | Robot location + dirt status | Left, Right, Suck | All squares clean | 1 per action |
| **8-queens** | Placement of queens on board | Add a queen to a square | 8 queens, none attacking | – |

### Abstraction

Real problems are too detailed (weather, road conditions, radio on…). We **abstract** by removing irrelevant detail from both the **state** and the **actions**. A good abstraction is **valid** (every abstract solution can be turned into a real one) and **useful** (easier than the original problem).

### State space size

The state space can be huge. The 8-puzzle has 9!/2 = 181,440 reachable states, the 15-puzzle has about 10¹³, and the 24-puzzle about 10²⁵. This explains why we need smart search.

### Search tree vs. state space

- The **state space** is the graph of states.
- The **search tree** is the tree of paths we explore. One state can appear many times in the tree (via different paths).
- A **search node** stores: the state, its parent node, the action that led to it, and the path cost `g(n)`.
- **Frontier** (open list): nodes generated but not yet expanded.
- **Explored set** (closed list): states already expanded. Using it avoids **repeated states** and loops (graph search vs. tree search).
- **Expanding** a node means applying all actions to create child nodes.

### Measuring performance of search algorithms

| Property | Meaning |
|---|---|
| **Completeness** | Does it always find a solution if one exists? |
| **Optimality** | Does it find the lowest-cost solution? |
| **Time complexity** | How many nodes are generated? |
| **Space complexity** | How many nodes must be stored in memory? |

Symbols: `b` = branching factor (max number of children per node), `d` = depth of the shallowest goal, `m` = maximum depth of the tree, `C*` = cost of the optimal solution, `ε` = minimum step cost.

---

## R4 – Brute-force (uninformed) search

*(Textbook: Chapter 3, section 3.4)*

"Uninformed" means the algorithm has **no information about how close a state is to the goal**, only the problem definition.

### Generic best-first idea

All search algorithms follow one skeleton:

```
frontier ← {initial node}
explored ← {}
loop:
    if frontier is empty: return failure
    node ← choose and remove a node from frontier
    if goal-test(node.state): return solution(node)
    add node.state to explored
    for each action a in ACTIONS(node.state):
        child ← child-node(node, a)
        if child.state not in explored and not in frontier:
            add child to frontier
```

The algorithms differ only in **which node is chosen next**, i.e. in the data structure of the frontier.

### Breadth-First Search (BFS)

- **Idea:** expand the shallowest nodes first (level by level).
- **Frontier:** FIFO **queue**.
- **Complete?** Yes (if `b` is finite).
- **Optimal?** Yes **if all step costs are equal** (it finds the shallowest goal).
- **Time:** O(b^d)
- **Space:** O(b^d). This is its main problem: it keeps all nodes of a level in memory.

### Uniform-Cost Search (UCS)

- **Idea:** expand the node with the **lowest path cost g(n)** (Dijkstra's algorithm).
- **Frontier:** **priority queue** ordered by g(n).
- **Complete?** Yes (if step costs ≥ ε > 0).
- **Optimal?** Yes (for any positive step costs). The goal test is applied when a node is *expanded* (not generated), so a cheaper path is not missed.
- **Time/Space:** O(b^(1+⌊C*/ε⌋))
- With equal step costs it behaves like BFS.

### Depth-First Search (DFS)

- **Idea:** expand the deepest node first (go down a branch until it ends, then backtrack).
- **Frontier:** LIFO **stack** (or recursion).
- **Complete?** No for infinite or cyclic graphs, but yes in finite state spaces with an explored set (graph search).
- **Optimal?** No (may return a deep, expensive solution first).
- **Time:** O(b^m). This can be much worse than b^d if m ≫ d.
- **Space:** O(b·m). This is its main advantage: **linear memory**.
- **Backtracking search** is a DFS variant that generates one successor at a time (O(m) memory).

### Depth-Limited Search (DLS)

DFS with a predefined **depth limit ℓ**: nodes at depth ℓ are treated as if they have no children. It solves the infinite-path problem but is incomplete if ℓ < d, and non-optimal if ℓ > d.

### Iterative Deepening Search (IDS / IDDFS)

- **Idea:** run depth-limited search with limit 0, then 1, then 2, … until a goal is found.
- Combines the **memory efficiency of DFS** with the **completeness and optimality of BFS** (with equal step costs).
- **Complete?** Yes (finite b).
- **Optimal?** Yes (equal step costs).
- **Time:** O(b^d). Re-generating upper levels is wasteful but cheap, because most nodes are at the bottom level.
- **Space:** O(b·d)
- Typically the **preferred uninformed method** when the search space is large and the solution depth is unknown.

### Bidirectional search (extra)

Search forward from the start and backward from the goal at the same time and meet in the middle. Time and space O(b^(d/2)), which is far better than O(b^d), but it needs the ability to search backwards.

### Comparison table

| Algorithm | Complete? | Optimal? | Time | Space |
|---|---|---|---|---|
| **BFS** | Yes | Yes (equal costs) | O(b^d) | O(b^d) |
| **Uniform-cost** | Yes | Yes | O(b^(1+⌊C*/ε⌋)) | O(b^(1+⌊C*/ε⌋)) |
| **DFS** | No (in general) | No | O(b^m) | O(b·m) |
| **Depth-limited** | No | No | O(b^ℓ) | O(b·ℓ) |
| **Iterative deepening** | Yes | Yes (equal costs) | O(b^d) | O(b·d) |
| **Bidirectional** | Yes | Yes (equal costs) | O(b^(d/2)) | O(b^(d/2)) |

### Worked example: BFS vs. DFS order

Tree: A has children B, C. B has children D, E. C has children F, G. Goal = G.

- **BFS order:** A, B, C, D, E, F, G
- **DFS order:** A, B, D, E, C, F, G

### Implementation tips (for coding assignments)

- Represent a **node** as an object/struct: `state`, `parent`, `action`, `path_cost`.
- BFS → `collections.deque` (Python); DFS → list as a stack; UCS/A* → `heapq` (priority queue).
- Use a **set** for explored states (states must be hashable, e.g. tuples).
- Reconstruct the solution by following `parent` pointers from the goal back to the start and reversing.

---

## R5 – Heuristic (informed) search

*(Textbook: Chapter 3, section 3.5–3.6)*

**Informed search** uses **domain knowledge** (a heuristic) to decide which node looks most promising.

### Evaluation function and heuristic

- **f(n)** = evaluation function used to choose the next node (lowest f first).
- **h(n)** = **heuristic function** = *estimated* cost of the cheapest path from node n to a goal. Always `h(goal) = 0`.
- **g(n)** = actual cost from the start to node n.

### Greedy Best-First Search

- **Evaluation:** f(n) = h(n). Expand the node that *seems* closest to the goal.
- **Complete?** No in general (can loop in graph search without a check). Yes in finite spaces with repeated-state checking.
- **Optimal?** No. It ignores the cost already paid.
- **Time/Space:** O(b^m) worst case, but a good heuristic improves this a lot.
- Fast but can be misled. Example: going straight toward the goal city into a dead end.

### A\* Search

- **Evaluation:** **f(n) = g(n) + h(n)** = estimated cost of the cheapest solution *through* n.
- Implementation: like uniform-cost search but ordered by f instead of g. Uses a priority queue.
- **Complete?** Yes (finite branching, positive step costs).
- **Optimal?** Yes, **if the heuristic is admissible** (tree search) or **consistent** (graph search).
- **Space:** O(b^d). This is the main drawback, as A\* keeps all generated nodes in memory.
- A\* is **optimally efficient**: no other optimal algorithm using the same heuristic is guaranteed to expand fewer nodes.

### Admissible and consistent heuristics

| Property | Definition | Meaning |
|---|---|---|
| **Admissible** | h(n) ≤ h\*(n) for every n (h\* = true cost to goal) | Never **overestimates** the true cost. It is "optimistic". |
| **Consistent (monotonic)** | h(n) ≤ c(n, a, n') + h(n') for every n and successor n' | A form of the triangle inequality. f(n) never decreases along a path. |

- **Every consistent heuristic is admissible** (the reverse is not always true).
- With a consistent heuristic, the first time A\* expands a node it has found the optimal path to it. Therefore no re-opening is needed.

### Why admissibility gives optimality (intuition)

Suppose A\* is about to return a suboptimal goal G₂ with cost g(G₂) > C\*. Some node n on the optimal path is still in the frontier. Because h is admissible, f(n) = g(n) + h(n) ≤ C\* < f(G₂). So n would be expanded *before* G₂. Contradiction.

### Examples of heuristics

**For the 8-puzzle:**

- **h₁ = number of misplaced tiles.** Admissible (every misplaced tile needs ≥ 1 move).
- **h₂ = sum of Manhattan distances** of tiles to their goal squares. Admissible, and more informed than h₁.

**For route finding:** **straight-line distance** to the goal. Admissible, since the shortest path between two points is a straight line.

### Heuristic quality

- **Dominance:** if h₂(n) ≥ h₁(n) for all n (both admissible), h₂ **dominates** h₁ and A\* with h₂ expands fewer nodes. Larger (but still admissible) values are better.
- **Effective branching factor b\*:** the branching factor a uniform tree would need to contain N+1 nodes at depth d. Values near 1 mean a good heuristic.
- **Creating heuristics via relaxed problems:** remove constraints from the problem. The exact cost of the relaxed problem is an admissible (and consistent) heuristic for the original. For example, "a tile can move to any square" gives h₁, and "a tile can move to any adjacent square, even if occupied" gives h₂.
- **Pattern databases:** pre-compute exact costs for subproblems (e.g. only some tiles).
- **Combining heuristics:** h(n) = max(h₁(n), h₂(n), …) stays admissible.

### Memory-bounded variants (short)

- **IDA\*** (iterative-deepening A\*): like IDS but the cutoff is an f-value instead of depth. Low memory.
- **RBFS** and **SMA\***: other memory-limited best-first methods.
- **Weighted A\***: f(n) = g(n) + W·h(n) with W > 1. Faster but only *bounded suboptimal*.

### Quick comparison

| Algorithm | f(n) | Complete | Optimal |
|---|---|---|---|
| Uniform-cost | g(n) | Yes | Yes |
| Greedy best-first | h(n) | No (in general) | No |
| A\* | g(n) + h(n) | Yes | Yes (admissible/consistent h) |

### Worked mini-example

Nodes: S→A (cost 1), S→B (cost 4), A→G (cost 10), B→G (cost 2). Heuristics: h(S)=5, h(A)=2, h(B)=2, h(G)=0.

- **Greedy:** from S, A and B both have h=2. It picks one, say A, then goes to G with total cost 1+10 = **11** (not optimal).
- **A\*:** f(A) = 1+2 = 3, f(B) = 4+2 = 6. It expands A, giving G with f = 11. It still has B in the frontier with f = 6 < 11, so it expands B, giving G with f = 4+2 = **6**. It returns the optimal path S→B→G with cost **6**.

---

## R8 – Logic as knowledge representation

*(Textbook: Chapters 7, 8, 9, 10)*

### Knowledge-based agents

A **knowledge-based agent** has a **knowledge base (KB)**: a set of sentences in a formal language. It interacts through two operations:

- **TELL(KB, sentence):** add knowledge.
- **ASK(KB, query):** ask what follows from the KB.

Advantage: the **declarative approach**. We tell the agent *what is true*, and it figures out what to do.

### Key logical concepts

| Concept | Meaning |
|---|---|
| **Syntax** | Which sentences are well-formed. |
| **Semantics** | The meaning of sentences, i.e. their truth in each *model* (possible world). |
| **Model** | An assignment of truth values (a possible world) in which every sentence is true or false. |
| **Entailment** KB ⊨ α | α is true in **all models** in which KB is true. |
| **Inference** KB ⊢ α | Deriving α from KB using an algorithm. |
| **Sound** | The inference procedure only derives entailed sentences (no false conclusions). |
| **Complete** | The procedure can derive *every* entailed sentence. |
| **Valid** | True in all models (a tautology), e.g. P ∨ ¬P. |
| **Satisfiable** | True in at least one model. |
| **Unsatisfiable** | True in no model (a contradiction). |
| **Grounding** | How sentences relate to the real world (via sensors and learning). |

Useful fact: **KB ⊨ α iff (KB ∧ ¬α) is unsatisfiable.** This is the basis of *proof by contradiction* (refutation).

### Propositional logic

**Syntax:**

- **Atomic sentences:** propositional symbols (P, Q, Wumpus₁,₃…) or the constants True/False.
- **Complex sentences** built with connectives:
  - ¬ not, ∧ and, ∨ or, ⇒ implies, ⇔ if and only if.

**Semantics (truth table basics):**

| P | Q | ¬P | P∧Q | P∨Q | P⇒Q | P⇔Q |
|---|---|---|---|---|---|---|
| F | F | T | F | F | **T** | T |
| F | T | T | F | T | **T** | F |
| T | F | F | F | T | **F** | F |
| T | T | F | T | T | T | T |

Remember: **P ⇒ Q is false only when P is true and Q is false.**

**Important equivalences:**

- De Morgan: ¬(P ∧ Q) ≡ ¬P ∨ ¬Q; ¬(P ∨ Q) ≡ ¬P ∧ ¬Q
- Implication: P ⇒ Q ≡ ¬P ∨ Q
- Contrapositive: P ⇒ Q ≡ ¬Q ⇒ ¬P
- Biconditional: P ⇔ Q ≡ (P ⇒ Q) ∧ (Q ⇒ P)
- Double negation: ¬¬P ≡ P

**Inference methods:**

1. **Model checking (truth table enumeration):** check all 2ⁿ models. Sound and complete but exponential.
2. **Inference rules:**
   - **Modus Ponens:** from α ⇒ β and α, infer β.
   - **And-elimination:** from α ∧ β, infer α.
   - **Resolution:** from (A ∨ B) and (¬B ∨ C), infer (A ∨ C).
3. **Resolution algorithm:**
   - Convert KB ∧ ¬α into **Conjunctive Normal Form (CNF)**: a conjunction of clauses, each clause a disjunction of literals.
   - Repeatedly resolve pairs of clauses. If the **empty clause** is derived, KB ⊨ α.
   - Resolution is **sound and complete** for propositional logic.
4. **Horn clauses:** clauses with at most one positive literal, e.g. (A ∧ B ⇒ C). Inference is possible in linear time using **forward chaining** (data-driven) and **backward chaining** (goal-driven).
5. **SAT solvers:** DPLL and WalkSAT. Modern solvers handle large problems efficiently.

**CNF conversion steps:**

1. Eliminate ⇔ and ⇒.
2. Move ¬ inward (De Morgan, double negation).
3. Distribute ∨ over ∧.

**Wumpus world** is the classic example. The agent explores a cave with pits, a wumpus and gold, using percepts (breeze, stench, glitter) and propositional rules such as `B₁,₁ ⇔ (P₁,₂ ∨ P₂,₁)`.

**Limitation:** propositional logic is **not expressive enough**. You need a separate sentence for every square, every time step and every object. It cannot say "all squares next to a pit are breezy" in one statement.

### First-order logic (FOL, predicate calculus)

FOL talks about **objects**, **relations** and **functions**, so it is far more expressive.

**Syntax elements:**

| Element | Examples |
|---|---|
| **Constants** | John, Richard, 2 |
| **Variables** | x, y |
| **Predicates** (relations) | Brother(x, y), King(x) |
| **Functions** | LeftLeg(x), Father(x) |
| **Equality** | x = y |
| **Connectives** | ¬ ∧ ∨ ⇒ ⇔ |
| **Quantifiers** | ∀ (for all), ∃ (there exists) |

**Terms** refer to objects (constants, variables, functions applied to terms). **Atomic sentences** are predicates applied to terms (e.g. `Brother(Richard, John)`).

**Quantifiers:**

- **Universal (∀x P(x)):** P holds for every object. Typical form: `∀x King(x) ⇒ Person(x)`. Use ⇒ with ∀ (not ∧).
- **Existential (∃x P(x)):** P holds for at least one object. Typical form: `∃x Crown(x) ∧ OnHead(x, John)`. Use ∧ with ∃ (not ⇒).
- **Duality:** ∀x ¬P ≡ ¬∃x P, and ∃x ¬P ≡ ¬∀x P.
- **Order matters:** `∀x ∃y Loves(x, y)` ("everybody loves somebody") is not the same as `∃y ∀x Loves(x, y)` ("somebody is loved by everyone").

**Common mistakes:**

- ∀x King(x) ∧ Person(x), which says everything is a king and a person. Wrong.
- ∃x King(x) ⇒ Person(x), which is trivially true if anything is not a king. Wrong.

**Example translations:**

| English | FOL |
|---|---|
| Every student passed. | ∀x Student(x) ⇒ Passed(x) |
| Some student failed. | ∃x Student(x) ∧ ¬Passed(x) |
| Brothers are siblings. | ∀x,y Brother(x, y) ⇒ Sibling(x, y) |
| Sibling is symmetric. | ∀x,y Sibling(x, y) ⇔ Sibling(y, x) |
| Nobody likes taxes. | ¬∃x Likes(x, Taxes) |

### Inference in FOL

- **Universal instantiation (UI):** from ∀x P(x), infer P(c) for any constant c.
- **Existential instantiation (EI):** from ∃x P(x), infer P(k) for a *new* constant k (Skolem constant).
- **Unification:** finding a substitution θ that makes two expressions identical. For example, `Knows(John, x)` and `Knows(y, Mother(y))` unify with θ = {y/John, x/Mother(John)}.
- **Generalised Modus Ponens:** a lifted version of Modus Ponens using unification.
- **Forward chaining / backward chaining:** for definite clauses (e.g. Prolog uses backward chaining).
- **Resolution for FOL:** convert to CNF (including Skolemisation to remove ∃), then resolve using unification. It is **refutation-complete**.
- **Gödel's results:** FOL entailment is **semi-decidable**. Algorithms can prove every entailed sentence, but cannot always decide that a non-entailed sentence is non-entailed.

### Knowledge engineering (Chapter 10, brief)

Steps: identify the task → assemble relevant knowledge → decide on a vocabulary (predicates, functions, constants) → encode general knowledge → encode the problem instance → pose queries → debug the KB.

**Ontologies** organise concepts into categories (e.g. Animal → Mammal → Dog). Categories support inheritance, so a property of a category applies to its members. Other topics: events, time, mental objects, default reasoning.

### Summary table: Propositional vs. First-order logic

| | Propositional logic | First-order logic |
|---|---|---|
| Ontology | Facts (true/false) | Objects, relations, functions |
| Expressiveness | Limited | High |
| Inference | Decidable (SAT is NP-complete) | Semi-decidable |
| Quantifiers | None | ∀, ∃ |

---

## R9 – Probabilistic reasoning

*(Textbook: Chapter 12 "Quantifying Uncertainty", Chapter 13 "Probabilistic Reasoning")*

### Why probability?

Real agents face **uncertainty** because of partial observability, noisy sensors, nondeterministic outcomes, and laziness or ignorance (too many factors to list). Pure logic can't handle degrees of belief. For example, "the patient has a toothache, therefore a cavity" is not strictly true.

**Probability theory** summarises uncertainty. The probability is the agent's **degree of belief** given the available evidence. Combined with **utility theory** (preferences), it gives **decision theory**: choose the action with the **maximum expected utility (MEU)**.

> Decision theory = probability theory + utility theory

### When to use probabilistic reasoning

Use it when:

- information is **incomplete or noisy** (medical diagnosis, sensors, spam filtering);
- outcomes are **non-deterministic** (games with chance, robot motion);
- you need to **quantify confidence** or compare alternatives under risk;
- the problem includes **learning from data**.

Use pure logic or search when the world is deterministic, fully observable, and rules are exact.

### Basic probability

- **Sample space Ω:** all possible worlds. **Event:** a subset of Ω.
- **Probability model:** each world ω has P(ω) with 0 ≤ P(ω) ≤ 1 and Σ P(ω) = 1.
- **Kolmogorov axioms:**
  1. 0 ≤ P(A) ≤ 1
  2. P(True) = 1, P(False) = 0
  3. P(A ∨ B) = P(A) + P(B) − P(A ∧ B)
- **Negation:** P(¬A) = 1 − P(A)
- **Random variables** (e.g. Weather ∈ {sunny, rain, cloudy, snow}). A **probability distribution** gives P for each value.
- **Prior (unconditional) probability:** P(a), belief without any other information.
- **Posterior (conditional) probability:** P(a | b), belief in a given that b is known.

### Conditional probability and the product rule

- **Definition:** P(a | b) = P(a ∧ b) / P(b), for P(b) > 0
- **Product rule:** P(a ∧ b) = P(a | b) P(b) = P(b | a) P(a)
- **Chain rule:** P(X₁, …, Xₙ) = Π P(Xᵢ | X₁, …, Xᵢ₋₁)

### Joint distribution and inference by enumeration

The **full joint probability distribution** lists the probability of every combination of values of all variables. Any query can be answered from it.

- **Marginalisation (summing out):** P(Y) = Σ_z P(Y, z)
- **Conditioning:** P(Y) = Σ_z P(Y | z) P(z)
- **Normalisation:** P(X | e) = α · P(X, e), where α = 1 / P(e). We compute unnormalised values for every value of X, then scale them to sum to 1.

**Problem:** the joint table has 2ⁿ entries for n Boolean variables. It is not practical, so we need **independence** and compact models (Bayesian networks).

### Independence

- **Absolute independence:** A and B are independent if P(A | B) = P(A), equivalently P(A, B) = P(A) P(B). Independence reduces the table size greatly.
- **Conditional independence:** A and B are conditionally independent given C if P(A, B | C) = P(A | C) P(B | C). This is the most useful property in practice. For example, two symptoms may be independent given the disease.

### Expected utility (brief)

For action a with outcomes s' of probability P(s' | a) and utility U(s'):

> EU(a) = Σ_s' P(s' | a) · U(s')

A rational agent picks the action with maximum EU.

---

## R10 – Bayes theorem and Bayesian networks

*(Textbook: Chapter 12 section 12.5, Chapter 13)*

### Bayes' theorem

From the product rule P(a ∧ b) = P(a | b)P(b) = P(b | a)P(a):

> **P(a | b) = P(b | a) · P(a) / P(b)**

Terminology:

- **P(a)** = prior
- **P(b | a)** = likelihood
- **P(a | b)** = posterior
- **P(b)** = evidence (normalising constant)

**Why it is useful:** we often know the *causal* direction P(effect | cause) (e.g. symptoms given disease) from data, but we want the *diagnostic* direction P(cause | effect).

**Normalised form:** P(A | b) = α · P(b | A) · P(A)

**With multiple pieces of evidence** (and conditional independence given the cause, a **naive Bayes** model):

> P(Cause | e₁, …, eₙ) = α · P(Cause) · Π P(eᵢ | Cause)

### Worked example: medical test

A disease affects **1%** of people. A test has **90% sensitivity** (P(positive | disease) = 0.9) and a **9% false-positive rate** (P(positive | no disease) = 0.09). You test positive. What is P(disease | positive)?

1. P(D) = 0.01, P(¬D) = 0.99
2. P(+ | D) = 0.9, P(+ | ¬D) = 0.09
3. P(+) = 0.9 × 0.01 + 0.09 × 0.99 = 0.009 + 0.0891 = 0.0981
4. P(D | +) = 0.009 / 0.0981 ≈ **0.092 (about 9%)**

**Lesson:** even with a positive test, the probability is low because the **prior (base rate) is low**. Ignoring the base rate is the *base-rate fallacy*.

### Bayesian networks (belief networks)

A **Bayesian network** is a compact representation of a joint probability distribution.

**Structure:**

- A **directed acyclic graph (DAG)**.
- Each **node** is a random variable.
- Each **arrow** X → Y means X is a (direct) **parent** of Y (often a causal influence).
- Each node Xᵢ has a **conditional probability table (CPT)**: P(Xᵢ | Parents(Xᵢ)).

**Semantics:** the joint distribution is the product of local conditional probabilities:

> **P(x₁, …, xₙ) = Π P(xᵢ | parents(Xᵢ))**

**Compactness:** with n Boolean variables and at most k parents each, the network needs about n·2ᵏ numbers instead of 2ⁿ. For example, 30 variables with 5 parents each need under 1000 numbers instead of over a billion.

**Constructing a network:**

1. Choose the variables.
2. Order them (causes before effects gives the most compact network).
3. For each variable, pick its minimal set of parents so that it is conditionally independent of the other predecessors given the parents.
4. Fill in the CPTs.

### Classic example: the burglar alarm

Variables: **Burglary (B)**, **Earthquake (E)**, **Alarm (A)**, **JohnCalls (J)**, **MaryCalls (M)**.

Structure: B → A ← E; A → J; A → M.

CPTs (typical values):

- P(B) = 0.001, P(E) = 0.002
- P(A | B, E): TT 0.95, TF 0.94, FT 0.29, FF 0.001
- P(J | A): T 0.90, F 0.05
- P(M | A): T 0.70, F 0.01

**Joint probability example:** probability that the alarm sounded, both call, and there was no burglary or earthquake:

P(j, m, a, ¬b, ¬e) = P(j | a) P(m | a) P(a | ¬b, ¬e) P(¬b) P(¬e)
= 0.90 × 0.70 × 0.001 × 0.999 × 0.998 ≈ **0.000628**

### Conditional independence in networks

- A node is conditionally independent of its **non-descendants** given its **parents**.
- A node is conditionally independent of all other nodes given its **Markov blanket** (parents, children, and children's other parents).
- **d-separation:** a rule to read independence from the graph. Three basic patterns for A – B – C:

| Pattern | Name | A and C independent? |
|---|---|---|
| A → B → C | Chain | Dependent, but **independent given B** |
| A ← B → C | Common cause (fork) | Dependent, but **independent given B** |
| A → B ← C | Common effect (collider, v-structure) | Independent, but **dependent given B** (or a descendant of B). This is "explaining away". |

**Explaining away:** if the alarm rang, learning that there was an earthquake makes burglary *less* likely.

### Exact inference

**Inference by enumeration:** to compute P(X | e), sum the joint over hidden variables:

> P(X | e) = α Σ_y P(X, e, y)

Example: P(B | j, m) = α Σ_e Σ_a P(B) P(e) P(a | B, e) P(j | a) P(m | a). For the alarm network the result is about **P(Burglary | John and Mary call) ≈ 0.284**.

**Variable elimination:** a more efficient algorithm. Do the sums right-to-left, store intermediate results (**factors**), and avoid recomputation. Efficiency depends on the network structure (polytrees are tractable, while general exact inference is NP-hard).

### Approximate inference (brief)

For big networks, use **sampling (Monte Carlo)** methods:

- **Direct (prior) sampling:** sample from the network in topological order, and estimate probabilities by counting.
- **Rejection sampling:** discard samples inconsistent with the evidence.
- **Likelihood weighting:** fix the evidence variables and weight samples by the likelihood of the evidence.
- **MCMC (Gibbs sampling):** random walk through states.

### Extensions (mention only)

- **Dynamic / temporal models (Chapter 14):** hidden Markov models (HMMs), Kalman filters, dynamic Bayesian networks.
- **Learning Bayesian networks (Chapter 20):** learn the CPTs (and structure) from data.

### Key ideas to remember

- Bayesian networks = **graph structure + local CPTs**, which gives a compact full joint.
- **Edges encode direct dependence; missing edges encode conditional independence.**
- Bayes' theorem lets us **reason from effects to causes**.

---

## R12 – Neural networks

*(Textbook: Chapter 19 "Learning from Examples" sections 19.6–19.7; Chapter 21 "Deep Learning")*

### Machine learning basics (context)

- **Supervised learning:** learn a function from labelled examples (x, y). **Classification** gives discrete outputs and **regression** gives continuous outputs.
- **Training set** vs. **test set**: always evaluate on data not used in training.
- **Overfitting:** the model fits noise in the training data and performs poorly on new data. **Underfitting:** the model is too simple. Counter overfitting with more data, simpler models, **regularisation**, **dropout**, **early stopping** and **cross-validation** (validation set).

### The artificial neuron (unit)

A unit computes a weighted sum of its inputs and applies a nonlinear **activation function** g:

> **a = g(w · x + b) = g(Σᵢ wᵢ xᵢ + b)**

- **wᵢ** = weights, **b** = bias (threshold), **g** = activation function.
- Inspired loosely by biological neurons (dendrites = inputs, synapses = weights, axon = output).

**Common activation functions:**

| Function | Formula | Notes |
|---|---|---|
| **Threshold / step** | 1 if z > 0 else 0 | Original perceptron. Not differentiable. |
| **Sigmoid (logistic)** | 1 / (1 + e⁻ᶻ) | Output in (0, 1). Used for probabilities. Can suffer vanishing gradients. |
| **tanh** | (eᶻ − e⁻ᶻ)/(eᶻ + e⁻ᶻ) | Output in (−1, 1). |
| **ReLU** | max(0, z) | Simple, fast, the default in deep networks. |
| **Softmax** | e^(zᵢ) / Σ e^(zⱼ) | Output layer for multi-class classification (outputs sum to 1). |

**Why nonlinearity?** A stack of linear layers is still just one linear function. Nonlinear activations let networks learn complex functions.

### Perceptron and its limits

- A single unit with a threshold represents a **linear classifier** (a line/hyperplane separating classes).
- It can learn AND, OR, NOT, but **not XOR** (not linearly separable). This was the Minsky–Papert criticism.
- **Perceptron learning rule:** wᵢ ← wᵢ + α (y − ŷ) xᵢ

### Multilayer networks

- **Feed-forward network:** units arranged in layers, connections only go forward (no cycles). **Input layer → hidden layer(s) → output layer.**
- **Hidden layers** let the network represent nonlinear functions (such as XOR).
- **Universal approximation theorem:** a network with a single (large enough) hidden layer can approximate any continuous function. *Deep* networks do so more efficiently.
- **Recurrent networks** have feedback loops and a memory of earlier inputs (used for sequences).

### Training: loss, gradient descent, back-propagation

1. **Loss function** L measures the error. Examples: **mean squared error** (regression), **cross-entropy** (classification).
2. **Gradient descent:** adjust the weights in the direction that reduces the loss:

   > **w ← w − α · ∂L/∂w**

   where **α** is the **learning rate** (too big = unstable, too small = slow).
3. **Back-propagation:** an efficient algorithm for computing the gradient of the loss with respect to *every* weight. It uses the **chain rule** to pass error information from the output layer backwards through the network. Steps:
   - **Forward pass:** compute the outputs layer by layer.
   - **Compute the loss.**
   - **Backward pass:** compute gradients layer by layer, from output to input.
   - **Update the weights.**
4. **Variants:** **batch**, **stochastic (SGD)** and **mini-batch** gradient descent (using all, one, or a small subset of examples per update). **Adam** and momentum are popular improved optimisers.
5. One pass through the whole training set = one **epoch**.

### Deep learning

**Deep learning** = neural networks with **many hidden layers**. Early layers learn simple features and later layers learn more abstract ones (e.g. edges → shapes → objects). It works well because of **big datasets**, **powerful hardware (GPUs)** and **better techniques** (ReLU, dropout, better initialisation, batch normalisation).

**Main architectures:**

| Architecture | Used for | Key idea |
|---|---|---|
| **Feed-forward / MLP** | General tabular data, classification | Fully connected layers |
| **Convolutional NN (CNN)** | Images, vision | Small shared **filters** (kernels) slide over the image, detecting local patterns. **Pooling** reduces size. Far fewer parameters than fully connected layers. |
| **Recurrent NN (RNN, LSTM, GRU)** | Sequences (text, speech, time series) | Hidden state carries memory from step to step. LSTM/GRU handle long-range dependencies better. |
| **Transformer** | Language, and increasingly other domains | **Self-attention** lets every element of the input look at all the others. It is parallelisable and underlies large language models. |
| **Autoencoder** | Compression, representation learning | Learns to reconstruct its own input through a bottleneck. |
| **Generative models (GANs, diffusion, etc.)** | Generating images, text, audio | Learn to produce new data similar to the training data. |

**Other concepts:**

- **Representation learning / embeddings:** networks learn useful feature representations automatically, so less manual feature engineering is needed.
- **Transfer learning:** reuse a network trained on one task as a starting point for another.
- **Unsupervised, self-supervised and reinforcement learning** also use neural networks (e.g. AlphaGo uses deep networks plus reinforcement learning and tree search).

### Strengths and weaknesses

| Strengths | Weaknesses |
|---|---|
| Excellent performance on perception tasks (vision, speech, language) | Need a lot of data and computation |
| Learn features automatically | Hard to interpret ("black box") |
| Flexible, general-purpose | Can overfit; can be fooled by **adversarial examples** |
| Scale well with data | Can inherit **bias** from data (links to R2) |

---

## Cheat sheets

### Search algorithms – at a glance

| Algorithm | Frontier | Uses | Complete | Optimal | Memory |
|---|---|---|---|---|---|
| BFS | Queue (FIFO) | Depth of node | Yes | Yes (equal costs) | Very high |
| UCS | Priority queue by g | Path cost | Yes | Yes | High |
| DFS | Stack (LIFO) | – | No (in general) | No | Low |
| IDS | Stack, repeated | Depth limit | Yes | Yes (equal costs) | Low |
| Greedy | Priority queue by h | Heuristic | No (in general) | No | High |
| A\* | Priority queue by g+h | Cost + heuristic | Yes | Yes (admissible/consistent h) | High |

### Logic – at a glance

- **Entailment** KB ⊨ α: α true in every model of KB.
- **Sound** = no false conclusions; **complete** = all true conclusions derivable.
- Resolution: CNF + resolve until the empty clause.
- Propositional: facts only. FOL: objects, relations, quantifiers.
- ∀ goes with ⇒, ∃ goes with ∧.

### Probability – formulas

- P(a ∧ b) = P(a | b) P(b)
- P(a | b) = P(b | a) P(a) / P(b)
- P(Y) = Σ_z P(Y, z)
- Independence: P(a, b) = P(a) P(b)
- Bayes net: P(x₁…xₙ) = Π P(xᵢ | parents(Xᵢ))
- Expected utility: EU(a) = Σ P(s' | a) U(s')

### Neural networks – formulas

- Neuron: a = g(Σ wᵢxᵢ + b)
- Gradient descent: w ← w − α ∂L/∂w
- ReLU: max(0, z); Sigmoid: 1/(1+e⁻ᶻ)

---

## Self-check questions

**R1 – History**
1. Which event in 1956 is regarded as the birth of AI?
2. What caused the first AI "winter" and how did the field recover?
3. Explain the four approaches to defining AI. Which one does the textbook adopt?

**R2 – Ethics**
4. Give three ethical risks of AI and one possible mitigation for each.
5. How can a machine learning system become biased, even if the developers did not intend it?
6. What is the value alignment problem?

**R3 – State space**
7. Define a search problem formally (five components).
8. What is the difference between the state space and the search tree?
9. Formulate the 8-puzzle as a search problem.

**R4 – Uninformed search**
10. Compare BFS and DFS in terms of completeness, optimality, time and space.
11. Why is iterative deepening often preferred over BFS?
12. In what order does BFS/DFS visit the nodes of a given tree?

**R5 – Heuristic search**
13. What is an admissible heuristic? A consistent heuristic? Which implies which?
14. Why is A\* optimal with an admissible heuristic?
15. Show that Manhattan distance is admissible for the 8-puzzle. Which heuristic dominates, misplaced tiles or Manhattan distance?
16. Give an example where greedy search returns a non-optimal path but A\* does not.

**R8 – Logic**
17. What does KB ⊨ α mean? How is it related to unsatisfiability?
18. Convert (A ⇒ B) ∧ (B ⇒ C) to CNF.
19. Prove using resolution: from (P ⇒ Q) and P, derive Q.
20. Translate to FOL: "Every student who studies passes the exam."
21. Why is first-order logic more expressive than propositional logic?

**R9 – Probabilistic reasoning**
22. When should you use probabilistic reasoning instead of logic?
23. Explain marginalisation and conditioning.
24. What is the difference between independence and conditional independence?

**R10 – Bayes and Bayesian networks**
25. State Bayes' theorem and name each term.
26. A disease has a prevalence of 2%, a test has 95% sensitivity and a 5% false positive rate. Compute P(disease | positive).
27. Draw a Bayesian network for the alarm example and compute a joint probability entry.
28. What is "explaining away"? Which network structure causes it?
29. Why does a Bayesian network need fewer parameters than a full joint table?

**R12 – Neural networks**
30. Describe how a single artificial neuron computes its output.
31. Why can't a single perceptron learn XOR? How does a hidden layer help?
32. Explain gradient descent and back-propagation in your own words.
33. Why do we need nonlinear activation functions?
34. What is overfitting and how can it be reduced?
35. What is a CNN and why is it good for images?

---

*End of summary. For deeper study, read the corresponding chapters in Russell & Norvig (4th ed.) and work through the end-of-chapter exercises.*

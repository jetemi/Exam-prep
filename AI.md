**1. a. Discuss "Artificial intelligence is a branch of Science which deals with helping machines find solutions to complex problems". (5.5 Marks)**

Artificial Intelligence (AI) is indeed a branch of computer science aiming to create intelligent systems.  The core idea is to enable machines to perform tasks that typically require human intelligence.  This involves designing algorithms and models that allow computers to:

*   **Learn from data:**  AI systems can analyze vast amounts of information to identify patterns, make predictions, and improve their performance over time, similar to how humans learn from experience.
*   **Solve complex problems:** AI tackles problems that are difficult or impossible for humans to solve efficiently due to their complexity, scale, or the need for rapid processing. Examples include optimizing logistics, diagnosing diseases, or predicting financial markets.
*   **Mimic cognitive functions:** AI seeks to replicate human-like cognitive abilities such as problem-solving, decision-making, perception (vision, speech), natural language understanding, and reasoning.
*   **Automate tasks:**  By automating intelligent tasks, AI can increase efficiency, reduce errors, and free up human resources for more creative and strategic endeavors.


**1. b. Highlight and explain four approaches to artificial Intelligence (12 Marks)**

*   **1. Symbolic AI (Rule-based AI):**
    *   **Highlight:**  Focuses on representing knowledge explicitly using symbols, rules, and logic.
    *   **Explanation:**  This approach believes intelligence can be achieved by manipulating symbols and applying logical rules. Expert systems are a prime example.  Knowledge is encoded as "if-then" rules.  Reasoning is performed by applying these rules to solve problems.  **Example:**  A medical diagnosis system might have rules like "IF patient has fever AND cough THEN suspect flu."
    *   **Strengths:**  Human-understandable reasoning, good for well-defined problems with structured knowledge.
    *   **Weaknesses:**  Struggles with uncertain or incomplete knowledge, knowledge acquisition bottleneck (difficult to extract rules from experts), brittle (rules need to be explicitly updated).

*   **2. Connectionist AI (Neural Networks):**
    *   **Highlight:**  Mimics the structure of the human brain using interconnected nodes (neurons) to learn patterns from data.
    *   **Explanation:** Inspired by biological neural networks, this approach uses artificial neural networks consisting of layers of interconnected nodes.  Learning occurs by adjusting the connections (weights) between nodes based on training data.  Deep learning is a subfield of connectionism with networks having many layers. **Example:** Image recognition, natural language processing, speech recognition.
    *   **Strengths:**  Excellent at pattern recognition, learning from large datasets, robust to noisy data, can handle complex and non-linear relationships.
    *   **Weaknesses:**  "Black box" problem (difficult to understand why a network makes a specific decision), requires large amounts of training data, computationally intensive.

*   **3. Evolutionary AI (Genetic Algorithms):**
    *   **Highlight:**  Uses principles of natural selection and evolution to develop AI systems.
    *   **Explanation:**  This approach employs algorithms inspired by biological evolution, such as genetic algorithms.  A population of candidate solutions is iteratively improved through processes like selection, crossover (combining solutions), and mutation.  The "fittest" solutions (those that perform best according to a fitness function) survive and reproduce.  **Example:**  Optimizing complex systems, robot control, game playing.
    *   **Strengths:**  Good for complex optimization problems, can discover novel solutions, robust to changes in the environment.
    *   **Weaknesses:**  Computationally expensive, can be slow to converge to a solution, solutions may be difficult to interpret.

*   **4. Statistical AI (Machine Learning):**
    *   **Highlight:**  Emphasizes using statistical methods to learn from data and make predictions.
    *   **Explanation:**  This broad approach encompasses various techniques like Bayesian networks, support vector machines, decision trees, and many other machine learning algorithms.  It focuses on building models that can learn statistical relationships from data and generalize to unseen data.  **Example:** Spam filtering, recommendation systems, fraud detection.
    *   **Strengths:**  Data-driven, can handle uncertainty and noise, wide range of algorithms for different tasks, strong theoretical foundation.
    *   **Weaknesses:**  Performance depends heavily on data quality and quantity, may require feature engineering (selecting relevant input features), can be computationally intensive for complex models.

**2. a. Define the term agent (1 Mark)**

An **agent** in AI is any entity that can perceive its environment through sensors and act upon that environment through actuators.

**2. b. State three performance measures of an agent (6 Marks)**

*   **1. Completeness:**  Measures whether the agent achieves its goals or intended outcomes.  A complete agent successfully solves the problem or completes the task it is designed for.  For example, a vacuum cleaning agent is complete if it cleans all the dirt in a given area.
*   **2. Efficiency:**  Measures how effectively the agent uses resources (like time, energy, or computational power) to achieve its goals. An efficient agent achieves its goals with minimal resource consumption. For example, a route-finding agent is efficient if it finds the shortest path in a reasonable time.
*   **3. Optimality:** Measures whether the agent finds the *best* possible solution or outcome. An optimal agent always aims for the highest possible performance level given its goals and constraints. For example, a game-playing agent is optimal if it always makes moves that lead to the best possible outcome (winning or drawing).

**2. c. Highlight and explain three agent architectures (10.5 Marks)**

*   **1. Simple Reflex Agent:**
    *   **Highlight:**  Reacts directly to percepts based on predefined condition-action rules.
    *   **Explanation:** This is the simplest architecture. It works based on "if-condition-then-action" rules.  The agent perceives the current state of the environment and selects an action based on a direct mapping from percept to action. It does not have memory or consider past percepts or future consequences.
    *   **Example:** A thermostat that turns on the heater when the temperature is below a set point and turns it off when above.
    *   **Strengths:** Simple to implement, fast reaction time.
    *   **Weaknesses:** Limited intelligence, cannot handle partially observable environments, cannot learn or improve over time, rule-based and brittle.

*   **2. Model-Based Reflex Agent:**
    *   **Highlight:**  Maintains an internal model of the environment to make decisions, especially in partially observable environments.
    *   **Explanation:**  This agent maintains an internal state, which is a representation of the current world based on percept history. It uses a "model" of the world to infer aspects of the current state that are not directly perceived.  It then uses condition-action rules based on this internal model to choose actions.
    *   **Example:** A robot navigating a maze. If it cannot directly see the entire maze, it builds a map (internal model) based on what it has explored so far and uses this map to plan its path.
    *   **Strengths:** Can handle partially observable environments, more flexible than simple reflex agents.
    *   **Weaknesses:** Model needs to be accurate, model maintenance can be complex, still largely rule-based.

*   **3. Goal-Based Agent:**
    *   **Highlight:**  Chooses actions to achieve explicit goals.
    *   **Explanation:**  This agent has a representation of its goals and uses search and planning to find a sequence of actions that will achieve those goals. It considers the future consequences of its actions and aims to reach a desired goal state.  It needs information about goals (what it wants to achieve) and state transitions (how actions affect the world).
    *   **Example:** A route-planning system that aims to find the shortest path between two cities.
    *   **Strengths:** More flexible and intelligent than reflex agents, can handle complex tasks, can plan ahead.
    *   **Weaknesses:** Goal formulation can be challenging, planning can be computationally expensive, may struggle in dynamic or unpredictable environments.

**3. Define the following terms within the scope of a state space search (17.5 Marks)**

*   **i. Initial State (2.5 Marks):** The **initial state** is the starting configuration or situation in which the problem begins. It is the point from which the agent starts its search for a solution.  **Example:** In a route-finding problem, the initial state is the starting city. In a puzzle like the 8-puzzle, it's the initial arrangement of tiles.

*   **ii. Action (2.5 Marks):** An **action** is a transition or move that an agent can make from one state to another state in the problem space. Actions transform the current state to a new state.  **Example:** In a route-finding problem, an action could be moving from one city to an adjacent city. In the 8-puzzle, actions are moving the blank tile up, down, left, or right.

*   **iii. Plan (2.5 Marks):** A **plan** is a sequence of actions that, when executed starting from the initial state, leads to a goal state. In state space search, the goal is to find a plan.  **Example:** In a route-finding problem, a plan is a sequence of cities to visit to get from the starting city to the destination city.

*   **iv. Path Cost (2.5 Marks):** The **path cost** is a numerical value associated with a path (sequence of actions) in the state space. It represents the "cost" of taking that path, typically measured in terms of resources consumed (time, distance, fuel, etc.). The search algorithm often aims to find a plan with the minimum path cost. **Example:** In a route-finding problem, path cost could be the total distance traveled or the travel time.

*   **v. Goal State (2.5 Marks):** A **goal state** is the desired final configuration or situation that represents a solution to the problem. The search process terminates when a goal state is reached. There can be multiple goal states. **Example:** In a route-finding problem, the goal state is the destination city. In the 8-puzzle, it's the desired arrangement of tiles.

*   **vi. Problem Space (2.5 Marks):** The **problem space** (or state space) is the set of all possible states that can be reached from the initial state by applying actions. It is the entire space of configurations that are relevant to solving the problem.  It can be visualized as a graph where states are nodes and actions are edges. **Example:** For the 8-puzzle, the problem space is all possible arrangements of the 8 tiles and the blank space.

*   **vii. Search Problem (2.5 Marks):** A **search problem** is formally defined by these components:
    *   **Initial State:**  The starting point.
    *   **Actions:**  Possible transitions between states.
    *   **State Space:**  The set of all reachable states.
    *   **Goal Test:**  A function that determines if a given state is a goal state.
    *   **Path Cost:**  A function that assigns a cost to a path.
    The task in a search problem is to find a sequence of actions (a plan) from the initial state to a goal state with the minimum path cost (optimal solution).

**4. a. In the quest of developing an expert system for question answering problem, how will you describe knowledge representation in this context. (3 Marks)**

*   **Capture semantic meaning:**  Represent the meaning of words, sentences, and concepts in a way that the system can understand and reason with.
*   **Enable inference:** Support logical reasoning and inference to derive answers that are not explicitly stated in the knowledge base.
*   **Be organized and accessible:** Structure knowledge for efficient retrieval and processing when answering questions.

**4. b. State and explain the key parameters involved in creating a knowledge representation (4.5 Marks)**

*   **1. Representational Adequacy:**  The ability of the representation to express all the necessary knowledge in the domain.  It should be rich enough to capture the nuances and complexities of the domain being modeled.  **Explanation:** If the representation is not adequate, some crucial information might be lost, limiting the system's ability to answer questions effectively.

*   **2. Inferential Adequacy:** The ability of the representation to support reasoning and inference. It should allow the system to deduce new knowledge from the explicitly represented facts. **Explanation:**  A good knowledge representation should not just store facts, but also enable the system to draw conclusions and answer questions that require reasoning.

*   **3. Inferential Efficiency:** The ability of the representation to support efficient reasoning and inference.  The reasoning mechanisms should be computationally feasible and provide answers in a reasonable time. **Explanation:** Even if a representation is inferentially adequate, it's not useful if the inference process is too slow or computationally expensive.

*   **4. Acquisitional Efficiency:** The ease with which new knowledge can be added to the representation. It should be relatively straightforward to update and expand the knowledge base as the domain evolves. **Explanation:**  Knowledge is constantly evolving. A good representation should be easy to update and maintain with new information.

**4. c. State how knowledge representation is specified in terms of the five distinct roles that it plays (10 Marks)**

*   **1. Surrogate:** Knowledge representation acts as a substitute for the real world or domain being modeled. It represents the essential aspects of the domain within the AI system. **Explanation:** Instead of directly dealing with the real world, the system manipulates and reasons with the knowledge representation, which acts as a stand-in for reality.

*   **2. Set of Ontological Commitments:**  Choosing a knowledge representation involves making commitments about what exists in the world.  It defines the vocabulary and concepts used to describe the domain. **Explanation:**  Different knowledge representations have different underlying assumptions about the nature of reality and what concepts are important. For example, using frames commits to representing knowledge in terms of objects and their attributes.

*   **3. Fragmentary Theory of Intelligent Reasoning:** Knowledge representation provides a framework for reasoning. It influences the types of inferences that can be made and the reasoning processes that are supported. **Explanation:**  The choice of knowledge representation shapes how the system reasons.  For example, rule-based systems use rule-based reasoning, while frame-based systems might use inheritance and slot filling.

*   **4. Medium for Human Expression:**  A good knowledge representation should be understandable and usable by humans. It should facilitate communication between knowledge engineers, domain experts, and the AI system itself. **Explanation:**  Knowledge needs to be acquired from humans (domain experts) and understood by humans (developers). A clear and understandable representation aids in knowledge acquisition, validation, and debugging.

*   **5. Medium for Computational Implementation:**  Knowledge representation must be implementable in a computer system. It should be designed in a way that allows for efficient storage, retrieval, and processing of knowledge by algorithms. **Explanation:**  Ultimately, the knowledge representation needs to be translated into a computer-executable format.  The representation should be compatible with computational techniques for reasoning and problem-solving.

**5. a. What is natural language processing? (3 Marks)**

**Natural Language Processing (NLP)** is a branch of Artificial Intelligence that deals with the interaction between computers and human (natural) languages. It aims to enable computers to understand, interpret, generate, and manipulate human language in a meaningful and valuable way.

**5. b. Explain the goal of NLP evaluation (4.5 Marks)**

The goal of **NLP evaluation** is to assess the performance and effectiveness of NLP systems and algorithms.  It aims to:

*   **Measure progress:** Track improvements in NLP techniques over time by providing quantifiable metrics.
*   **Compare different approaches:**  Objectively compare the performance of various NLP models and algorithms on specific tasks.
*   **Identify strengths and weaknesses:**  Pinpoint areas where an NLP system performs well and areas that need improvement.
*   **Ensure quality and reliability:**  Validate that NLP systems are robust, accurate, and suitable for real-world applications.
*   **Guide development:**  Provide feedback to developers to refine their models and algorithms and make informed design choices.

**5. c. Differentiate between the following evaluation measures (10 Marks)**

**i. Intrinsic and Extrinsic Evaluation:**

| Feature          | Intrinsic Evaluation                                     | Extrinsic Evaluation                                       |
| ---------------- | -------------------------------------------------------- | ---------------------------------------------------------- |
| **Focus**        | Evaluating the NLP task itself.                          | Evaluating the NLP component in a larger application context. |
| **Metric**       | Task-specific metrics (e.g., precision, recall, F1-score, BLEU for translation, accuracy for classification). | Impact on the performance of the end-to-end application.    |
| **Example**      | Evaluating the accuracy of a part-of-speech tagger on a test set. | Evaluating the improvement in a search engine's relevance due to using a better query understanding module. |
| **Advantages**   | Directly measures the quality of the NLP component.        | Real-world relevance, measures actual impact.              |
| **Disadvantages**| May not reflect real-world utility, task may be artificial. | Can be complex to isolate the impact of the NLP component, influenced by other factors in the application. |

**ii. Black Box and Glass Box Evaluation:**

| Feature          | Black Box Evaluation                                      | Glass Box Evaluation                                      |
| ---------------- | --------------------------------------------------------- | ---------------------------------------------------------- |
| **Approach**     | Focuses on the overall input-output behavior of the system. | Examines the internal workings and components of the system. |
| **Analysis**     | Treats the system as a "black box" and measures performance based on inputs and outputs. | "Opens the box" and analyzes internal decisions, reasoning processes, and intermediate results. |
| **Metrics**      |  Accuracy, precision, recall (overall performance metrics). |  Rule coverage, feature importance, attention weights (internal system behaviors). |
| **Purpose**      |  Measure overall effectiveness, compare systems.          | Understand system behavior, diagnose errors, identify areas for improvement in design. |
| **Example**      |  Measuring the accuracy of a sentiment classifier on a dataset. | Analyzing which features (words, phrases) are most important for the sentiment classifier's decisions. |
| **Advantages**   |  Simple to perform, system-agnostic.                      |  Provides deeper insights, facilitates system debugging and improvement. |
| **Disadvantages**|  Limited diagnostic information, doesn't explain *why* a system performs a certain way. |  More complex to perform, requires access to internal system components. |

**6. a. State five attributes that one should look out for in AI problems (7.5 marks)**

*   **1. Complexity:** The problem should be complex enough to require intelligent solutions, exceeding the capabilities of simple algorithms or manual approaches.  This might involve large datasets, intricate rules, or non-linear relationships.
*   **2. Ambiguity and Uncertainty:** Problems involving incomplete, noisy, or ambiguous data, requiring the system to handle uncertainty and make decisions under incomplete information. Natural language understanding, image recognition in poor lighting, or medical diagnosis with uncertain symptoms are examples.
*   **3. Need for Adaptability and Learning:** Problems where the environment or data changes over time, requiring the system to learn, adapt, and improve its performance continuously.  Spam filtering, fraud detection, and personalized recommendations are examples.
*   **4. Human-like Intelligence Required:** Problems that traditionally require human cognitive abilities like perception, reasoning, learning, problem-solving, decision-making, or natural language understanding.
*   **5. Value and Impact:** The problem should have significant potential value or impact if solved by AI, either in terms of efficiency gains, cost reduction, improved quality, new capabilities, or societal benefit.

**6. b. State the differences between AI Programs and conventional programs (5 marks)**

| Feature            | Conventional Programs                               | AI Programs                                                    |
| ------------------ | ----------------------------------------------------- | ------------------------------------------------------------- |
| **Programming Approach** | Explicitly programmed steps, algorithm-driven.          | Data-driven, learning-based, often use algorithms to learn.       |
| **Problem Solving**  | Solve well-defined problems with fixed logic.           | Solve complex, ill-defined problems, handle uncertainty.       |
| **Decision Making**  | Follow pre-defined rules, deterministic.                | Can make decisions under uncertainty, probabilistic, heuristic. |
| **Learning**         | Cannot learn or adapt from data.                       | Designed to learn from data and improve performance.           |
| **Data Dependence**   | Less data-dependent, logic is primary.                 | Highly data-dependent, performance improves with more data.    |
| **Explanation**      | Logic is transparent, easy to trace execution.          | "Black box" nature can make explanations challenging.         |
| **Examples**         | Calculator, word processor, database management system. | Image recognition, speech recognition, natural language understanding, game playing. |

**6. c. "Can machines think ?" <--------> "Can machines behave intelligently ?" Answer the above question using Turing test. (Diagrammatic approach attracts more mark(s)) (5 marks)**

The question "Can machines think?" is a philosophical debate.  Alan Turing proposed shifting the focus to a more operational question: "Can machines behave intelligently?" and introduced the **Turing Test** to assess this.

**Turing Test Explanation:**

The Turing Test is a test of a machine's ability to exhibit intelligent behavior equivalent to, or indistinguishable from, that of a human.

**Diagrammatic Approach:**

```
                        +--------------------+
                        | Human Interrogator |
                        +--------------------+
                                ^
                                | Text-based questions (e.g., typed)
                                v
+-----------------+     Text-based answers     +--------------------+
| Human Respondent| <------------------------> |  Machine Respondent|
+-----------------+                            +--------------------+
```

**Explanation of the Diagram and Turing Test:**

1.  **Setup:**  A human interrogator engages in text-based conversations with two respondents, both hidden from view. One respondent is a human, and the other is a machine (computer program).
2.  **Task:** The interrogator's goal is to determine which respondent is the machine and which is the human, solely based on their text-based responses to questions.
3.  **Passing the Test:** The machine passes the Turing Test if the interrogator cannot reliably distinguish the machine's responses from the human's responses. In other words, if the machine can convincingly imitate human conversation to the point of fooling a human judge.

**Answering the question "Can machines think?" using the Turing Test:**

*   **Turing's Argument:** Turing argued that if a machine can pass the Turing Test, then we should consider it to be "thinking" or at least behaving intelligently.  He sidestepped the difficult philosophical question of "thinking" and focused on observable intelligent behavior.
*   **Behavioral Intelligence:** The Turing Test emphasizes **behavioral intelligence**. It doesn't try to define consciousness or internal mental states. It focuses on whether a machine can *behave* in a way that we would typically associate with human intelligence.
*   **"Thinking" vs. "Behaving Intelligently":**  The Turing Test effectively shifts the question from "Can machines think?" (which is hard to define and measure) to "Can machines behave intelligently?" (which is testable).  If a machine can consistently fool a human into thinking it's human through conversation, then it is exhibiting a form of intelligence, regardless of whether it truly "thinks" in the human sense.
*   **Limitations:**  The Turing Test has limitations and criticisms.  It primarily tests conversational ability, not necessarily all aspects of intelligence.  A machine might pass by cleverly mimicking human conversation without genuine understanding or consciousness.  However, it remains a significant milestone and a useful benchmark for AI.

**Conclusion:** The Turing Test provides a practical and behavior-oriented way to assess machine intelligence.  By focusing on whether machines can *behave* intelligently, it offers a measurable and testable approach to evaluating AI progress, even if it doesn't definitively answer the philosophical question of "Can machines think?"
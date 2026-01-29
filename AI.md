**1. a. Discuss "Artificial intelligence is a branch of Science which deals with helping machines find solutions to complex problems". (5.5 Marks)**

Artificial Intelligence (AI) is indeed a branch of computer science aiming to create intelligent systems.  The core idea is to enable machines to perform tasks that typically require human intelligence.  This involves designing algorithms and models that allow computers to:

*   **Learn from data:**  AI systems can analyze vast amounts of information to identify patterns, make predictions, and improve their performance over time, similar to how humans learn from experience.
*   **Solve complex problems:** AI tackles problems that are difficult or impossible for humans to solve efficiently due to their complexity, scale, or the need for rapid processing. Examples include optimizing logistics, diagnosing diseases, or predicting financial markets.
*   **Mimic cognitive functions:** AI seeks to replicate human-like cognitive abilities such as problem-solving, decision-making, perception (vision, speech), natural language understanding, and reasoning.
*   **Automate tasks:**  By automating intelligent tasks, AI can increase efficiency, reduce errors, and free up human resources for more creative and strategic endeavors.


**1. b. Highlight and explain four approaches to artificial Intelligence (12 Marks)**

1. **Strong AI**: This approach focuses on creating machines with genuine self-awareness and human-level reasoning. It suggests that a properly programmed computer is not just a tool, but actually possesses a mind and cognitive mental states.
2. **Weak AI**: This approach involves building systems that act as if they are intelligent but do not possess true understanding or consciousness. It aims to simulate human cognition to perform tasks without requiring actual "thought."
3. **Applied AI**: This is the practical branch of AI focused on creating commercially successful "smart" systems. It focuses on solving real-world problems, such as facial recognition for security systems.
4. **Cognitive AI**: This approach uses computer models as a scientific tool to test theories about human psychology. It aims to understand how the human mind functions, specifically how we process information and solve abstract problems.

**2. a. Define the term agent (1 Mark)**

An **agent** in AI is any entity that can perceive its environment through sensors and act upon that environment through actuators.

**2. b. State three performance measures of an agent (6 Marks)**

*   **1. Accuracy:**  Measures whether the agent achieves its goals or intended outcomes.  A complete agent successfully solves the problem or completes the task it is designed for.  For example, a vacuum cleaning agent is complete if it cleans all the dirt in a given area.
*   **2. Efficiency/Resources used (Power/Money):**  Measures how effectively the agent uses resources (like time, energy, or computational power) to achieve its goals. An efficient agent achieves its goals with minimal resource consumption. For example, a route-finding agent is efficient if it finds the shortest path in a reasonable time.
*   **3. Quality/Optimality:** Measures whether the agent finds the *best* possible solution or outcome. An optimal agent always aims for the highest possible performance level given its goals and constraints. For example, a game-playing agent is optimal if it always makes moves that lead to the best possible outcome (winning or drawing).

**2. c. Highlight and explain three agent architectures (10.5 Marks)**

*   **1. Simple Reflex Agent (Percept-based):** This is the simplest architecture. It works based on "if-condition-then-action" rules. The agent perceives the current state of the environment and selects an action based on a direct mapping from percept to action. It does not have memory or consider past percepts or future consequences.

*   **2. Model-Based Reflex Agent (State-based):** This agent maintains some sort of state based on the percept sequence received so far. The state is updated regularly based on what the agent senses, and the agent‘s actions.

    Such agents work as follows:
    *   information comes from sensors – percepts.
    *   based on this, the agent changes the current state of the world.
    *   based on state of the world and knowledge (memory), it triggers actions through the effectors.

*   **3. Goal-Based Agent:** The goal based agent has some goal which forms a basis of its actions.

    Such agents work as follows:
    *   information comes from sensors - percepts.
    *   changes the agents current state of the world.
    *   based on state of the world and knowledge (memory) and goals/intentions, it chooses actions and does them through the effectors.

**3. Define the following terms within the scope of a state space search (17.5 Marks)**

*   **i. Initial State (2.5 Marks):** The **initial state** is the starting configuration or situation in which the problem begins. It is the point from which the agent starts its search for a solution.
*   **ii. Action (2.5 Marks):** Also called an **operator** is a transition or move that an agent can make from one state to another state in the problem space. Actions transform the current state to a new state called a successor state.

*   **iii. Plan (2.5 Marks):** A **plan** is a sequence of actions that, when executed starting from the initial state, leads to a goal state. In state space search, the goal is to find a plan.

*   **iv. Path Cost (2.5 Marks):** The **path cost** is a numerical value associated with a path (sequence of actions) in the state space. It represents the "cost" of taking that path, typically measured in terms of resources consumed (time, distance, fuel, etc.). The search algorithm often aims to find a plan with the minimum path cost.

*   **v. Goal State (2.5 Marks):** A **goal state** is the desired final configuration or situation that represents a solution to the problem. The search process terminates when a goal state is reached. There can be multiple goal states.

*   **vi. Problem Space (2.5 Marks):** The **problem space** (or state space) is the set of all possible states that can be reached from the initial state by applying actions. It is the entire space of configurations that are relevant to solving the problem.  It can be visualized as a graph where states are nodes and actions are edges.

*   **vii. Search Problem (2.5 Marks):** A **search problem** is formally defined by these components:
    *   **Initial State:**  The starting point.
    *   **Actions:**  Possible transitions between states.
    *   **State Space:**  The set of all reachable states.
    *   **Goal Test:**  A function that determines if a given state is a goal state.
    *   **Path Cost:**  A function that assigns a cost to a path.
    The task in a search problem is to find a sequence of actions (a plan) from the initial state to a goal state with the minimum path cost (optimal solution).

**4. a. In the quest of developing an expert system for question answering problem, how will you describe knowledge representation in this context. (3 Marks)**

*   **Capture semantic meaning:**  Represent the meaning of words, sentences, and concepts in a way that the system can understand and reason with.
*   **Enable inference:** Support logic
al reasoning and inference to derive answers that are not explicitly stated in the knowledge base.
*   **Be organized and accessible:** Structure knowledge for efficient retrieval and processing when answering questions.

**4. b. State and explain the key parameters involved in creating a knowledge representation (4.5 Marks)**

*   **1. Completeness:**  The ability of the representation to express all the necessary knowledge in the domain.  It should be rich enough to capture the nuances and complexities of the domain being modeled.

*   **2. Expressivity:** refers to how easy and compact it is to express a fact or element of knowledge within the semantics and grammar of the KR (Compactness)

*   **3. Efficiency:** The ability of the representation to support efficient reasoning and inference.  The reasoning mechanisms should be computationally feasible and provide answers in a reasonable time. **Explanation:** Even if a representation is inferentially adequate, it's not useful if the inference process is too slow or computationally expensive.

*   **4. Inferential Adequacy:** The ability of the representation to support reasoning and inference. It should allow the system to deduce new knowledge from the explicitly represented facts. **Explanation:**  A good knowledge representation should not just store facts, but also enable the system to draw conclusions and answer questions that require reasoning.

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


## Assignment 1

#### Question 1: Define Intelligent
Intelligent means the ability to learn from experience, reason, adapt to new situations, and apply knowledge to solve problems effectively. An intelligent system can understand its environment, make decisions, and improve its performance over time
#### Question 2: What are the different approaches to defining Artificial Intelligence?
* AI is defined as systems that **think like humans**, replicating human cognitive processes such as reasoning, learning, and memory.
* AI is defined as machines that can **act like humans**, especially in conversation, problem-solving, and social interaction.
* AI is seen as systems that use **logical reasoning**—following rules to reach correct conclusions.
* AI is defined as systems that **act rationally** by taking actions that maximize their chances of achieving goals.
#### Question 3: Five tasks you would like a computer to be able to do within the next five years
1. Accurately diagnose medical conditions from images or symptoms in real time.
2. Fully automate customer service with natural, human-level conversations.
3. Drive cars safely and independently in major cities.
4. Translate languages with human-level fluency, including African languages.
5. Predict and prevent financial fraud before it happens.
#### Question 4: Five tasks computers are unlikely to be able to do in the next five years
1. Fully replace human judgment in complex legal or ethical decisions.
2. Perform delicate physical tasks such as tailoring clothes or braiding hair with human precision.
3. Understand human emotions perfectly in all cultural contexts.
4. General human-level intelligence across all tasks (AGI).
5. Autonomously run a government or lead a company without human oversight.

## Assignment 2


#### 1. Define an Agent
An agent is an entity that perceives its environment through sensors and acts upon that environment through actuators in order to achieve specific goals.

#### 2. What is a Rational Agent?
A rational agent is an agent that selects the action that maximizes its expected performance measure, based on:
- The information it has perceived
- Its built-in knowledge
- The actions available to it
Rationality means doing the right thing, not necessarily being perfect or omniscient.

#### 3. What is Bounded Rationality?
Bounded rationality refers to the idea that an agent’s rational decision-making is limited by:
- Incomplete information
- Limited computational resources
- Time constraints

#### 4. What is an Autonomous Agent?
An autonomous agent is an agent that operates independently of human control and learns from its environment, using its own experience to improve future actions.

#### 5. Describe the Salient Features of an Agent

1. **Perception** – Ability to sense the environment through sensors.
2. **Action** – Ability to affect the environment using actuators.
3. **Rationality** – Chooses actions that maximize goal achievement.
4. **Autonomy** – Operates with minimal or no human intervention.
5. **Learning** – Improves performance over time from experience.
6. **Reactivity** – Responds to changes in the environment.
7. **Proactiveness** – Takes initiative to achieve goals.

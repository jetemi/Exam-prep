# CSC 424 — Expert Systems & Knowledge Engineering: Exam-Ready Answers

---

## SECTION A — Answer key (blanks 1–30)

1. **Expert system** — the system that emulates the cognitive skills of human experts to guide users through complex decision-making.
2. **Task domain**

**3–12. Differentiate Knowledge System applications from Conventional System applications** (write as 5 contrast pairs):


| #   | Knowledge System Application                                                        | #   | Conventional System Application                                                 |
| --- | ----------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------- |
| 3   | Processes **knowledge** (facts + rules) using **symbolic reasoning**                | 4   | Processes **data** using algorithms (well-defined numeric operations)           |
| 5   | Uses **heuristic** reasoning (rules of thumb)                                       | 6   | Uses strict **algorithmic/procedural** logic                                    |
| 7   | Can work with **incomplete, uncertain or fuzzy** data                               | 8   | Requires **complete and exact** data                                            |
| 9   | **Knowledge is separate** from the control mechanism — rules are easy to add/change | 10  | Knowledge and control are **mixed in the program code** — changes are difficult |
| 11  | Can **explain** how and why it reached a conclusion                                 | 12  | **Cannot explain** its results (black box)                                      |


1. **Heuristic** — a rule of thumb, fact, or procedure that can be used to solve a problem but is **not guaranteed** to do so.

**14–16. The components of an expert system are:**  
14. **Knowledge base**  
15. **Inference engine**  
16. **User interface**
17. Building an expert system is known as **Knowledge engineering**.
18. The practitioners of expert systems are called **Knowledge engineers**.

**19–23. Human elements in expert system development:**  
19. **Domain expert**
20. **Knowledge engineer**
21. **Programmer**
22. **Project manager**
23. **End-user**

> 💡 Code: **D**on't **K**eep **P**eople **P**raying **E**ndlessly.

**24–25. The types of inferences are:**  
24. **Forward chaining** (data-driven reasoning)  
25. **Backward chaining** (goal-driven reasoning)  
26. **Inference engine** is the brain of the expert system.  
27. **Inference engine** serves as the rule interpreter.  
28. **Inference engine** provides methodology for reasoning.

**29–30. Expert system tools are:** 
29. **Expert system shells** (e.g. CLIPS — a shell is an ES with the knowledge removed)
30. **Programming languages** (high-level AI languages: LISP, PROLOG)

---

## SECTION B — answer any TWO

### Question 1

#### 1.a Define expert system technologies — 2 marks

Expert system technologies are the **software tools, techniques and methodologies used to develop and run expert systems** — knowledge representation formalisms (rules, frames, semantic networks), inference engines, knowledge acquisition techniques, **expert system shells** (e.g. CLIPS, EMYCIN) and specialized **AI programming languages** (LISP, PROLOG).

#### 1.b Stages of developing a knowledge base — 6 marks

The five steps of knowledge engineering (transferring human knowledge into a knowledge base):

1. **Knowledge acquisition** — extract knowledge from domain experts and documents (interviews, protocol analysis, observation, questionnaires).
2. **Knowledge validation** — verify the acquired knowledge is correct, complete and consistent (test cases, expert review).
3. **Knowledge representation** — organize the validated knowledge in a machine-usable form (rules, frames, semantic networks, logic).
4. **Inferencing** — design how the system will reason with the knowledge to draw conclusions (forward/backward chaining).
5. **Explanation and justification** — build the facility that lets the system explain *how* and *why* it reached its conclusions.

> 💡 Mnemonic: **A**ll **V**alid **R**ules **I**nfer **E**xplanations (Acquisition, Validation, Representation, Inferencing, Explanation).

#### 1.c.i Stages of expert system analysis and design methodology (with diagram) — 10 marks

Knowledge engineering has **six phases** (Negnevitsky, Fig. 9.1) — the process is **highly iterative**:

```
┌──────────────────────────────────┐
│ 1. Problem assessment            │
└────────────────┬─────────────────┘
                 ▼
┌──────────────────────────────────┐
│ 2. Data and knowledge acquisition│◄────────┐
└────────────────┬─────────────────┘         │
                 ▼                           │
┌──────────────────────────────────┐         │
│ 3. Development of a prototype    │         │  feedback /
│    system                        │         │  iteration
└────────────────┬─────────────────┘         │  (phases repeat
                 ▼                           │  as new knowledge
┌──────────────────────────────────┐         │  is discovered)
│ 4. Development of a complete     │         │
│    system                        │         │
└────────────────┬─────────────────┘         │
                 ▼                           │
┌──────────────────────────────────┐         │
│ 5. Evaluation and revision       │─────────┘
└────────────────┬─────────────────┘
                 ▼
┌──────────────────────────────────┐
│ 6. Integration and maintenance   │
└──────────────────────────────────┘
```

1. **Problem assessment** — define the problem, check an ES is suitable, identify participants and resources.
2. **Data and knowledge acquisition** — collect and analyse data and knowledge from experts and documents.
3. **Development of a prototype system** — choose a tool, represent the knowledge, build and test a small working version with test cases.
4. **Development of a complete system** — detailed design, add remaining knowledge, develop the user interface, implement the full system.
5. **Evaluation and revision** — test against performance criteria with real cases and expert review; revise as needed.
6. **Integration and maintenance** — deploy into the working environment, integrate with existing systems, maintain and update as the domain evolves.

> 💡 Mnemonic for the phase order: **P**lease **D**on't **P**anic, **C**alm **E**ngineers **I**terate.

#### 1.c.ii Explain stages 1 and 2 — 4 marks

- **Stage 1 — Problem assessment:** clearly define the problem the ES will solve and evaluate feasibility: Is a cooperative domain expert available? Is the knowledge heuristic/symbolic (suited to an ES)? Is the domain narrow and well-defined? Will the benefits justify the cost, and are time, budget and personnel sufficient? The output is the scope and objectives of the project.
- **Stage 2 — Data and knowledge acquisition:** gather the knowledge the system needs, mainly from the **domain expert**, using techniques such as **interviews** (structured/unstructured), **protocol analysis** (expert thinks aloud while solving typical cases), **observation** of the expert at work, **questionnaires**, and **document analysis** (manuals, case records). The knowledge engineer then studies, structures and analyses what was collected. This stage is iterative and is the classic bottleneck of ES development.

---

### Question 2

#### 2.a Define knowledge representation — 2 marks

Knowledge representation is the process of **structuring and encoding knowledge in a symbolic form that a computer system can store and manipulate**, so that it can reason with it — i.e. make inferences and solve problems. (In AI, production rules are the most common form.)

#### 2.b.i How many categories is knowledge classified into? — 1 mark

Knowledge is broadly classified into **two** categories.

#### 2.b.ii Highlight and explain the categories — 7 marks

1. **Declarative knowledge ("knowing WHAT")** — descriptive facts and assertions about objects, events and situations. Represented as facts/propositions. *Examples: "Water boils at 100 °C"; "MYCIN diagnoses blood infections."*
2. **Procedural knowledge ("knowing HOW")** — knowledge of how to perform tasks: steps, procedures, strategies and heuristics. Represented as rules and procedures. *Examples: how to start a car; IF temperature > 38 °C THEN suspect fever.*

For extra credit, add: **Meta-knowledge** — knowledge *about* knowledge (which knowledge to use and when); and **heuristic knowledge** — experiential rules of thumb acquired by experts.

> ⚠️ Note: some texts classify knowledge into more types (your KBS deck lists five: declarative, procedural, causal, conditional, relational). The declarative/procedural pair is the standard 2-category answer; mentioning meta-knowledge shows depth.

#### 2.c.i How many methods can be used to represent knowledge? — 1 mark

There are **four** main methods of knowledge representation.

#### 2.c.ii Highlight and explain the knowledge representation methods — 9 marks

1. **Production rules (rule-based representation)** — knowledge as IF–THEN rules: the IF part (antecedent/condition) states when the rule applies, the THEN part (consequent/action) states the conclusion. *Example: IF it is raining THEN carry an umbrella.* Modular and easy to add/remove rules; the most widely used method in expert systems.
2. **Semantic networks** — knowledge as a **graph**: nodes represent objects/concepts, labelled links represent relationships ("is-a", "has-a", "part-of", "instance-of"). *Example: Robin —is-a→ Bird —has-a→ Wings.* Natural for showing relationships and supports inheritance.
3. **Frames** — knowledge packaged into structured records for objects/concepts, with **slots** (attributes) and **facets** (slot properties: value, default, type). Frames form hierarchies with inheritance. *Example: a "Bird" frame with slots wings=2, can-fly=yes.* Good for stereotyped objects; combines declarative and procedural knowledge.
4. **Logic (predicate/propositional logic)** — knowledge as formal logical statements, allowing precise, unambiguous representation and sound inference. *Example: ∀x Bird(x) → CanFly(x).* Prolog implements this style.

*(Other methods worth naming in one line each if you have time: decision trees, scripts — stereotyped event sequences, ontologies — shared formal vocabularies.)*

> 💡 Mnemonic for the four: **R**obins **S**ing **F**or **L**ove — Rules, Semantic nets, Frames, Logic.

---

### Question 3

#### 3.a Five factors that suggest when an expert system is appropriate — 5 marks

1. **Human expertise is scarce or expensive** — the ES captures and distributes rare expert knowledge (experts get tired, retire and die; an ES doesn't).
2. **The problem domain is narrow and well-defined** — focused, specific domains suit ES; broad general problem-solving does not.
3. **The problem needs symbolic reasoning and heuristics** rather than pure numeric computation — this is what conventional programs handle poorly.
4. **Consistency and reliability are required** — an ES applies the same rules the same way every time, eliminating human inconsistency, fatigue and bias.
5. **Explanation of reasoning is important** — in domains like medicine or credit approval, the system must justify *how* and *why* it reached a conclusion; expert systems can.

*(Spares: expertise is needed in many locations at once/hostile environments; knowledge would otherwise be lost when the expert leaves; the task takes an expert a reasonably short time — the "phone-call rule".)*

#### 3.b Five application areas of expert systems — 15 marks

For 3 marks each: **name the area, explain what the ES does there, and give an example.**

1. **Medical diagnosis and healthcare** — ES assist doctors to diagnose diseases from symptoms and test results, recommend treatments, and flag drug interactions; they apply vast medical knowledge consistently, helping with rare/complex conditions. *Classic example: **MYCIN** — diagnosed infectious blood diseases and recommended antibiotics.*
2. **Finance and banking** — credit risk assessment, loan approval, fraud detection, investment advice and portfolio management; the ES analyses customer and market data and applies lending rules consistently and objectively. *Example: credit-scoring/loan-approval advisors used by banks.*
3. **Manufacturing, engineering and process control** — configuration, monitoring, fault diagnosis, scheduling and quality control of complex industrial processes; increases efficiency and reduces downtime. *Classic example: **XCON (R1)** — configured DEC VAX computer systems.*
4. **Geology and mineral exploration** — interpreting geological and field data to advise on where to drill and what mineral deposits are likely present. *Classic example: **PROSPECTOR** — advised on mineral-deposit exploration.*
5. **Education and training** — intelligent tutoring systems that adapt to each student, give customized feedback, and act as trainers/simulators for complex skills (also used for troubleshooting help-desks and customer support chatbots).

*(Spares: chemistry/scientific analysis — **DENDRAL** inferred molecular structures from mass-spectrometry data; agriculture — crop disease diagnosis; law — legal advice systems; customer service help desks.)*

---

## ⚡ Last-minute cram sheet

- **ES definition:** emulates the decision-making/cognitive skills of a human expert in a narrow (task) domain, and can explain its reasoning.
- **Area of human intellectual endeavor = TASK DOMAIN.**
- **3 components:** Knowledge base (the knowledge) · Inference engine (the brain/rule interpreter/reasoning) · User interface (communication).
- **Heuristic** = rule of thumb, NOT guaranteed (vs algorithm = guaranteed).
- **Building an ES = knowledge engineering; builders = knowledge engineers.**
- **5 team members:** Domain expert, Knowledge engineer, Programmer, Project manager, End-user (*Don't Keep People Praying Endlessly*).
- **2 inference types:** Forward chaining (data-driven) · Backward chaining (goal-driven).
- **2 ES tools:** Shells (CLIPS) · Programming languages (LISP, PROLOG).
- **KB development, 5 steps:** Acquisition → Validation → Representation → Inferencing → Explanation (*All Valid Rules Infer Explanations*).
- **KE methodology, 6 phases:** Problem assessment → Data & knowledge acquisition → Prototype → Complete system → Evaluation & revision → Integration & maintenance (*Please Don't Panic, Calm Engineers Iterate*).
- **Knowledge: 2 categories** — Declarative (what) · Procedural (how) [+ meta-knowledge].
- **KR: 4 methods** — Rules, Semantic nets, Frames, Logic (*Robins Sing For Love*).
- **Famous systems:** MYCIN (medicine), DENDRAL (chemistry), XCON/R1 (computer configuration), PROSPECTOR (geology).


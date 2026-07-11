# CSC 432 — Principles of Programming Languages II

## Exam Prep Built Strictly from the Lecturer's Course Material

**How this file is organised:**

- **Section A** — Past-exam questions (Set 1 = 2023/2024, Set 2 = 2021/2022) that **can be answered from the course material**, answered using the material's own framing.
- **Section B** — **Likely questions** predicted from the material, focusing on the topics the material covers heavily but the past papers barely touched (Effects of Scale, Parameter Passing, Generics, Modules, OOP internals, Functional & Logic).
- **Appendix** — Past-paper items that are **outside** these materials (use the `set 1`/`set 2` answer files for those).

---

# SECTION A — Past Questions Answerable from the Course Material

*Each item lists the past-paper source(s). Where the same question repeats across sets, it is answered once.*

## A1. Outline the most commonly used techniques for describing programming-language semantics

*(Set 1 Q1a-i, 3 Mks · Set 2 Q6a-i, 5 Mks — Material: Topic/Module 3)*

Semantics defines **what programs mean** (as opposed to syntax, which defines their form). The three standard techniques are:

1. **Operational Semantics** — defines meaning by how a program **executes step-by-step on an abstract machine**. Two variants: **small-step (structural)** describes one reduction at a time (e.g. `⟨x := 5+3, σ⟩ → ⟨x := 8, σ⟩ → ⟨skip, σ[x→8]⟩`); **big-step (natural)** gives the final result directly (`⟨e,σ⟩ ⇓ v`). Best for interpreter/compiler construction.
2. **Denotational Semantics** — assigns each construct a **mathematical object (denotation)** via a semantic function, e.g. `M⟦e1+e2⟧ = M⟦e1⟧ + M⟦e2⟧`. Its key property is **compositionality** (meaning of the whole is built from meanings of the parts). Best for reasoning about program equivalence and language design.
3. **Axiomatic Semantics** — specifies meaning through **logical assertions** using a proof system (**Hoare Logic**). A **Hoare triple** `{P} C {Q}` means: if precondition `P` holds before `C` runs and `C` terminates, then postcondition `Q` holds after. Basis of formal program verification.

*(Informal semantics — plain natural-language description, as in most commercial standards — is also mentioned in the material, but is imprecise and can be ambiguous.)*

## A2. Outline the three main types of grammar used in programming languages

*(Set 1 Q2a-i, 4½ Mks · Set 2 Q4a-ii, 4½ Mks — Material: Module 2.2, Chomsky Hierarchy)*


| Grammar type                   | Chomsky class | Power    | Used for                                                                    | Recogniser               |
| ------------------------------ | ------------- | -------- | --------------------------------------------------------------------------- | ------------------------ |
| **Regular Grammar**            | Type 3        | Weakest  | **Lexical structure** — tokens (identifiers, keywords, literals)            | Finite automaton (DFA)   |
| **Context-Free Grammar (CFG)** | Type 2        | Medium   | **Phrase structure** — expressions, statements (the syntax proper)          | Pushdown automaton       |
| **Context-Sensitive Grammar**  | Type 1        | Stronger | **Some semantic constraints** (e.g. declare-before-use, C++ template rules) | Linear-bounded automaton |


Most programming-language **syntax sits at Type 2 (CFG)**, with **lexical structure at Type 3 (regular)**. *(Type 0, Unrestricted, is the most powerful but rarely used in practice.)*

## A3. Differentiate between Static and Dynamic Type Checking (with examples)

*(Set 1 Q2a-ii, 4 Mks · Set 2 Q4a-iii "advantages of dynamic", Q5a — Material: Module 4.3)*


| Property         | Static Type Checking                      | Dynamic Type Checking                                            |
| ---------------- | ----------------------------------------- | ---------------------------------------------------------------- |
| When performed   | **Compile time**                          | **Runtime** (as code executes)                                   |
| Errors           | Caught **before execution**; cheap to fix | Surface as **runtime exceptions**, only when the buggy path runs |
| Runtime overhead | **None** (types erased after compilation) | Type **tags checked on every operation**                         |
| Flexibility      | Less (constrained by type rules)          | More (duck typing, open classes)                                 |
| Refactoring      | Compiler finds all affected sites         | Only testing finds issues                                        |
| Examples         | C, Java, Haskell, Rust                    | Python, JavaScript, Ruby                                         |


**Example — static (Java):** `int x = "hello";` → compile-time error: incompatible types.
**Example — dynamic (Python):** `x = "hello"; y = x + 5` → runtime `TypeError` only when that line executes.

**Advantages of dynamic type checking** *(Set 2 Q4a-iii)*: (1) **flexibility / rapid prototyping** — no type declarations needed; (2) **conciseness** — shorter code; (3) **natural polymorphism** — one function works on many types without type parameters.

**Related — Strong vs Weak typing:** *Strongly typed* (Python, Java) — every expression has a well-defined type, no unsafe implicit coercions; *Weakly typed* (C, JavaScript) — silent implicit conversions can change types.

## A4. Describe "Type Checking" and state its two main uses

*(Set 1 Q4a-ii/Q5a-i · Set 2 Q5a — Material: Module 4.3)*

**Type checking** is the process of **verifying that operands and operators are type-compatible** — i.e. that operations are applied only to values of the types they are defined for. It uses a type system of rules and can be **static** (compile time) or **dynamic** (runtime).

**Two main uses:**

1. **Safety — error detection & prevention.** Catches type errors (e.g. adding a string to an integer, calling a missing method) before they cause wrong results, crashes, or security holes. Static checking catches them at every call site before execution.
2. **Efficiency — storage & code generation.** Knowing types lets the compiler **allocate the right amount of storage** and **generate efficient machine code** (instruction selection, no runtime tag checks).

*(The material also lists documentation and abstraction as further purposes of types.)*

## A5. Declarations: the model, and the purpose of declarations

*(Set 1 Q1b-i/ii · Set 2 Q6b-i/ii — Material: Module 4.2)*

A **declaration** introduces a **name (identifier)** and **binds** it to an entity (value, type, or location), e.g. `int x = 5` binds `x` to a location holding 5.

**Every declaration has four properties:**


| Property       | Meaning                                                                             |
| -------------- | ----------------------------------------------------------------------------------- |
| **Binding**    | Association of the name with an entity (value/type/location)                        |
| **Visibility** | The textual region where the binding can be **seen and used**                       |
| **Scope**      | The region of program text where the declaration is **active** (lexical vs dynamic) |
| **Lifetime**   | The **duration during execution** for which the binding exists                      |


**Two types of declaration** *(standard distinction; the material's model above supports it)*: **Explicit** — the programmer states the type (`int x;`); **Implicit** — the type is inferred from context/usage (e.g. Python, or Java `var`).

**Purpose of declarations:**

1. **Associate a name with a type/entity** (binding).
2. **Define scope and visibility** — control where the name is usable.
3. **Define lifetime** — when storage is allocated and released.
4. **Enable type checking and storage allocation** by the compiler.
5. **Document intent** — communicate the kind of data to other programmers.

## A6. Garbage Collection in Java — the two main types of GC activity (and the algorithms)

*(Set 1 Q6a-iii, 4 Mks — Material: Module 4.4 + main-notes 4.4.4)*

**Garbage Collection (GC)** = automatic reclamation of heap memory occupied by objects **no longer reachable** from the program. It eliminates dangling pointers, double-frees, and leaks.

**The two main GC activities in the JVM (generational GC):**

1. **Minor GC (Young Generation)** — collects the **Eden + Survivor** spaces where **most objects die young**. Very frequent and **fast** (~1–10 ms): live objects are copied to a survivor space and aged; objects surviving enough cycles are **promoted** to the Old Generation; Eden is cleared.
2. **Major / Full GC (Old Generation)** — collects long-lived objects when the Old Generation fills up. **Slower** (~100–500 ms) and typically uses **mark–sweep–compact**.

**Underlying algorithms (context):**


| Algorithm          | Principle                                 | Advantage                  | Disadvantage              |
| ------------------ | ----------------------------------------- | -------------------------- | ------------------------- |
| Reference Counting | Free when ref-count = 0                   | Incremental, low latency   | **Cannot collect cycles** |
| Mark-and-Sweep     | Mark reachable from roots, sweep the rest | Handles cycles             | Stop-the-world pauses     |
| Copying            | Copy live objects to a new space          | Compacts heap              | Needs double space        |
| Generational (JVM) | Collect young space more often            | Very efficient in practice | Complex                   |


## A7. The syntax of a language can be described by formal and informal techniques — describe them

*(Set 2 Q6a-ii, 4½ Mks — Material: Topic 2 + Module 3.1)*

**Syntax** = the rules defining the valid **form/structure** of programs, independent of meaning. It is described at two levels — **lexical** (tokens) and **phrase** (how tokens combine).

**Formal techniques** (precise, machine-processable):

1. **Context-Free Grammars (BNF/EBNF)** — production rules define phrase structure; parsers (LL/LR) are built from them to produce parse trees/ASTs. e.g. `<expr> ::= <expr> "+" <term> | <term>`.
2. **Regular Expressions** — define the **lexical** syntax (patterns for identifiers, literals, operators); implemented as DFAs in the scanner.

**Informal techniques** (readable, but imprecise):

1. **Natural-language descriptions** — language manuals explain rules in English.
2. **Syntax (railroad) diagrams** — graphical depiction of valid token sequences.
3. **Examples** — sample code snippets from which learners infer the rules.

In practice, specifications combine **formal** (for precision and tooling) and **informal** (for teaching/documentation).

## A8. Differentiate Syntax vs Semantics; and Parsing vs Parser

*(Set 2 Q4b-i, Q4b-ii — Material: Module 1.2 & Topic 2/3)*

**Syntax vs Semantics**


|                 | Syntax                                     | Semantics                                       |
| --------------- | ------------------------------------------ | ----------------------------------------------- |
| Concerns        | The **form/structure** of code             | The **meaning** of code                         |
| Example (valid) | `int x = 10 + 5;` is well-formed           | what `+` computes and what the statement does   |
| Checked by      | Grammars (BNF/EBNF), regexes               | Operational/denotational/axiomatic semantics    |
| Errors          | Syntax errors (missing `;`, bad structure) | Semantic errors (type mismatch, undeclared var) |


**Parsing vs Parser** — *parsing* is the **process** of analysing a token stream against the grammar to determine structure and build a **parse tree/AST**; a *parser* is the **program/component** that performs parsing (hand-written recursive-descent, or generated by yacc/bison/ANTLR). One is an activity; the other is the tool that carries it out.

## A9. Expression notations — infix → postfix conversion and postfix evaluation

*(Set 1 Q4b-ii & Q5b · Set 2 Q5b & Q5c — Material: Topic 2 / Module 1.3)*

Three equivalent notations: **Infix** (`a OP b`, needs precedence/parentheses), **Prefix/Polish** (`OP a b`, never needs parentheses), **Postfix/RPN** (`a b OP`, never needs parentheses — evaluated with a stack in one pass). Build the **AST** first; **pre-order** read = prefix, **post-order** read = postfix.

**(a) Convert `(A − (B + C)) * D ^ (E + F)` to postfix** → `**A B C + - D E F + ^ *`**

- `B + C` → `B C +`; then `A − (…)` → `A B C + -`
- `E + F` → `E F +`; then `D ^ (…)` → `D E F + ^`
- product → `A B C + - D E F + ^ *`

**(b) Evaluate `6 2 3 + - 3 8 2 / + * 2 ^ 3 +`** (Set 1 Q5b, Set 2 Q5c-i) → **52**


| Token | Op          | Stack      |
| ----- | ----------- | ---------- |
| 6 2 3 | push        | 6, 2, 3    |
| +     | 2+3=5       | 6, 5       |
| −     | 6−5=1       | 1          |
| 3 8 2 | push        | 1, 3, 8, 2 |
| /     | 8/2=4       | 1, 3, 4    |
| +     | 3+4=7       | 1, 7       |
| *     | 1×7=7       | 7          |
| 2     | push        | 7, 2       |
| ^     | 7²=49       | 49         |
| 3     | push        | 49, 3      |
| +     | 49+3=**52** | **52**     |


**(c) Evaluate `6 5 2 3 + 8 * + 3 + *`** (Set 1 Q4b-ii, Set 2 Q5c-ii) → **288**

`2 3 +`=5 → `5 8 *`=40 → `5 40 +`=45 → `45 3 +`=48 → `6 48 *`=**288**.

## A10. The phases by which a compiler processes source code

*(Set 2 Q3b "compilation phases" — Material: Topic 2 lexical/syntax + Topic 4 semantic/codegen)*

Grounded in the material's pipeline:

1. **Lexical analysis (scanning)** — characters → **tokens** (using regular expressions/DFA). First phase.
2. **Syntax analysis (parsing)** — tokens → **parse tree / AST** (using a CFG); detects syntax errors.
3. **Semantic analysis** — walks the AST for **type checking and scope resolution**; detects semantic errors.
4. **Optimisation** — transforms the AST/intermediate form (e.g. **constant folding** `3+4 → 7`) to improve performance.
5. **Code generation** — produces target/executable code.

*(The AST is the central data structure feeding semantic analysis, optimisation, code generation, and interpretation.)*

---

# SECTION B — Likely Exam Questions from the Course Material

*These target the material's heavily-developed topics that the past papers barely tested. Each is a strong candidate.*

## Topic 1 — Effects of Scale on Programming Methodology *(not tested in past papers → high-priority)*

**B1.1 — State Brooks's Law and show its cost with a calculation.**
Brooks's Law (1975): *"Adding manpower to a late software project makes it later."* With `n` developers the number of communication channels is `**n(n−1)/2`** (quadratic). A new developer also needs weeks of onboarding, during which experienced staff are pulled off coding.
*Worked:* a 12-person team → `12·11/2 = 66` channels. Add 3 → `15·14/2 = 105`. **39 new channels** plus onboarding cost, so short-term output **falls**.

**B1.2 — Distinguish essential vs accidental complexity (Brooks).**

- **Essential complexity** — inherent in the problem itself; no language feature removes it (a tax engine must model the tax law).
- **Accidental complexity** — introduced by our tools/languages/choices (e.g. 40 lines of getter/setter boilerplate). Good language design attacks it: **GC** removed manual memory management, **generics** removed per-type container copies, **Option/Maybe** reduced null errors, **async/await** removed callback hell.

**B1.3 — Define coupling and cohesion; state the architectural ideal.**

- **Coupling** — degree to which a module depends on others. Tight coupling ⇒ cannot compile/test/understand a module in isolation.
- **Cohesion** — degree to which a module's elements belong together; a cohesive module does one thing well.
- **Ideal: maximise cohesion within modules, minimise coupling between them.** Languages support this via private fields, module systems, and typed interfaces. (Worst→best coupling: content → common → control → data.)

**B1.4 — Contrast programming "in the small" vs "in the large" (DeRemer & Kron).**


|                 | In the Small                       | In the Large                            |
| --------------- | ---------------------------------- | --------------------------------------- |
| Primary concern | Algorithm correctness & efficiency | Module composition & team coordination  |
| Key tools       | Debugger, profiler, unit tests     | Module system, build tool, versioning   |
| Error detection | Testing, code review               | Type system, contracts, static analysis |
| Change impact   | Local                              | Cross-team, needs migration             |


## Topic 2 — Syntactic Structure

**B2.1 — Draw the AST for `(a + b) * (c − d)` and explain what an AST discards.**

```
        *
       / \
      +   -
     / \ / \
    a  b c  d
```

An **AST** captures hierarchical structure while **discarding parentheses, punctuation, and redundant non-terminals** — the **tree shape itself encodes precedence and associativity**. It is the primary structure for semantic analysis, optimisation, code generation, and interpretation.

**B2.2 — Distinguish BNF and EBNF.** BNF (Backus–Naur Form, ALGOL 60) uses `<nonterminal> ::= alt1 | alt2`, with recursion for repetition. **EBNF** adds `{X}` (zero-or-more), `[X]` (optional), `(X|Y)` (grouping), mapping directly onto iterative parsers, e.g. `expr = term {("+"|"-") term}`. **Left recursion** encodes left-associativity; **right recursion** encodes right-associativity (`2 ** 3 ** 2 = 512`).

**B2.3 — What is an ambiguous grammar? Give an example.** A grammar is **ambiguous** if some string has **two or more distinct parse trees**. Example: `E → E+E | E*E | id` gives two trees for `id + id * id`. The **dangling-else** problem is another. Fix by rewriting with a precedence hierarchy (`E→E+T; T→T*F; F→(E)|id`) or requiring braces.

**B2.4 — State the Chomsky hierarchy and where PLs sit.** Type 3 Regular (DFA, tokens) ⊂ Type 2 Context-Free (PDA, phrase structure) ⊂ Type 1 Context-Sensitive (LBA, some static-semantic rules) ⊂ Type 0 Unrestricted (Turing machine). **PL syntax = Type 2; lexing = Type 3.**

**B2.5 — Compare LL and LR parsing.** LL(k): **top-down**, left-derivation, **cannot handle left recursion**, usually hand-written recursive descent, clearer errors. LR/LALR(1): **bottom-up**, right-derivation, handles left recursion, generated by yacc/bison/ANTLR, more powerful but cryptic errors.

## Topic 3 — Semantics (worked)

**B3.1 — Give the big-step derivation of `(2 + 3) * 4`.** `⟨2,σ⟩⇓2` and `⟨3,σ⟩⇓3` (NUM) ⇒ `⟨2+3,σ⟩⇓5` (ADD); `⟨4,σ⟩⇓4` (NUM); therefore `⟨(2+3)*4,σ⟩⇓20` (MUL).

**B3.2 — Compute the denotational meaning of `x := 2 ; y := x + 1 ; z := x * y`.** Compose state transformers left-to-right: `{x:2}` → `{x:2, y:3}` → `{x:2, y:3, z:6}`. Key property: **compositionality** (`⟦S₁;S₂⟧ = ⟦S₂⟧ ∘ ⟦S₁⟧`).

**B3.3 — State the Hoare triple and verify assignment.** `{P} C {Q}`: if `P` holds before `C` and `C` terminates, `Q` holds after. Assignment axiom: `{Q[e/x]} x:=e {Q}`. E.g. `{x+1>0} x:=x+1 {x>0}`. **While rule:** `{I} while B do C {I ∧ ¬B}`, where `I` is the **loop invariant**.

## Topic 4 — Declarations & Types

**B4.1 — Name vs structural type equivalence (and why name is safer).** **Name equivalence** — two types are equal only if they share the **same name** (Java, Ada, Pascal). **Structural equivalence** — equal if they have the **same shape** (TypeScript, Go anon types). Name equivalence is safer: two records both `{value: double}` named `Celsius` and `Fahrenheit` are interchangeable under structural rules — the kind of unit mix-up behind the **Mars Climate Orbiter** loss; name equivalence would be a compile error.

**B4.2 — List the binding times.** Language-design time (meaning of `+`) → compile time (variable type, struct layout) → link time (external addresses) → load time (absolute addresses) → run time (variable values). Only run-time bindings are changeable during execution.

**B4.3 — Static vs dynamic scope.** **Static/lexical scope** (all modern languages): a free variable resolves to the **nearest enclosing definition in the source text** — depends on where a function is *defined*. **Dynamic scope** (old Lisp, TeX): resolves to the **most recent binding on the call stack** — depends on who *called* it, which makes reasoning hard.

## Topic 5 — Abstraction Mechanisms *(parameter passing — untested, high-priority)*

**B5.1 — Describe the parameter-passing mechanisms.**


| Mechanism                | How it works                                  | Effect on caller             | Languages                       |
| ------------------------ | --------------------------------------------- | ---------------------------- | ------------------------------- |
| **Call by Value**        | Copy of argument passed                       | Caller **unchanged**         | C, Java (primitives), Python    |
| **Call by Reference**    | Address passed; formal aliases the actual     | Caller variable **modified** | C++ `&`, Pascal `var`, C# `ref` |
| **Call by Value-Result** | Copy in at call, copy back at return          | Caller updated **on return** | Ada `in out`                    |
| **Call by Name**         | Argument expression **re-evaluated each use** | Lazy; re-evaluated           | ALGOL 60, macros                |
| **Call by Need (lazy)**  | Evaluated at **first use, then memoised**     | Cached after first use       | Haskell, Scala `lazy val`       |


**B5.2 — Trace: `void triple(int n){ n=n*3; } … int x=7; triple(x);` — output?** **7.** Call by value copies 7 into `n`; `n` becomes 21 locally and is destroyed on return; `x` is untouched.

**B5.3 — What is an activation record?** A **stack frame** pushed on each call, holding: **return address**, **saved/previous frame pointer** (dynamic link), **static link** (for nested-scope access), **parameters**, **local variables**, **temporaries**, and space for the **return value**. Recursion works because each call gets its own frame (`fact(3)→fact(2)→fact(1)→fact(0)`).

**B5.4 — Explain Tail-Call Optimisation (TCO).** A **tail call** is the **last action** of a function (nothing pending on its result). TCO rewrites it as a **jump reusing the current frame**, so tail-recursive functions run in **O(1) stack space**. `factTail(n,acc)` is tail-recursive; naïve `n*factorial(n-1)` is **not** (the multiply is pending). *Note: Java and Python do not implement TCO; Scheme/Haskell do.*

**B5.5 — What is a closure?** A function **plus the environment it captured** from its enclosing scope. `makeCounter()` returning `() -> ++count[0]` keeps `count` alive between calls (1, 2, 3…). Enables callbacks, counter factories, currying/partial application.

## Topic 6 — Parameterised Types (Generics)

**B6.1 — Why generics? Give the motivation.** They resolve **reuse vs type-safety**. Without them you either duplicate a container per type or use `Object` and lose safety (`(int) stack.pop()` risks `ClassCastException`). `Stack<Integer>` gives **reuse + compile-time safety, no cast**.

**B6.2 — Explain type bounds.** `<T extends Comparable<T>>` (Java) / `Ord a =>` (Haskell) / `T: PartialOrd` (Rust) constrain `T` so the body may use the bounded operations (`compareTo`, `>`). `max(List<T>)` needs `Comparable`.

**B6.3 — Explain variance and the PECS rule.** Java generics are **invariant** (`List<Dog>` is *not* a `List<Animal>` — else you could insert a `Cat`). Wildcards relax this: `<? extends T>` = **covariant producer (read-only)**; `<? super T>` = **contravariant consumer (write-only)**. **PECS: Producer Extends, Consumer Super** — a copy method uses `copy(List<? extends T> src, List<? super T> dst)`.

**B6.4 — Java type erasure vs C++ templates.** Java **erases** type parameters at compile time and inserts casts → one bytecode for all instantiations, but **no `new T()`, no `new T[]`, no `instanceof List<String>`**, and `Stack<Integer>`/`Stack<String>` share one `Class`. C++ **instantiates** separate code per type → full runtime type info, `new T()` legal, but larger code and slower compiles.

## Topic 7 — Modules

**B7.1 — Properties of a good module system.** Encapsulation (hide internals), separate compilation (compile against interface only), namespace management (avoid name clashes), explicit dependencies, interface abstraction (program to a contract), and parameterised modules (functors).

**B7.2 — State the Parnas Principle.** Decompose a system by **what each module hides — its "secret"**; a module should hide the **design decision most likely to change independently**. Clients depend only on the **interface**; when the hidden decision changes, only the implementation changes. E.g. a `StudentRepository` interface with Postgres/Mongo/InMemory implementations — swap by changing **one binding**; test with the in-memory one, no database.

**B7.3 — Functor vs generic.** A **generic** maps a **type → type** (`Stack<T>`). An **ML/OCaml functor** maps a **module → module**: it takes a whole module (type **plus** its operations, e.g. `Elem.compare`) and returns a new module (`MakeSortedSet(IntOrd)`), which is strictly more powerful.

**B7.4 — Why must module dependencies form a DAG?** A **cycle** prevents separate compilation, creates tight coupling, and blocks isolated testing. Fix by extracting shared types into a dependency-free module, or by **dependency inversion** (introduce an interface both sides depend on).

## Topic 8 — Object-Oriented Paradigm

**B8.1 — The four pillars of OOP.**

- **Encapsulation** — bundle data + methods, restrict access via visibility modifiers, enforce invariants (a `Money` type rejecting negative amounts at construction).
- **Inheritance** — a subclass acquires a superclass's members; models *is-a*, enables reuse.
- **Polymorphism** — one interface, many implementations; correct method chosen at **runtime** (dynamic dispatch). Also compile-time (overloading) and parametric (generics).
- **Abstraction** — expose essential behaviour through an interface, hide implementation (a `PaymentGateway` with Stripe/PayPal/Mock behind it).

**B8.2 — Explain dynamic dispatch / vtables.** Each object carries a hidden **vtable pointer** to its class's table of method pointers. `Animal a = new Dog(); a.makeSound();` → the runtime dereferences the vtable pointer (which points to **Dog's** vtable), finds `makeSound`, and calls `Dog::makeSound()` → "Woof". The compile-time type only type-checks; dispatch uses the actual object's vtable. In Java every non-private/non-final/non-static method is virtual; in C++ only `virtual` ones.

**B8.3 — State the SOLID principles.** **S**ingle Responsibility (one reason to change), **O**pen/Closed (open for extension, closed for modification), **L**iskov Substitution (subtypes substitutable for base types), **I**nterface Segregation (many small interfaces > one fat one), **D**ependency Inversion (depend on abstractions, not concretions).

**B8.4 — Give a Liskov Substitution violation.** `Square extends Rectangle` overriding `setWidth/setHeight` to keep sides equal breaks `r.setWidth(4); r.setHeight(5); assert r.area()==20;` (a Square gives 25). Fix: make both implement a read-only `Shape` interface, or make `Rectangle` immutable.

**B8.5 — Name common design patterns.** *Creational:* Factory Method, Abstract Factory, Singleton, Builder. *Structural:* Adapter, Decorator, Proxy. *Behavioural:* Observer, Strategy, Command, Template Method. (e.g. **Strategy** = swap interchangeable algorithms behind an interface at runtime; **Observer** = event-bus notification.)

**B8.6 — Explain the diamond problem.** In C++, `D` inheriting from both `B` and `C` (each from `A`) gets **two copies of `A`** and an **ambiguous** `f()`. Fixes: **virtual inheritance** (one shared `A`), or Java's approach — **no multiple class inheritance**; multiple interface inheritance is allowed, and conflicting default methods must be overridden explicitly.

## Topic 9 — Functional & Logic Paradigms

**B9.1 — What is referential transparency? Give pure vs impure examples.** An expression is **referentially transparent** if it can be **replaced by its value** without changing the program. **Pure/transparent:** `2+3`, `sqrt(4)`, `map(*2)([1,2,3])` — same input → same output, so they can be **cached, reordered, parallelised**. **Impure:** `random()`, `queue.pop()`, `Date.now()` — depend on/modify hidden state.

**B9.2 — Explain the three fundamental higher-order functions.** `**map`** applies a function to every element (`map (+1) [1,2,3] = [2,3,4]`); `**filter**` keeps elements passing a predicate (`filter even [1..10]`); `**fold/reduce**` collapses a list to one value (`foldr (+) 0 [1..5] = 15`). Composed: sum of squares of odds = `foldr (+) 0 . map (^2) . filter odd`.

**B9.3 — Prolog: facts, rules, and queries.** Lowercase = atom/functor, Uppercase = variable, `:-` = "if".

```prolog
parent(tom, bob).  parent(bob, ann).        % facts
ancestor(X,Y) :- parent(X,Y).               % rule (base)
ancestor(X,Y) :- parent(X,Z), ancestor(Z,Y).% rule (recursive)
?- ancestor(tom, ann).   % true (tom→bob→ann)
```

**B9.4 — What is unification?** The core mechanism: two terms **unify** if they can be made identical by consistently substituting values for variables. `f(X,3) = f(2,Y)` ⇒ `X=2, Y=3`; `f(X,X) = f(1,2)` fails; `[H|T] = [1,2,3]` ⇒ `H=1, T=[2,3]`. (The **occurs check** prevents circular terms like `X = f(X)`.)

**B9.5 — Explain backtracking.** Prolog searches **depth-first**; on failure it **backtracks** to the last choice point and tries the next alternative. Because it uses unification + backtracking, a predicate like `append/3` runs **backwards** too — `append(X,Y,[1,2,3])` generates every way to split the list.

**B9.6 — What is a monad (briefly)?** A type with `return :: a -> m a` (wrap a value) and `>>= :: m a -> (a -> m b) -> m b` (**bind** / sequence). The **Maybe monad** chains fallible steps so `Nothing` propagates automatically (`safeDiv x y >>= safeSqrt`); the **IO monad** sequences effects while keeping the rest pure.

**B9.7 — Compare imperative/OOP, functional, and logic paradigms.**


| Feature       | Imperative / OOP           | Functional                  | Logic                     |
| ------------- | -------------------------- | --------------------------- | ------------------------- |
| Basic unit    | Statements / Objects       | Functions / Expressions     | Facts / Rules             |
| State         | Mutable, central           | Immutable, no side effects  | No explicit state         |
| Control flow  | `if`, `for`, `while`       | Recursion, higher-order fns | Backtracking, unification |
| Key languages | C, Java, Python            | Haskell, Erlang, ML         | Prolog, Datalog           |
| Best for      | System/enterprise software | Data transformation, AI     | Constraint solving, AI    |


---

# Appendix — Past-Paper Items NOT Covered by These Materials

These appeared in the past papers but are **outside** the two lecture-note files (they come from Sebesta-style intro material). Use the `Principle of programng lang II set 1/2.md` answer files for them:

- **Criteria for language evaluation** — expressivity, well-definedness, portability, efficiency, pedagogy, generality *(Set 2 Q2a)*
- **Reasons for studying programming-language concepts** *(Set 2 Q2b)*
- **Application domains of programming languages** — scientific, business, AI, systems, web *(Set 1 Q6a-ii, Set 2 Q3a-ii)*
- **Four general methods of implementing a language** — compilation, interpretation, hybrid, … *(Set 1 Q6a-i, Set 2 Q3a-i)*
- **Compiler vs Interpreter; compiled vs interpreted language** *(Set 1 Q2b-ii, Q5a-ii)*
- **Features of an ideal programming language** *(Set 1 Q3a-i)*
- **Source vs object code; Compiler vs Assembler; Hardware vs Software; Linker vs Editor** *(Set 2 Q1a; Set 1 Q2a-iii)*
- **JVM & platform independence; Java array/class-variable snippets; Python `list` slicing output** *(Set 1 Q3a, Q6b)*
- **Regular-set union closure proof** *(Set 1 Q4a-iii)* — the material covers regular grammars/Chomsky but not this closure proof.

> **Tip:** The examiner reuses the covered core every year — **semantics techniques, grammar types, type checking (static/dynamic), declarations, postfix conversion/evaluation, and garbage collection** are the safest bets from Section A. Section B (Scale, parameter passing, generics, modules, OOP internals, functional/logic) reflects where the new lecture material is richest and least-tested — study it for the "surprise" questions.


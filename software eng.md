**Question 1**

**(a) Decision Table for Discount Rules (16 marks)**

To construct a decision table, we need to identify the conditions and actions based on the given discount rules.

**Conditions:**

1.  **Customer Type:** Existing Customer (Y/N)
2.  **Payment Method:** Cash (Y/N)
3.  **Sale Value:** Over #1000 (Y/N)

**Actions:**

*   Apply 5% discount
*   Apply 10% discount
*   Apply 15% discount
*   Apply No discount

**Decision Table:**

| Condition                                   | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5 | Rule 6 | Rule 7 | Rule 8 |
| :------------------------------------------ | :----- | :----- | :----- | :----- | :----- | :----- | :----- | :----- |
| **Existing Customer?**                      | Y      | Y      | Y      | Y      | N      | N      | N      | N      |
| **Payment Method: Cash?**                   | Y      | Y      | N      | N      | Y      | Y      | N      | N      |
| **Sale Value Over #1000?**                   | Y      | N      | Y      | N      | Y      | N      | Y      | N      |
| **Actions:**                                  |        |        |        |        |        |        |        |        |
| Apply 5% discount                         |        | X      |        | X      |        |        |        |        |
| Apply 10% discount                        |        |        | X      |        |        |        |        |        |
| Apply 15% discount                        | X      |        |        |        |        |        |        |        |
| Apply No discount                         |        |        |        |        | X      | X      | X      | X      |

**Explanation of Rules:**

*   **Rule 1:** Existing customer, pays cash, sale over #1000 -> 15% discount. (Rule iii)
*   **Rule 2:** Existing customer, pays cash, sale not over #1000 -> 5% discount. (Rule i)
*   **Rule 3:** Existing customer, pays credit, sale over #1000 -> 10% discount. (Rule ii)
*   **Rule 4:** Existing customer, pays credit, sale not over #1000 -> 5% discount. (Rule i)
*   **Rule 5:** New customer, pays cash, sale over #1000 -> No discount. (Rule iv)
*   **Rule 6:** New customer, pays cash, sale not over #1000 -> No discount. (Rule iv)
*   **Rule 7:** New customer, pays credit, sale over #1000 -> No discount. (Rule iv)
*   **Rule 8:** New customer, pays credit, sale not over #1000 -> No discount. (Rule iv)

**(b) Concepts of Software Implementation (4 marks)**

Software implementation is the stage in the software development lifecycle where the design is translated into actual code. It involves writing, testing, and debugging the source code to create a working software system. Key concepts with reference to Programming methods and Documentation are:

**(i) Programming Methods:**

*   **Coding Standards:** Following predefined coding standards (like naming conventions, indentation, commenting) ensures code readability, maintainability, and consistency across the project. This makes it easier for developers to understand and work with the codebase.
*   **Structured Programming:**  This method emphasizes breaking down the program into smaller, manageable modules or functions. It promotes clarity and reduces complexity by avoiding unstructured jumps (like `goto` statements) and focusing on control structures (sequence, selection, iteration).
*   **Object-Oriented Programming (OOP):**  If the design is object-oriented, implementation involves using OOP principles like encapsulation, inheritance, and polymorphism. This approach organizes code around "objects" that combine data and behavior, promoting modularity and reusability.
*   **Choosing the Right Language:** Selecting a programming language that is appropriate for the project requirements, considering factors like performance needs, platform, available libraries, and team expertise is crucial for effective implementation.

**(ii) Documentation:**

*   **Code Comments:**  Adding meaningful comments within the code to explain the purpose of sections, complex logic, or algorithms. This is essential for future maintenance and understanding.
*   **Inline Documentation:**  Documentation embedded directly within the code, often using specific formats (like Javadoc for Java or Docstrings for Python) to generate API documentation automatically.
*   **User Manuals and Guides:**  Providing documentation for end-users on how to install, use, and troubleshoot the software.
*   **Technical Documentation:**  Detailed documentation for developers and system administrators, including design specifications, architecture diagrams, database schemas, and API documentation.  This is crucial for maintenance, upgrades, and future development.
*   **Version Control Documentation:** Using version control systems (like Git) and documenting changes made in each version, along with commit messages explaining the rationale behind changes.

Good documentation is vital during implementation and throughout the software lifecycle as it aids in understanding, maintaining, and evolving the software.

**Question 2**

**(a) Levels of Software Testing (12 marks)**

Software testing is performed at different levels to ensure different aspects of the software quality. Here are the levels of software testing:

**(i) Unit Testing:**

*   **Focus:**  Testing individual units or components of the software in isolation. A "unit" is typically the smallest testable part of an application, like a function, method, or module.
*   **Purpose:**  To verify that each unit functions correctly according to its specification.
*   **Who performs it:** Usually done by developers.
*   **Example:** Testing a function that calculates the square root to ensure it returns the correct result for various inputs.

**(ii) Integration Testing:**

*   **Focus:** Testing the interaction and interfaces between integrated units or components.
*   **Purpose:** To verify that units work together correctly when combined as per the design. It checks data flow and control flow between modules.
*   **Who performs it:** Testers, sometimes developers assist.
*   **Example:** Testing how the user login module interacts with the database module to ensure successful authentication.

**(iii) System Testing:**

*   **Focus:** Testing the entire system as a whole to verify that it meets the specified requirements.
*   **Purpose:** To evaluate the system's compliance with functional and non-functional requirements (performance, security, reliability, etc.).
*   **Who performs it:**  Independent testers, QA team.
*   **Example:** Testing the complete e-commerce website to ensure all features like browsing products, adding to cart, checkout, payment processing, etc., work as expected under normal and peak load conditions.

**(iv) Acceptance Testing:**

*   **Focus:**  Testing conducted to determine if the system meets the customer's needs and is ready for deployment or release.
*   **Purpose:** To gain confidence that the system is acceptable to the end-users or stakeholders.
*   **Who performs it:** End-users, customers, or stakeholders, often with testers facilitating.
*   **Types:**  User Acceptance Testing (UAT), Business Acceptance Testing (BAT), Alpha and Beta testing.
*   **Example:**  Having business users test the new banking application to ensure it meets their business processes and usability requirements before it's rolled out to customers.

**(v) Regression Testing:**

*   **Focus:** Re-testing previously tested parts of the software after changes (e.g., bug fixes, new features, modifications).
*   **Purpose:** To ensure that changes have not introduced new defects or re-introduced old ones and that existing functionality still works as expected.
*   **When performed:**  After any code modification.
*   **Who performs it:** Testers, often using automation tools.
*   **Example:** After fixing a bug in the payment module, regression testing would involve re-running tests for payment, user login, and other related functionalities to ensure the fix didn't break anything else.

**(b) White-Box Testing and its Techniques (8 marks)**

**White-Box Testing (also known as Glass-Box or Structural Testing):**

White-box testing is a testing approach where the internal structure, design, and code of the software are known to the tester. The tester uses this knowledge to design test cases that examine the program's logic and internal paths. The goal is to ensure that all internal operations are performed according to the specifications and that all internal code paths are exercised.

**Diagram (Illustrative):**

```
[Source Code] --> [White-Box Testing Techniques] --> [Test Cases] --> [Execution] --> [Results & Code Coverage Analysis]
```

**Techniques of White-Box Testing:**

1.  **Statement Coverage:**
    *   **Goal:** To ensure that every statement in the code is executed at least once during testing.
    *   **Metric:**  Percentage of statements executed.
    *   **Example:** If a function has 10 lines of code, statement coverage aims to execute all 10 lines with test cases.

2.  **Branch Coverage (Decision Coverage):**
    *   **Goal:** To ensure that every decision (branch) in the code is taken at least once, resulting in both true and false outcomes.
    *   **Metric:** Percentage of branches covered.
    *   **Example:** For an `if-else` statement, test cases should be designed to execute both the `if` block (true branch) and the `else` block (false branch).

3.  **Path Coverage:**
    *   **Goal:** To ensure that every possible execution path through the code is tested.
    *   **Metric:** Percentage of paths covered.
    *   **Complexity:** Path coverage is more comprehensive than statement and branch coverage but can be very complex and sometimes impossible to achieve for larger programs with many paths.
    *   **Example:** For nested `if` statements, path coverage would aim to test all combinations of true/false outcomes for each condition, covering all possible routes through the code.

4.  **Condition Coverage:**
    *   **Goal:** To test each logical condition in a decision to take on all possible outcomes at least once.
    *   **Metric:** Percentage of condition outcomes covered.
    *   **Example:** For a condition `(A AND B)`, test cases should cover scenarios where A is true and false, and B is true and false, irrespective of the overall decision outcome.

5.  **Control Flow Graph (CFG) Based Testing:**
    *   **Concept:** Representing the program's control flow as a graph. Nodes represent statements, and edges represent control flow paths.
    *   **Techniques:** Using CFG to design test cases to cover paths, branches, etc.

White-box testing is valuable for uncovering defects in the code logic, control flow, and data flow. It is often used in combination with black-box testing to provide a comprehensive test coverage.

**Question 3**

**(a) (i) Categories of Software Evolution according to Lehman (5 marks)**

Meir Lehman and Laszlo Belady proposed several laws regarding software evolution, often referred to as Lehman's Laws of Software Evolution. These laws describe the dynamics of software systems as they evolve. Briefly explained:

1.  **Continuing Change (Law of Continuing Change):** A software system that is used undergoes continuing change until it is judged more cost-effective to replace it with a re-engineered or new system.  Essentially, software must continuously adapt to remain useful.
2.  **Increasing Complexity (Law of Increasing Complexity):** As a software system evolves, its complexity increases unless active work is done to maintain or reduce it. Adding new features or fixing bugs without careful design and refactoring can lead to increased complexity.
3.  **Conservation of Organizational Stability (Law of Conservation of Organizational Stability):**  Over the lifetime of a system, the rate of development of a software product is approximately constant.  Large changes in one area tend to be compensated by reduced changes in other areas to maintain overall stability.
4.  **Conservation of Familiarity (Law of Conservation of Familiarity):** As a system evolves, all associated with it, developers, users, etc., must maintain mastery of its content and behavior to maintain satisfactory evolution.  Complexity growth limits understandability.
5.  **Feedback System (Law of Feedback System):** Software evolution processes are feedback systems. Changes must be managed and controlled based on feedback from users, developers, and the environment.
6.  **Continuing Growth (Law of Continuing Growth):** The functionality offered by systems has to continually increase to maintain user satisfaction over their lifetime.  Users become accustomed to existing features and expect more over time.

**(a) (ii) Describe the Software Development Process in Brief (6 marks)**

The software development process (also known as Software Development Life Cycle - SDLC) is a structured approach to planning, creating, testing, and deploying an information system.  It's a framework that defines the steps involved in developing software from initial concept to final product and maintenance. Briefly, the typical phases are:

1.  **Requirements Gathering/Analysis:**
    *   **Purpose:** To understand and document the needs of the users and stakeholders. What problem does the software need to solve? What features are needed?
    *   **Activities:** Eliciting requirements from clients, analyzing requirements, documenting them in a Software Requirements Specification (SRS).

2.  **Design:**
    *   **Purpose:** To plan the structure and architecture of the software system based on the requirements. How will the software be built?
    *   **Activities:** High-level design (system architecture, modules), low-level design (algorithms, data structures, interfaces), creating design documents.

3.  **Implementation (Coding):**
    *   **Purpose:** To translate the design into actual code. Writing the program code.
    *   **Activities:** Coding in the chosen programming language, following coding standards, unit testing individual modules.

4.  **Testing:**
    *   **Purpose:** To identify defects and ensure the software meets the requirements and quality standards.
    *   **Activities:** Various levels of testing (unit, integration, system, acceptance), bug reporting and fixing.

5.  **Deployment:**
    *   **Purpose:** To make the software available for users.
    *   **Activities:** Installation, configuration, system setup, user training, going live.

6.  **Maintenance:**
    *   **Purpose:** To keep the software running smoothly, fix bugs found after deployment, and adapt to new requirements or environments.
    *   **Activities:** Corrective maintenance (bug fixes), adaptive maintenance (adapting to new platforms), perfective maintenance (adding new features, improving performance), preventive maintenance (improving maintainability).

Different SDLC models (like Waterfall, Agile, Iterative, Spiral) organize these phases in different ways, but these core phases are generally present in any software development process.

**(b) Write short notes on the following Software Design Strategies (9 marks)**

**(i) Structured Design:**

*   **Concept:** A top-down design approach that focuses on breaking down a complex system into smaller, independent modules or functions. It emphasizes modularity and hierarchical organization.
*   **Focus:**  Data flow and functional decomposition.
*   **Techniques:**  Uses techniques like Structure Charts to represent the system hierarchy and data flow.  Emphasizes control flow and data flow between modules.
*   **Goal:** To create programs that are easier to understand, modify, and maintain.
*   **Suitable for:** Systems where functionality can be clearly decomposed into independent modules, often used in procedural programming.

**(ii) Function-Oriented Design:**

*   **Concept:**  Similar to structured design, it revolves around functions as the primary building blocks of the software. The system is decomposed into a set of interacting functions.
*   **Focus:**  Functions and algorithms.
*   **Approach:**  Identifies the main functions the system needs to perform and then designs sub-functions to achieve them. Data is often considered secondary to functions.
*   **Example:** Designing a payroll system by identifying functions like `calculate_salary`, `generate_pay_slip`, `deduct_taxes`, etc.
*   **Often used with:** Structured programming languages like C, Pascal.

**(iii) Object-Oriented Design (OOD):**

*   **Concept:**  Organizes software design around "objects," which encapsulate both data (attributes) and behavior (methods).
*   **Focus:**  Objects, classes, and their interactions.
*   **Principles:**  Emphasizes principles like encapsulation, inheritance, polymorphism, and abstraction.
*   **Approach:**  Identifies objects in the problem domain, defines their classes, attributes, and methods, and establishes relationships between objects.
*   **Advantages:** Promotes reusability, modularity, maintainability, and better modeling of real-world entities.
*   **Often used with:** Object-oriented programming languages like Java, C++, Python.
*   **Example:** Designing a library management system with objects like `Book`, `Member`, `Loan`, each having attributes and methods related to library operations.

**Question 4**

**(a) Software Analysis and Design Tools (9 marks)**

**(i) Data Flow Diagram (DFD):**

*   **Purpose:** A graphical tool used to represent the flow of data through a system. It visualizes how data moves between processes, data stores, and external entities.
*   **Components:**
    *   **Processes:** Activities that transform data (represented by circles or rounded rectangles).
    *   **Data Flows:**  Paths through which data moves (represented by arrows).
    *   **Data Stores:**  Places where data is stored (represented by open-ended rectangles or parallel lines).
    *   **External Entities (Sources/Sinks):** Entities outside the system that send data to or receive data from the system (represented by rectangles).
*   **Levels:** DFDs can be leveled to represent increasing levels of detail (Level 0 - Context Diagram, Level 1, Level 2, etc.).
*   **Use:**  Used during requirements analysis and design to understand and document data processing requirements.

**(ii) Structure Charts:**

*   **Purpose:** A hierarchical chart that shows the modular structure of a program. It depicts the organization and relationships between modules in a program.
*   **Components:**
    *   **Modules:**  Represented by rectangles.
    *   **Hierarchy:**  Modules are arranged in a tree-like structure, showing the calling relationships (which module calls which).
    *   **Data Flow:** Arrows with annotations can show data passed between modules (data couples, control couples).
    *   **Control Flow:**  Often implied by the hierarchical structure, showing the sequence of module calls.
*   **Use:** Used in structured design to represent the program's modular structure and control flow. Helps in understanding the program's organization and designing modular systems.

**(iii) HIPO Diagram (Hierarchy plus Input-Process-Output):**

*   **Purpose:**  A documentation technique to represent the functional decomposition of a system. It provides a hierarchical view of the system's functions and, for each function, describes its inputs, processes, and outputs.
*   **Components:**
    *   **Hierarchy Chart (H-Chart):**  Shows the hierarchical decomposition of functions.  Similar to a structure chart but focuses on functions.
    *   **IPO Charts:**  For each function in the hierarchy, an IPO chart describes:
        *   **Input:** Data required for the function.
        *   **Process:**  Steps performed by the function.
        *   **Output:** Data produced by the function.
*   **Use:** Used for documenting and understanding system functions, inputs, and outputs at different levels of detail. Useful for functional decomposition and documenting system functionality.

**(b) (i) Coupling (8 marks)**

**Coupling:**

Coupling is a measure of the degree of interdependence between modules or components in a software system. It indicates how strongly connected modules are to each other. Low coupling is desirable, meaning modules are relatively independent, while high coupling means modules are strongly dependent.

**Levels of Coupling (from lowest/best to highest/worst):**

1.  **Data Coupling:**
    *   **Description:** Modules are dependent on each other only through data passed as parameters. Modules share data through parameters only.
    *   **Type of Data:** Simple data items (not data structures).
    *   **Example:** A function calculating the area of a rectangle taking length and width as parameters.
    *   **Lowest Coupling, Best type.**

2.  **Stamp Coupling (Control Coupling in some classifications):**
    *   **Description:** Modules are coupled because they pass structured data (data structures, records, objects) as parameters, and the called module uses only parts of the structure.
    *   **Example:** Passing a customer record to a function, but the function only uses the customer's ID and address.
    *   **Moderate Coupling.**

3.  **Control Coupling:**
    *   **Description:** One module controls the flow of another module by passing control information (flags, control signals) as parameters. One module tells another *what* to do and *how* to do it.
    *   **Example:** A function passing a flag to another function to indicate which operation to perform (e.g., sort in ascending or descending order).
    *   **Higher Coupling than Data or Stamp.**

4.  **External Coupling:**
    *   **Description:** Modules are coupled because they depend on the same externally imposed data format, protocol, or interface.
    *   **Example:** Two modules interacting with the same external database or communicating via a shared network protocol.
    *   **Significant Coupling, can be hard to change external factors.**

5.  **Common Coupling (Global Coupling):**
    *   **Description:** Modules are coupled because they access and modify the same global data (global variables, shared data areas).
    *   **Example:** Multiple modules directly reading and writing to the same global variable.
    *   **High Coupling, makes changes difficult and error-prone.**

6.  **Content Coupling (Pathological Coupling):**
    *   **Description:** One module directly accesses or modifies the internal data or control flow of another module.  One module directly modifies the code of another.
    *   **Example:** One module jumping into the middle of another module's function, or directly modifying another module's local variables.
    *   **Highest Coupling, Worst type, should be avoided.**

**(b) (ii) State the three Software Design Levels used in software engineering (3 marks)**

The three main levels of software design are:

1.  **Architectural Design (System Design):**
    *   **Focus:**  Defines the overall structure of the system. It identifies the major components (subsystems, modules), their responsibilities, and how they interact.
    *   **Outputs:** System architecture diagrams, component diagrams, deployment diagrams, high-level design document.
    *   **Example:** Deciding to use a three-tier architecture (presentation, application, data tier) for a web application and defining the components within each tier.

2.  **High-Level Design (Modular Design):**
    *   **Focus:**  Breaks down the system into modules and defines the interfaces between these modules.  It specifies what each module does and how modules interact with each other.
    *   **Outputs:** Module specifications, interface definitions, data flow between modules, detailed structure charts.
    *   **Example:**  Designing the modules within the application tier of the web application, like user management, product catalog, order processing modules, and defining the APIs they will use to communicate.

3.  **Detailed Design (Component-Level Design or Program Design):**
    *   **Focus:**  Refines the high-level design to a level of detail where implementation (coding) can begin. It specifies the internal logic, data structures, and algorithms for each module.
    *   **Outputs:**  Algorithm specifications, data structure definitions, class diagrams (in OOP), pseudocode, detailed module design document.
    *   **Example:** Designing the algorithm for the order processing module, defining the data structures to store order information, and specifying the logic for payment processing, inventory updates, etc.

These levels provide a progression from the broad system structure to the fine details required for coding.

**Question 5**

**(a) Software Requirements and Concepts of Requirement Engineering (8 marks)**

**Software Requirements:**

Software requirements are descriptions of the services that a software system is expected to provide and the constraints under which it must operate. They are essentially statements of what the system should do. Requirements can be functional (describing what the system should do) or non-functional (describing how well it should do it, e.g., performance, security, usability).

**Requirement Engineering:**

Requirement Engineering (RE) is the process of defining, documenting, and maintaining requirements in the software development lifecycle. It is a critical phase because errors in requirements can lead to significant problems later in development. RE encompasses all the activities related to discovering, analyzing, specifying, validating, and managing requirements.

**Concepts of Requirement Engineering:**

**(i) Requirement Engineering Process:** Typically involves these main steps:

1.  **Elicitation (Requirements Gathering):** Discovering requirements from stakeholders, users, documentation, existing systems, etc. Techniques include interviews, questionnaires, workshops, brainstorming, prototyping.
2.  **Analysis and Negotiation:** Understanding, refining, and structuring the elicited requirements. Resolving conflicts, inconsistencies, and ambiguities. Prioritizing requirements.
3.  **Specification:** Documenting the requirements clearly, precisely, and comprehensively in a Software Requirements Specification (SRS) document. Using models, diagrams, and formal notations where appropriate.
4.  **Validation:** Checking that the requirements are correct, complete, consistent, and unambiguous and that they truly reflect the needs of the stakeholders. Techniques include reviews, prototypes, test case generation.
5.  **Management:** Controlling changes to requirements throughout the project lifecycle. Establishing a baseline, managing versions, tracking changes, and ensuring traceability.

**(ii) Requirement Elicitation Process:**

Requirement elicitation is the process of discovering, acquiring, and understanding the requirements of a system from stakeholders and other sources. It's the first step in requirement engineering and crucial for getting a clear picture of what the software needs to do. Key activities and techniques include:

1.  **Identify Stakeholders:** Determine who are the users, customers, domain experts, and other relevant parties who have a stake in the system and can provide requirements.
2.  **Choose Elicitation Techniques:** Select appropriate techniques based on project context, stakeholder availability, and type of information needed. Common techniques:
    *   **Interviews:** One-on-one or group interviews with stakeholders to gather requirements.
    *   **Questionnaires:** Distributing questionnaires to a larger group to collect information.
    *   **Workshops/JAD Sessions:** Facilitated group meetings to brainstorm and collaboratively define requirements.
    *   **Brainstorming:**  Generating ideas and requirements freely in a group setting.
    *   **Document Analysis:** Reviewing existing documents, system documentation, business plans, etc., to extract requirements.
    *   **Prototyping:** Developing early prototypes to show stakeholders and get feedback, clarifying requirements through interaction.
    *   **Observation:** Observing users in their work environment to understand their tasks and needs.
    *   **Use Cases:** Developing use cases to describe interactions between users and the system to achieve specific goals.
    *   **User Stories:**  Short, simple descriptions of a feature from the user's perspective.

3.  **Conduct Elicitation Sessions:**  Carry out the chosen techniques to gather requirements from stakeholders.
4.  **Document Initial Requirements:** Record the gathered requirements in a preliminary format (notes, lists, initial documents).
5.  **Confirm and Refine:** Review the elicited requirements with stakeholders for accuracy, completeness, and clarity. Refine and iterate as needed.

Effective requirement elicitation is essential for building software that truly meets user needs and business goals.

**(b) Project Management Tools (Diagrams) (12 marks)**

**(i) Gantt Chart:**

*   **Diagram Type:** Bar chart.
*   **Purpose:** To visually represent the project schedule, showing tasks, their durations, start and end dates, and dependencies.
*   **Elements:**
    *   **Tasks:** Listed on the vertical axis.
    *   **Time scale:** Horizontal axis (days, weeks, months).
    *   **Bars:** Represent the duration of each task, extending from start to end date.
    *   **Dependencies:** Can be shown with arrows connecting dependent tasks.
*   **Usefulness:**
    *   **Planning and Scheduling:** Helps in planning project timelines, allocating resources, and setting realistic deadlines.
    *   **Progress Tracking:**  Visualizes project progress by showing completed vs. planned tasks.
    *   **Communication:**  Easy-to-understand visual representation of the project schedule for stakeholders.
*   **Diagram Example:** A bar chart with tasks listed on the left (e.g., "Requirements Gathering", "Design", "Coding", "Testing"), and bars extending across a timeline at the top, indicating duration and start/end dates for each task.

**(ii) PERT Chart (Program Evaluation and Review Technique):**

*   **Diagram Type:** Network diagram (nodes and arrows).
*   **Purpose:** To represent project tasks and their dependencies, especially useful for projects with uncertain task durations.
*   **Elements:**
    *   **Nodes (Events):** Represent milestones or significant points in the project.
    *   **Arrows (Activities):** Represent tasks or activities, labeled with task name and estimated duration.
    *   **Paths:** Sequences of connected tasks from project start to end.
    *   **Critical Path:** The longest path in the network, determining the minimum project completion time.
*   **Time Estimates:** PERT uses three time estimates for each activity: optimistic (shortest), pessimistic (longest), and most likely time.
*   **Usefulness:**
    *   **Dependency Analysis:** Clearly shows task dependencies and sequences.
    *   **Critical Path Identification:**  Highlights critical tasks that must be completed on time to avoid project delays.
    *   **Risk Assessment:**  Accounts for uncertainty in task durations using probabilistic time estimates.
*   **Diagram Example:** A network of circles (nodes) connected by arrows (tasks), with tasks labeled with names and time estimates. The critical path is often highlighted differently.

**(iii) Resource Histogram:**

*   **Diagram Type:** Bar chart or line graph.
*   **Purpose:** To visualize the amount of resources (e.g., person-hours, equipment, budget) required over time during a project.
*   **Elements:**
    *   **Time scale:** Horizontal axis (days, weeks, months).
    *   **Resource units:** Vertical axis (e.g., person-hours, cost).
    *   **Bars or Line:**  Represent the amount of resource needed for each time period.
*   **Usefulness:**
    *   **Resource Planning and Allocation:** Helps in planning resource needs over the project lifecycle.
    *   **Resource Leveling:**  Identifies periods of resource over-allocation or under-allocation, allowing for resource leveling (smoothing resource usage).
    *   **Budgeting:**  Visualizes cost distribution over time.
*   **Diagram Example:** A bar chart with time periods on the x-axis and resource units (e.g., person-hours) on the y-axis. Bars show the total person-hours needed for each week/month of the project.

**(iv) Critical Path Analysis (CPA):**

*   **Technique:**  Not just a diagram, but a technique using network diagrams (often PERT or similar) to determine the critical path and project duration.
*   **Purpose:** To identify the sequence of critical tasks that directly impact the project completion date and to calculate the earliest and latest start and finish times for each task.
*   **Process:**
    1.  **Construct Network Diagram:** (PERT or Activity-on-Node).
    2.  **Estimate Task Durations:**.
    3.  **Forward Pass:** Calculate earliest start (ES) and earliest finish (EF) times for each task.
    4.  **Backward Pass:** Calculate latest start (LS) and latest finish (LF) times for each task.
    5.  **Calculate Slack/Float:**  (LF - EF or LS - ES). Tasks with zero slack are on the critical path.
    6.  **Identify Critical Path:** The path through the network with zero slack for all tasks.
*   **Usefulness:**
    *   **Project Scheduling:** Determines realistic project duration.
    *   **Critical Task Management:** Focuses project management efforts on critical tasks to prevent delays.
    *   **Time Buffering:**  Identifies how much delay can be tolerated for non-critical tasks without affecting project completion.
*   **Diagram Example:** Often uses a PERT chart or Activity-on-Node diagram, with calculations of ES, EF, LS, LF, and slack values for each task. The critical path is highlighted, showing the sequence of tasks that must be on schedule.

**Question 6**

**(a) (i) Outline any three types of feasibility study (5 marks)**

Feasibility study is an assessment of the practicality and viability of a proposed project or system. It's conducted before significant resources are committed to development to determine if the project is worth pursuing. Three common types are:

1.  **Technical Feasibility:**
    *   **Focus:**  Assesses whether the proposed system can be developed and implemented using existing technology and resources.
    *   **Questions:**
        *   Is the required technology available and mature enough?
        *   Does the team have the necessary technical expertise?
        *   Can the system be integrated with existing systems?
        *   Is the technology scalable to meet future needs?
        *   Are there any technical risks or challenges that could hinder development?
    *   **Outcome:** Determines if the technical aspects of the project are realistic and achievable within the given constraints.

2.  **Economic Feasibility (Cost-Benefit Analysis):**
    *   **Focus:** Evaluates the financial viability of the project. It compares the estimated costs of development and operation with the expected benefits.
    *   **Questions:**
        *   What are the estimated development costs (hardware, software, personnel, etc.)?
        *   What are the ongoing operational costs (maintenance, support, etc.)?
        *   What are the potential benefits (increased revenue, cost savings, improved efficiency, etc.)?
        *   Will the benefits outweigh the costs?  What is the Return on Investment (ROI)?
        *   What is the payback period?
    *   **Outcome:** Determines if the project is financially sound and will provide a positive return on investment.

3.  **Operational Feasibility:**
    *   **Focus:**  Assesses how well the proposed system will solve the identified problems and meet the needs of the users and the organization. It examines the operational aspects of the system.
    *   **Questions:**
        *   Will the system be easy to use and operate by end-users?
        *   Will it fit into the existing organizational workflow and business processes?
        *   Will it improve efficiency and effectiveness?
        *   Is it compatible with the organization's culture and environment?
        *   Will it be accepted and supported by users and stakeholders?
    *   **Outcome:**  Determines if the system will be operationally effective and beneficial to the organization in practice.

**(a) (ii) What are the contents of a feasibility report in software development? (5 marks)**

A feasibility report documents the findings of a feasibility study. It typically includes the following contents:

1.  **Executive Summary:**
    *   A brief overview of the feasibility study, its purpose, key findings, and recommendations.  Should be concise and understandable for decision-makers.

2.  **Introduction:**
    *   Background of the project proposal, the problem or opportunity being addressed, and the objectives of the feasibility study.

3.  **Project Description:**
    *   Detailed description of the proposed software system, its features, functionalities, and scope.

4.  **Technical Feasibility Assessment:**
    *   Analysis of the technical feasibility, including:
        *   Technology availability and maturity.
        *   Technical expertise required and available.
        *   System integration aspects.
        *   Scalability considerations.
        *   Technical risks and challenges.
        *   Conclusion on technical feasibility.

5.  **Economic Feasibility Assessment:**
    *   Cost-benefit analysis, including:
        *   Estimated development costs (breakdown).
        *   Estimated operational costs.
        *   Expected benefits (tangible and intangible).
        *   Return on Investment (ROI) calculation.
        *   Payback period.
        *   Conclusion on economic feasibility.

6.  **Operational Feasibility Assessment:**
    *   Evaluation of operational aspects, including:
        *   User friendliness and ease of operation.
        *   Compatibility with existing workflows and processes.
        *   Impact on organizational efficiency and effectiveness.
        *   User and stakeholder acceptance.
        *   Organizational culture fit.
        *   Conclusion on operational feasibility.

7.  **Schedule Feasibility (Optional, or could be part of Technical):**
    *   Assessment of whether the project can be completed within a reasonable timeframe.
    *   Estimated project timeline, key milestones, and deadlines.

8.  **Legal and Ethical Feasibility (Optional):**
    *   Consideration of legal and ethical aspects related to the project (data privacy, compliance, etc.).

9.  **Alternatives Considered (Optional):**
    *   Briefly discuss any alternative solutions or approaches that were considered and why the proposed solution was chosen.

10. **Recommendations and Conclusion:**
    *   Overall conclusion based on the feasibility assessments.
    *   Clear recommendations on whether to proceed with the project, proceed with modifications, or abandon the project.
    *   Next steps if the project is recommended to proceed.

11. **Appendices (Optional):**
    *   Supporting documents, detailed cost breakdowns, data sources, stakeholder interviews, etc.

**(b) (i) Briefly explain the concepts of software evolution as applicable in developing a software product (5 marks)**

Software evolution is the process of change and development of a software system over time. It's not a one-time development but a continuous process of adaptation, improvement, and maintenance throughout the software's lifespan. Concepts of software evolution are highly relevant in developing a software product because:

1.  **Software is rarely finished:**  Once software is deployed, it's not static. User needs change, business requirements evolve, technology advances, and bugs are discovered. Software must evolve to remain useful and relevant.
2.  **Types of Evolution:** Software evolves through different types of maintenance:
    *   **Corrective Maintenance:** Fixing defects and bugs discovered after deployment.
    *   **Adaptive Maintenance:** Modifying software to adapt to new environments (e.g., new operating systems, databases, hardware).
    *   **Perfective Maintenance:** Adding new features, improving performance, enhancing usability, and meeting new user requirements.
    *   **Preventive Maintenance:**  Restructuring and re-documenting software to improve maintainability and prevent future problems.
3.  **Lehman's Laws of Software Evolution:** These laws (as discussed in Question 3a(i)) highlight the inherent nature of software to change, grow in complexity, and require ongoing effort to maintain. Understanding these laws is crucial for managing software evolution effectively.
4.  **Evolutionary Development Models:**  Agile and iterative development models explicitly embrace evolution. They build software incrementally, with frequent feedback and adaptation, allowing for changes in requirements and design throughout the development process. This is in contrast to waterfall models that assume requirements are fixed upfront.
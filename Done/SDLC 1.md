**SET 1:  CSC 339 - SYSTEMS ANALYSIS AND DESIGN**

**Question 1**

**a. List 5 characteristics of a system.** (5 marks)

*   **Components:** Systems are made up of interacting parts or subsystems.
*   **Interrelationships:** These components are linked and interact with each other.
*   **Boundary:**  A system has a defined boundary that separates it from its environment.
*   **Purpose/Objective:** Systems are designed to achieve a specific goal or set of goals.
*   **Environment:**  Systems exist within an environment and interact with it (receiving inputs and producing outputs).

**b. Explain any 3 of the characteristics of the system.** (6 marks)

*   **Components:**  Every system is composed of different parts that work together. For example, in a university system, components include students, lecturers, departments, administration, and facilities. Each component has its role, but they must interact to achieve the university's goals.
*   **Interrelationships:** The components of a system are not isolated; they are interconnected and depend on each other.  In a library system, the catalog system is related to the borrowing system, which is related to the acquisitions system. Changes in one can affect others.
*   **Boundary:**  A system has a boundary that defines what is inside and outside of it. This boundary can be physical or conceptual. For example, the boundary of a hospital system might include all departments within the hospital building, but exclude external clinics, even though they might be related.  Boundaries help define the scope of the system.

**c. Draw a model to represent a system with its elements that can keep the system in equilibrium.** (5 marks)

You should draw a **Feedback Loop Diagram**.  Here's a description of what to include:

*   **System Core (Process):**  In the center, represent the main activities or processes of the system (e.g., "Production Process," "Information Processing," "Service Delivery").
*   **Input:**  An arrow pointing into the System Core labeled "Input" (e.g., "Raw Materials," "Data," "Customer Requests").
*   **Output:** An arrow pointing out of the System Core labeled "Output" (e.g., "Finished Goods," "Reports," "Service Provided").
*   **Feedback Loop:** An arrow going from the "Output" back to the "Input" (or to a control mechanism influencing the Input or Process). Label this "Feedback."
*   **Control Mechanism (Optional but good):** You can add a box somewhere in the loop labeled "Control/Regulation" or "Management." This mechanism analyzes the feedback and makes adjustments to the input or process to maintain equilibrium.
*   **Environment:**  Draw a box encompassing the whole diagram labeled "Environment."

**Explanation of Equilibrium:** The feedback loop is crucial for equilibrium.  The system monitors its output and uses feedback to adjust its input or internal processes. This self-regulation helps the system maintain a stable state and adapt to changes in the environment.  Think of a thermostat in a heating system - it's a feedback mechanism that keeps the temperature at a set point (equilibrium).

**d. In the pyramid representing levels of management in organization, DSS and MIS are essentially for which level of management? Explain these two types of system at that management level.** (5 marks)

*   **MIS (Management Information Systems):** Primarily for **Tactical Level Management** (Middle Management).  MIS provides structured reports, summaries, and exceptions to help middle managers monitor performance, make operational decisions, and control activities.
*   **DSS (Decision Support Systems):** Primarily for **Strategic Level Management** (Top Management) and sometimes **Tactical Level**. DSS are interactive systems that help managers make semi-structured and unstructured decisions. They provide analytical tools, simulations, and access to data to explore different scenarios and support complex decision-making.

**Explanation:**

*   **Tactical Level (Middle Management):**  Focuses on implementing the strategic goals. They need information to monitor departmental performance, allocate resources, and make short-to-medium term decisions. MIS provides routine and summary reports for this purpose.
*   **Strategic Level (Top Management):** Focuses on long-term planning, setting organizational goals, and making strategic decisions that impact the entire organization. These decisions are often complex and less structured. DSS helps them analyze complex data, explore different strategic options, and make informed judgments.

**e. Group the following into internal and external environment:** (4 marks)

**Internal Environment:**

1.  **Customer**  (While customers interact, they are often considered part of the *task environment* which is closely linked to the internal operations and goals of the organization) - *This can be argued as both internal and external depending on the context, but for this grouping in a typical business context, it's often considered part of the task/internal environment influence.*
2.  **Company Management**
3.  **Employees of different departments**
4.  **Consultancy services** (If these are *internal* consultants, then internal. If *external* consultants hired, then external - *Assuming internal here as it fits better with the rest of the internal list*)
5.  **Internal auditors**
6.  **Financial services** (If referring to *internal* finance department, then internal. If *external* financial institutions, then external - *Assuming internal finance department here*)

**External Environment:**

7.  **External auditors**
8.  **Government policies**

**Question 2**

**a. What is requirement analysis? State the three activities that could be performed to achieve requirement analysis.** (4 marks)

*   **Requirement Analysis:** The process of discovering, documenting, and validating the needs and conditions that a new system or system change must meet. It's about understanding what the stakeholders want and need from the system.

*   **Three Activities:**
    1.  **Elicitation (Gathering Requirements):**  Collecting requirements from stakeholders using techniques like interviews, questionnaires, workshops, document review, and observation.
    2.  **Analysis and Modeling:**  Organizing, structuring, and modeling the gathered requirements. This involves creating diagrams (like use case diagrams, data flow diagrams), defining data dictionaries, and ensuring requirements are consistent and complete.
    3.  **Validation and Verification:** Checking that the documented requirements are correct, complete, unambiguous, and achievable. This involves reviewing requirements with stakeholders, prototyping, and conducting walkthroughs.

**b. Explain the activities mentioned above in details.** (9 marks)

*   **Elicitation (Detailed Explanation):** This is the crucial first step. It involves actively seeking out and collecting requirements from all relevant stakeholders (users, managers, customers, domain experts, etc.).  Different techniques are used depending on the context:
    *   **Interviews:**  One-on-one or group discussions to understand needs, problems, and expectations.
    *   **Questionnaires:**  Surveys to gather information from a larger group of stakeholders, often for quantifiable data or broad opinions.
    *   **Workshops/Joint Application Development (JAD) sessions:** Facilitated group meetings where stakeholders collaboratively define requirements and resolve conflicts.
    *   **Document Review:** Examining existing documents (like business plans, system manuals, reports) to understand current processes and identify needs.
    *   **Observation:**  Watching users perform their tasks to understand their workflow and identify areas for improvement.

*   **Analysis and Modeling (Detailed Explanation):**  Once requirements are gathered, they are often disorganized and may be conflicting. Analysis and modeling help to:
    *   **Organize:** Group related requirements, categorize them (functional, non-functional, data, etc.).
    *   **Structure:** Create a logical flow and hierarchy of requirements.
    *   **Model:** Represent requirements visually using diagrams (Use Case Diagrams for functionality, ER Diagrams for data, DFDs for processes). Models help to understand complexity, identify gaps, and communicate requirements clearly.
    *   **Resolve Conflicts:** Identify and resolve inconsistencies or conflicting requirements from different stakeholders.
    *   **Define Data:** Create data dictionaries to define data elements, their types, and relationships.

*   **Validation and Verification (Detailed Explanation):**  This step ensures the quality of the requirements.
    *   **Validation:**  Are we building the *right* system?  Does the requirements document accurately reflect what the stakeholders *need*?  Techniques include:
        *   **Stakeholder Reviews:**  Presenting the requirements document to stakeholders for their feedback and approval.
        *   **Prototyping:**  Developing a working model of parts of the system to demonstrate functionality and get user feedback on requirements.
        *   **Use Case Scenarios:**  Creating detailed scenarios of how users will interact with the system to validate that requirements are complete and realistic.
    *   **Verification:** Are we building the system *right*? Are the requirements stated clearly, consistently, and unambiguously?  Techniques include:
        *   **Requirements Walkthroughs/Inspections:**  Formal reviews by a team to identify errors, ambiguities, and omissions in the requirements document.
        *   **Checklists:** Using predefined checklists to ensure requirements meet quality criteria (e.g., testability, feasibility).

**c. Mention four (4) advantages of system analysis.** (2 marks)

*   **Improved Understanding of the System:**  System analysis provides a deep understanding of the current system, its problems, and opportunities for improvement.
*   **Clearer Requirements:**  It helps to define clear, concise, and unambiguous requirements for a new or improved system, reducing misunderstandings and rework later in the development process.
*   **Better Decision Making:**  By analyzing information and identifying alternatives, system analysis supports better-informed decisions about system design and implementation.
*   **Reduced Development Costs and Risks:**  Early identification of problems and clear requirements reduce the risk of costly errors, delays, and scope creep during development.
*   **Improved System Efficiency and Effectiveness:** By optimizing processes and addressing user needs, system analysis can lead to more efficient and effective systems. (Choose any 4).

**Question 3**

**a. Who is a system analyst?** (3 marks)

*   A **System Analyst** is a professional who analyzes, designs, and implements information systems. They act as a bridge between business users and technical teams. They understand business problems and opportunities and translate them into system requirements and design specifications that developers can use to build solutions.  They are problem solvers who use technology to improve organizational effectiveness.

**b. Mention 5 multifaceted roles of a system analyst and explain three out of them.** (8 marks)

**Five Multifaceted Roles:**

1.  **Investigator:**  The analyst investigates problems, opportunities, and user needs. They gather data, analyze existing systems, and understand the business context.
2.  **Architect:** The analyst designs the overall structure and components of the new system. They create blueprints for the system, defining its architecture, interfaces, and data flows.
3.  **Designer:** The analyst details the specific features and functionalities of the system. They design user interfaces, database structures, and process logic.
4.  **Catalyst:**  The analyst acts as a change agent, driving the system development project forward and facilitating communication and collaboration among stakeholders.
5.  **Consultant:** The analyst provides expert advice and guidance to the organization on system-related matters, recommending solutions and best practices.
6.  **Problem Solver:** The core role is to identify and solve business problems using information systems.

**Explain Three Roles:**

*   **Investigator:**  As an investigator, the system analyst uses various techniques like interviews, surveys, and document analysis to understand the current situation. They are like detectives, digging into the details to uncover the root causes of problems and identify areas where a new system can add value.  For example, when a company is experiencing slow order processing, the analyst investigates the current process, identifies bottlenecks, and understands user needs.
*   **Architect:** In the role of architect, the system analyst is responsible for the high-level design of the system. They decide on the major components, how they will interact, and the overall system structure.  They consider factors like scalability, security, and maintainability.  It's like designing the blueprint of a building before construction starts. For instance, deciding whether a system should be client-server, web-based, or cloud-based is part of the architect role.
*   **Catalyst:** As a catalyst, the system analyst is a driver of change.  They motivate stakeholders, facilitate communication between users and developers, and ensure the project moves forward smoothly. They help to overcome resistance to change and build consensus.  For example, they might organize meetings, workshops, and presentations to keep everyone informed and engaged in the system development process.

**c. Differentiate between desk research and brainstorming techniques of fact findings.** (4 marks)

*   **Desk Research:**
    *   **Definition:**  A fact-finding technique that involves reviewing existing documentation, reports, manuals, websites, and other readily available information. It's done primarily at a desk, hence the name.
    *   **Purpose:** To gather background information, understand existing systems, identify relevant data, and gain a general overview of the situation.
    *   **Interaction:** Minimal direct interaction with stakeholders.
    *   **Examples:** Reviewing company reports, studying competitor websites, reading industry publications, analyzing existing system documentation.

*   **Brainstorming:**
    *   **Definition:** A group fact-finding technique where participants collaboratively generate a wide range of ideas and potential solutions related to a specific problem or topic.
    *   **Purpose:** To stimulate creative thinking, uncover new ideas, identify potential requirements, and explore different perspectives.
    *   **Interaction:** Highly interactive, involving group discussion and idea sharing.
    *   **Examples:**  Gathering a team to brainstorm features for a new mobile app, generating ideas for improving customer service, identifying potential risks in a project.

**Key Differences Summarized:**

| Feature          | Desk Research                     | Brainstorming                        |
|-------------------|------------------------------------|--------------------------------------|
| **Data Source**    | Existing documents, records      | Group ideas, collective knowledge     |
| **Interaction**  | Minimal stakeholder interaction   | High stakeholder interaction         |
| **Purpose**        | Background info, overview         | Idea generation, creative solutions |
| **Approach**       | Individual, analytical            | Group, collaborative, generative     |

**Question 4**

**a. With the aid of diagrams differentiate between Spiral and Waterfall models of system development.** (10 marks)

You need to draw diagrams for both Waterfall and Spiral models and then explain the key differences.

**Waterfall Model Diagram:**

*   Draw a series of descending steps, like a waterfall. Each step flows into the next.
*   Label the steps in order:
    1.  **Requirements Analysis**
    2.  **System Design**
    3.  **Implementation**
    4.  **Testing**
    5.  **Deployment**
    6.  **Maintenance**
*   Show arrows flowing linearly downwards from one step to the next.  Ideally, show *no* arrows going backward significantly (or very minimal feedback arrows).

**Spiral Model Diagram:**

*   Draw a spiral, starting from the center and expanding outwards in loops.
*   Each loop represents a phase of development.  Divide each loop into four quadrants (or sections):
    1.  **Planning:** (Risk Analysis, Project Planning)
    2.  **Risk Analysis:** (Identify, Assess, Resolve Risks)
    3.  **Engineering (Implementation):** (Design, Develop, Test)
    4.  **Customer Evaluation:** (Evaluate, Feedback, Plan Next Phase)
*   Show the spiral progressing outwards through multiple loops, indicating iterative development.  Label each loop as an "Iteration" or "Phase."

**Diagrammatic Differences (Visually):**

*   **Waterfall:** Linear, sequential, downward flow. Emphasizes phases as distinct and completed one after another.
*   **Spiral:** Iterative, cyclical, expanding outwards. Emphasizes cycles of development, risk management, and refinement.

**Explanations and Key Differences:**

*   **Waterfall:**
    *   **Sequential:** Phases are completed in a strict sequence. You move to the next phase only after the current one is finished.
    *   **Rigid:**  Difficult to go back to previous phases once completed. Changes are expensive and disruptive.
    *   **Suitable for:** Projects with well-defined, stable requirements, low risk, and where changes are unlikely.
    *   **Emphasis:**  Planning and thorough documentation upfront.

*   **Spiral:**
    *   **Iterative and Incremental:**  Development occurs in cycles (iterations). Each iteration builds upon the previous one, adding more features and refining the system.
    *   **Risk-Driven:**  Risk analysis is a central part of each iteration. Risks are identified, assessed, and mitigated in each cycle.
    *   **Flexible:**  Allows for changes and evolving requirements throughout the development process. Feedback from each iteration is incorporated into the next.
    *   **Suitable for:** Complex, large projects with high risk, unclear or evolving requirements, and where flexibility is important.
    *   **Emphasis:** Risk management, iterative development, and customer feedback.

**b. List five benefits of prototyping model of system development.** (5 marks)

*   **Improved User Involvement:** Prototypes allow users to interact with a working model early on, leading to better understanding and feedback, and greater user satisfaction.
*   **Early Error Detection:**  Mistakes and misunderstandings in requirements and design are identified early in the prototyping phase, reducing costly rework later.
*   **Refined Requirements:** User feedback on prototypes helps to clarify and refine requirements, ensuring the final system meets actual needs.
*   **Reduced Development Time (Potentially):**  While prototyping itself takes time, it can reduce overall development time by preventing major rework caused by late-discovered errors. (However, sometimes it can increase time if not managed well).
*   **Improved System Usability:**  User feedback during prototyping helps to ensure the system is user-friendly and meets usability expectations.
*   **Better Understanding of Feasibility:** Prototyping can help assess the technical and economic feasibility of certain design choices early on. (Choose any 5).

**Question 5**

**a. Use appropriate ER symbols to draw a typical:** (10 marks)

*   **i. One to Many Relationship:**

    *   **Entities:** Draw two rectangles, label them "Customer" and "Order."
    *   **Relationship:** Draw a diamond shape between them, label it something like "Places" or "Creates."
    *   **Cardinality (One-to-Many):**
        *   On the "Customer" side of the relationship line, use the symbol for "one" (often just a single line or a "1").
        *   On the "Order" side of the relationship line, use the symbol for "many" (often a "crow's foot" - three lines diverging like a crow's foot, or symbols like "N" or "*").
    *   **Connect:** Draw lines connecting the entities to the relationship diamond.
    *   **Label Attributes (Optional but good):** Briefly list a couple of attributes inside each entity rectangle (e.g., Customer: CustomerID, Name; Order: OrderID, OrderDate).

*   **ii. Many to Many Relationship:**

    *   **Entities:** Draw two rectangles, label them "Student" and "Course."
    *   **Relationship:** Draw a diamond shape between them, label it something like "Registers for" or "Enrolls in."
    *   **Cardinality (Many-to-Many):**
        *   On the "Student" side of the relationship line, use the symbol for "many" (crow's foot, "N", "*").
        *   On the "Course" side of the relationship line, use the symbol for "many" (crow's foot, "N", "*").
    *   **Connect:** Draw lines connecting the entities to the relationship diamond.
    *   **Label Attributes (Optional but good):** Briefly list attributes (e.g., Student: StudentID, Name; Course: CourseCode, CourseTitle).

**b. List 5 rules for constructing Data Flow Diagrams (DFD).** (5 marks)

1.  **Process Naming:**  Processes should be named with a verb-noun phrase that describes the activity (e.g., "Validate Order," "Generate Report").
2.  **Data Flow Naming:** Data flows should be named with a noun phrase that describes the data moving in the flow (e.g., "Customer Order," "Sales Report").
3.  **External Entities/Terminators:**  External entities should be placed on the edges of the DFD to indicate they are outside the system boundary.
4.  **Data Stores:** Data stores should represent a store of data at rest (e.g., files, databases). They are typically nouns (e.g., "Customer File," "Order Database").
5.  **Process Numbering/Labeling:** Processes are typically numbered hierarchically to show levels of decomposition (e.g., 1.0, 1.1, 1.2, 2.0 etc.).
6.  **Conservation of Data:** Data entering a process must be sufficient to produce the output data (or explain where the data is transformed or added).
7.  **Avoid Data Miracles (Black Holes/Magic):**  Processes should not produce output data without sufficient input data. Similarly, processes should not consume input data without producing any output (unless it's a sink for data, which should be explicitly shown and justified).
8.  **Hierarchical Decomposition (Leveling):** DFDs should be leveled to manage complexity. Start with a context diagram (Level 0) showing the system as one process, then decompose processes into more detailed diagrams (Level 1, Level 2, etc.). (Choose any 5)

**Question 6**

**a. List 5 types of output.** (5 marks)

1.  **Detailed Reports:**  Comprehensive reports containing detailed information, often for internal use (e.g., sales transaction reports, inventory reports).
2.  **Summary Reports:**  Concise reports that summarize key data, often for management overview (e.g., monthly sales summary, budget performance report).
3.  **Exception Reports:** Reports that highlight unusual or exceptional situations that require attention (e.g., overdue invoices, low stock alerts).
4.  **Graphical Reports (Charts/Graphs):** Visual representations of data to make trends and patterns easier to understand (e.g., bar charts, line graphs, pie charts).
5.  **Turnaround Documents:** Documents that are sent to customers or external parties and then returned with updated information (e.g., invoices with payment stubs).
6.  **Promotional Materials:** Output designed to market products or services (e.g., brochures, flyers, website content).
7.  **Operational Documents:** Documents needed for daily operations (e.g., purchase orders, invoices, shipping labels).
8.  **Internal Communications:**  Memos, emails, and other forms of communication within the organization generated by the system. (Choose any 5).

**b. Briefly explain two validation checks.** (4 marks)

*   **Range Check:**  Ensures that numeric data entered falls within a specified acceptable range.  For example, in a student grading system, a range check would ensure that grades are between 0 and 100.  If a user tries to enter a grade of 150, the system would reject it as invalid.
*   **Type Check:**  Verifies that the data entered is of the correct data type. For example, if a field is defined as "numeric," a type check would ensure that only numbers are entered, and not letters or special characters.  If a user tries to enter "ABC" in a field designed for age (numeric), the system would flag it as an error.
*   **(Other examples - you can choose any two and explain):**
    *   **Format Check:** Verifies data is in a predefined format (e.g., date format DD/MM/YYYY, email format).
    *   **Completeness Check (Mandatory Check):** Ensures that required fields are not left blank.
    *   **Consistency Check:**  Verifies that related data items are consistent with each other (e.g., if total quantity is calculated, it matches the sum of individual quantities).
    *   **Check Digit:**  Used to detect transposition errors in long numbers (like account numbers or product codes). An extra digit is calculated based on the other digits and appended. The system recalculates the check digit when data is entered to verify accuracy.

**c. With the aid of diagram explain a typical testing process.** (6 marks)

**Testing Process Diagram (V-Model is a good one to draw):**

*   Draw a "V" shape.
*   **Left Side of the V (Verification - moving downwards):**
    1.  **Requirements Analysis:** Box labeled "Requirements"
    2.  **System Design:** Box labeled "High-Level Design"
    3.  **Module Design:** Box labeled "Low-Level Design"
    4.  **Coding:** Box labeled "Coding" (at the bottom point of the V)

*   **Right Side of the V (Validation - moving upwards):**
    5.  **Unit Testing:** Box labeled "Unit Testing" (aligned with "Coding") - Arrow from "Coding" to "Unit Testing"
    6.  **Integration Testing:** Box labeled "Integration Testing" (aligned with "Module Design") - Arrow from "Unit Testing" to "Integration Testing"
    7.  **System Testing:** Box labeled "System Testing" (aligned with "System Design") - Arrow from "Integration Testing" to "System Testing"
    8.  **Acceptance Testing:** Box labeled "Acceptance Testing" (aligned with "Requirements") - Arrow from "System Testing" to "Acceptance Testing"

*   **Horizontal connections:** Draw horizontal lines connecting "Requirements" to "Acceptance Testing," "System Design" to "System Testing," and "Module Design" to "Integration Testing," "Coding" to "Unit Testing." These lines represent the testing level being related to the corresponding development phase.

**Explanation of the Testing Process (Based on V-Model):**

1.  **Requirements Analysis Phase:**  Business requirements are gathered and documented.  *Relates to Acceptance Testing.*
2.  **System Design Phase:** Overall system architecture and design are created. *Relates to System Testing.*
3.  **Module Design Phase:**  Detailed design of individual modules/components is done. *Relates to Integration Testing.*
4.  **Coding Phase:**  Actual code is written based on the design. *Relates to Unit Testing.*

**Testing Phases (Right side of V):**

5.  **Unit Testing:**  Testing individual modules or components in isolation to ensure they function correctly. Done by developers.
6.  **Integration Testing:** Testing groups of integrated modules to verify they work together as designed. Focuses on interfaces and interactions between modules.
7.  **System Testing:** Testing the complete integrated system to ensure it meets the overall system requirements and functions as a whole. Tests functionality, performance, security, etc.
8.  **Acceptance Testing:**  Testing conducted by end-users or customers to validate that the system meets their business needs and is acceptable for deployment.  This often includes User Acceptance Testing (UAT).

**Key Idea of V-Model:**  Each testing phase is planned in parallel with a corresponding development phase.  The V-model emphasizes the relationship between testing and development, showing that testing should be considered from the very beginning of the project lifecycle.

---

Okay, that's Set 1 answered in detail.  Let me know which set you'd like to tackle next!  We can do Set 2 or Set 3, or if you have any follow-up questions about Set 1, feel free to ask.
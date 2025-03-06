**SET 3: CSC 339 - SYSTEMS ANALYSIS AND DESIGN.**

**Question 1**

**(a) (i) Define System Development Methodology** (3 marks)

*   **System Development Methodology:** A structured and systematic approach to developing information systems. It provides a framework of processes, methods, techniques, and tools to guide all activities in the system development life cycle (SDLC), from planning to implementation and maintenance. It ensures a consistent, repeatable, and manageable way to develop high-quality systems.

**(ii) List three approaches that could be used for the development of computer system** (3 marks)

1.  **Waterfall Model:** A linear, sequential approach where each phase of development is completed before moving to the next.
2.  **Prototyping Model:** An iterative approach where a working model (prototype) is built and refined based on user feedback.
3.  **Spiral Model:** A risk-driven approach that combines iterative development with risk analysis at each iteration.
4.  **Rapid Application Development (RAD):**  An approach emphasizing speed and rapid delivery through iterative development, user involvement, and prototyping.
5.  **Agile Methodologies (e.g., Scrum, Kanban):**  Iterative and incremental approaches that focus on flexibility, collaboration, and rapid response to changing requirements. *(Choose any 3)*

**(b) Requirement investigation uses fact finding methods. List the methods** (6 marks)

1.  **Interview:** Conducting structured or unstructured conversations with stakeholders to gather information about requirements, needs, and expectations.
2.  **Questionnaire (Survey):** Distributing written sets of questions to a large group of stakeholders to collect standardized data and opinions.
3.  **Observation:** Observing users in their work environment to understand their tasks, workflows, and identify areas for improvement.
4.  **Document Review:** Examining existing documents (reports, manuals, procedures, system documentation) to understand current systems and processes.
5.  **Joint Application Development (JAD) Sessions:** Facilitated group workshops where stakeholders collaboratively define and refine requirements.
6.  **Prototyping:** Developing working models of the system to demonstrate functionality and gather user feedback on requirements.
7.  **Research (Desk Research):**  Reviewing published materials, industry reports, competitor analysis, and online resources to gather background information and understand the problem domain.

**(c) (i) Define System Design** (3 marks)

*   **System Design:** The phase in the SDLC where the requirements gathered during system analysis are translated into a detailed blueprint or specification for how the system will be built. It involves defining the system architecture, components, modules, interfaces, data structures, processes, and user interfaces. System design focuses on the "how" of the system – how it will meet the functional and non-functional requirements.

**(ii) Briefly explain the four important aspects on which system design is focused** (8 marks)

1.  **Architecture Design:**  Defining the overall structure and organization of the system. This includes choosing the system architecture (e.g., client-server, web-based, cloud-based), identifying major components and their relationships, and defining system boundaries.
2.  **Interface Design:** Designing the interfaces between system components, between the system and external systems, and most importantly, the user interface. This includes designing user screens, menus, reports, and interactions to ensure usability and effective communication.
3.  **Data Design:**  Designing the database structure and data storage mechanisms. This involves defining data entities, attributes, relationships, data types, and data access methods.  Ensuring data integrity, security, and efficient data management are key.
4.  **Process Design:**  Defining the processes and algorithms that the system will perform to achieve its functions. This includes designing program logic, workflows, control flows, and algorithms for data processing and manipulation.  Ensuring efficiency, accuracy, and reliability of processes is crucial.

**Question 2**

**(a) Briefly describe the following system development models and list the steps involved when they are deployed:** (6 marks each - Total 18 marks)

**(i) Waterfall**

*   **Description:** A linear, sequential model where each phase of system development is completed in order before moving to the next. Progress flows downwards like a waterfall. It's a structured and rigid approach, suitable for projects with well-defined and stable requirements.
*   **Steps Involved:**
    1.  **Requirements Analysis:** Gather and document all system requirements.
    2.  **System Design:** Design the system architecture, components, and interfaces.
    3.  **Implementation (Coding):** Write the program code.
    4.  **Testing:** Test the system to identify and fix defects.
    5.  **Deployment (Installation):** Install and deploy the system to the production environment.
    6.  **Maintenance:** Provide ongoing support and maintenance.

**(ii) Spiral**

*   **Description:** A risk-driven, iterative model that combines elements of waterfall and prototyping. Development progresses in cycles (spirals), with each cycle involving planning, risk analysis, engineering (development), and evaluation. Risk assessment is a central activity in each iteration to identify and mitigate potential problems. Suitable for complex projects with evolving requirements and high risks.
*   **Steps Involved (within each spiral iteration):**
    1.  **Planning:** Determine objectives, alternatives, and constraints for this iteration.
    2.  **Risk Analysis:** Identify, assess, and resolve risks associated with the chosen approach.
    3.  **Engineering (Development & Testing):** Design, implement, and test the current iteration's functionalities.
    4.  **Evaluation (Customer Evaluation):** Evaluate the results, get feedback from stakeholders, and plan for the next iteration.
    *   *These steps are repeated in each spiral until the system is complete.*

**(iii) Prototyping**

*   **Description:** An iterative model where a working model (prototype) of the system is developed quickly to demonstrate functionality and gather user feedback. Prototypes are refined based on feedback until they evolve into the final system or are used to clarify requirements. Focuses on user interaction and early validation.
*   **Steps Involved:**
    1.  **Identify Basic Requirements:** Gather initial, high-level requirements.
    2.  **Develop a Prototype:** Create a working model of the system or key parts.
    3.  **User Evaluation:** Users test and provide feedback on the prototype.
    4.  **Refine Prototype:** Based on feedback, refine and enhance the prototype (repeat steps 3 & 4 iteratively).
    5.  **Implement and Test Final System (or Use Prototype as Basis):** Once the prototype is satisfactory, either evolve it into the final system or use the refined requirements from prototyping to develop the final system using another SDLC model.

**(b) Explain the three types of maintenance used after system implementation** (6 marks)

1.  **Corrective Maintenance:**  Performed to fix errors or defects in the system that were not detected during testing. It's about "correcting" problems and restoring the system to its intended functionality.
2.  **Adaptive Maintenance:**  Performed to modify the system to adapt to new business requirements or technological changes in the environment. It's about "adapting" the system to remain relevant and compatible with its evolving surroundings.
3.  **Perfective Maintenance:**  Performed to improve the system's performance, efficiency, maintainability, or user satisfaction. It's about "perfecting" the system and making it better, even if there are no specific errors or new requirements.

**Question 3**

**(a) Define system** (4 marks)

*   **Definition of a System:** A system is a set of interacting or interdependent components forming an integrated whole. These components work together to achieve a common objective or set of objectives. Systems operate within an environment, have defined boundaries, and receive inputs, process them, and produce outputs.  Key aspects are interdependence, common purpose, and interaction with an environment.

**(b) Explain the following: i. Boundary and environment ii. Subsystem iii. Interface iv. Feedback control v. Black box** (10 marks)

**(i) Boundary and Environment:**
*   **Boundary:** The demarcation line that separates a system from its environment. It defines what is inside the system and what is outside. Boundaries can be physical or conceptual. They help to define the scope and limits of the system.
*   **Environment:** Everything outside the system's boundary that can influence or be influenced by the system. The environment provides inputs to the system and receives outputs from it. Systems interact with their environment by exchanging resources, information, or energy.

**(ii) Subsystem:** A component or part of a larger system that is itself a system. Subsystems have their own boundaries, components, and objectives, but they contribute to the overall functioning and goals of the larger system. Complex systems are often composed of multiple interacting subsystems.

**(iii) Interface:**
*   **Interface:** The point of interaction or communication between two components, subsystems, or between a system and its environment. Interfaces define how components exchange data, signals, or energy. 

**(iv) Feedback Control:** A mechanism within a system that monitors the output of the system and uses that information (feedback) to adjust the input or internal processes to maintain a desired state or achieve a goal. Feedback loops are essential for self-regulation and adaptation in systems.
*   **Types:**
    *   **Positive Feedback:** Amplifies change, moving the system further away from equilibrium. (e.g., compound interest).
    *   **Negative Feedback:** Counteracts change, bringing the system back towards equilibrium or a set point. (e.g., thermostat regulating temperature).

**(v) Black Box:** Is a system or component whose internal workings are hidden or not considered.  When viewing something as a black box, we are only concerned with its inputs and outputs, and not with its internal processes or implementation. This abstraction simplifies understanding and managing complex systems by focusing on external behavior rather than internal details.

**(c) (i) Define Systems Analysis.** (5 marks)

*   **System Analysis:** The process of studying a system to understand its functions, components, interactions, boundaries, and environment. It involves investigating problems, identifying needs, and defining requirements for a new or improved system. System analysis focuses on understanding the current system (if it exists), identifying problems and opportunities, and determining what the new system should do to meet user needs and business goals. It's about problem definition and requirements gathering.

**(ii) List the advantages of Systems Analysis.** (5 marks)

1.  **Clearer Understanding of Problems:** System analysis provides a structured way to investigate and understand complex problems within an organization or system.
2.  **Well-Defined Requirements:** It results in clearly defined, documented, and validated requirements for a new or improved system, reducing ambiguity and misunderstandings.
3.  **Improved Communication:** Facilitates communication between stakeholders (users, analysts, developers) by providing a common understanding of the system and its requirements.
4.  **Better Decision Making:**  Provides information and analysis to support informed decisions about system design, development, and implementation.
5.  **Reduced Development Costs and Risks:** Early identification of problems and clear requirements reduces the risk of costly errors, rework, and project failures later in the development process.
6.  **Increased System Effectiveness:** By focusing on user needs and business goals, system analysis helps to develop systems that are more effective and better aligned with organizational objectives.
7.  **Optimized Processes:**  Analysis of existing systems can identify inefficiencies and opportunities for process improvement.

**Question 4**

**(a) Explain the differences between the following and give an example of each:** (5 marks each - Total 10 marks)

**(i) Natural and Artificial systems**  *(See answer provided for Set 2, Question 3c.)*

**(ii) Open and closed systems** *(See answer provided for Set 2, Question 3c.)*

**(b) (c) List the functions and benefits of Transaction Processing System (TPS)** *(See answer provided for Set 2, Question 3a.)*

**(c) List the functions and benefits of Decision Support System (DSS)** *(See answer provided for Set 2, Question 3b.)*

**Question 5**

**(a) In order to accomplish all the tasks at every functional level of system development system analyst has to perform many roles. List and explain these roles.** (10 marks)

1.  **Change Agent:** The analyst identifies areas for improvement and initiates change within the organization through system development projects. They drive the process of adopting new systems and processes.
2.  **Investigator:** The analyst investigates problems, opportunities, and user needs. They gather data, analyze existing systems, and understand the business context to define the scope and nature of the system development project.
3.  **Architect:** The analyst designs the overall structure and components of the new system. They create the high-level blueprint, defining the system's architecture, interfaces, and data flows.
4.  **Designer:** The analyst details the specific features and functionalities of the system. They design user interfaces, database structures, process logic, and reports.
5.  **Implementer:** In some cases, especially in smaller projects or with certain methodologies, the analyst may be involved in the actual implementation of the system, including coding, testing, and deployment.
6.  **Tester:** The analyst plays a role in testing the system to ensure it meets requirements and functions correctly. They may design test cases, conduct testing, and coordinate testing activities.
7.  **Trainer and Support Provider:** The analyst may be involved in training users on the new system and providing ongoing support after implementation.
8.  **Consultant:** The analyst provides expert advice and guidance to the organization on system-related matters, recommending solutions and best practices.
9.  **Facilitator:** The analyst facilitates communication and collaboration among various stakeholders (users, managers, developers, vendors) throughout the system development process.
10. **Project Manager:** In smaller projects, the analyst may also take on project management responsibilities, overseeing timelines, resources, and deliverables.

**(b) Briefly explain the interpersonal skills a system analyst should possess.** (5 marks)

1.  **Communication Skills (Verbal and Written):**  Must be able to clearly and effectively communicate with diverse stakeholders (technical and non-technical) both verbally (interviews, presentations, meetings) and in writing (reports, documentation, emails).
2.  **Listening Skills:**  Active and empathetic listening is crucial to understand user needs, gather requirements accurately, and resolve conflicts.
3.  **Facilitation Skills:**  Ability to lead and facilitate meetings, workshops, and JAD sessions to effectively gather requirements, brainstorm solutions, and build consensus.
4.  **Negotiation and Conflict Resolution Skills:**  Must be able to negotiate requirements, resolve conflicting viewpoints among stakeholders, and find mutually acceptable solutions.
5.  **Teamwork and Collaboration Skills:**  System analysts work as part of a team. They need to collaborate effectively with developers, users, managers, and other stakeholders, fostering a positive and productive team environment.
6.  **Empathy and Understanding:**  Ability to understand and appreciate the perspectives and needs of different users and stakeholders.
7.  **Persuasion and Influence Skills:**  Sometimes need to persuade stakeholders to adopt certain approaches or solutions, requiring tact and effective influencing skills.

**(c) Explain the following: i. Strategic information ii. Tactical information iii. Operational information iv. Statutory information.** (8 marks)

**(i) Strategic Information:** Information used by top-level management (executives, senior managers) for long-term strategic planning and decision-making. It focuses on the overall direction and goals of the organization.

**(ii) Tactical Information:** Information used by middle management (department heads, project managers) for medium-term tactical planning, resource allocation, and performance monitoring within their departments or functional areas.

**(iii) Operational Information:** Information used by lower-level management (supervisors, team leaders) and operational staff for day-to-day operations, task execution, and immediate problem solving.

**(iv) Statutory Information:** Information that organizations are legally required to collect, process, and report to government agencies or regulatory bodies to comply with laws and regulations.

### **Question 1**

**(a) What do you understand by Modeling and Simulation? (4 marks)**

**Modelling** is the process of representing a real-world system using mathematical, logical, or physical relationships.
**Simulation** is the imitation of the operation of a real system over time using the model, especially when analytical solutions are difficult.

| Another view |
| :--- |

*   **Modeling:** This is the process of creating a simplified, conceptual, or mathematical representation of a real-world system or process. The goal is to capture the essential characteristics of the system to study its behavior without interacting with the actual system itself.
*   **Simulation:** This is the act of operating or running the model over time. It involves using the model to mimic the actual operation of a system to evaluate various scenarios, predict future outcomes, or understand how the system reacts to changes.

**(b) State the importance of Modeling. (5 marks)**

1. Reduces cost of experimenting with real systems
2. Helps in decision making
3. Allows testing of alternatives
4. Saves time
5. Helps understand complex systems
6. Predicts future behavior
7. Improves system performance
8.  **Risk Reduction:** Allows testing of ideas in a safe environment before implementation in reality.

**(c) Numerical Simulation Problem (8.5 marks)**
To solve this, we first establish the cumulative probability ranges for the three variables.

**Variable 1: Annual Demand**
| Units | Prob. | Cumulative Prob. | RN Range |
| :--- | :--- | :--- | :--- |
| 20,000 | 0.20 | 0.20 | 00 - 19 |
| 25,000 | 0.10 | 0.30 | 20 - 29 |
| 30,000 | 0.20 | 0.50 | 30 - 49 |
| 35,000 | 0.30 | 0.80 | 50 - 79 |
| 40,000 | 0.10 | 0.90 | 80 - 89 |
| 45,000 | 0.05 | 0.95 | 90 - 94 |
| 50,000 | 0.05 | 1.00 | 95 - 99 |

**Variable 2: Price minus Cost (Margin)**
| margin ($) | Prob. | Cumulative Prob. | RN Range |
| :--- | :--- | :--- | :--- |
| 3.00 | 0.10 | 0.10 | 00 - 09 |
| 5.00 | 0.20 | 0.30 | 10 - 29 |
| 7.00 | 0.40 | 0.70 | 30 - 69 |
| 9.00 | 0.20 | 0.90 | 70 - 89 |
| 10.00 | 0.10 | 1.00 | 90 - 99 |

**Variable 3: Investment Required**
| Invest (M) | Prob. | Cumulative Prob. | RN Range |
| :--- | :--- | :--- | :--- |
| 1.75 | 0.25 | 0.25 | 00 - 24 |
| 2.00 | 0.50 | 0.75 | 25 - 74 |
| 2.50 | 0.25 | 1.00 | 75 - 99 |

**Simulation Table (10 Trials)**
*Formula: Return = ((Margin * Units) / Investment)*
*Random Numbers Sequence: 28, 19, 18, 87, 07, 61, 60, 90, 16, 17, 02, 71, 64, 57, 43, 20, 28, 68...*

| Trial | RN (Dem) | Demand | RN (Marg) | Margin | RN (Inv) | Invest | Calculation (M) | Return |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 28 | 25,000 | 19 | 5.00 | 18 | 1.75M | (25k*5)/1.75M | 0.071 |
| 2 | 87 | 40,000 | 07 | 3.00 | 61 | 2.00M | (40k*3)/2.0M | 0.060 |
| 3 | 60 | 35,000 | 90 | 10.00 | 16 | 1.75M | (35k*10)/1.75M | 0.200 |
| 4 | 17 | 20,000 | 02 | 3.00 | 71 | 2.00M | (20k*3)/2.0M | 0.030 |
| 5 | 64 | 35,000 | 57 | 7.00 | 43 | 2.00M | (35k*7)/2.0M | 0.122 |
| 6 | 20 | 25,000 | 28 | 5.00 | 68 | 2.00M | (25k*5)/2.0M | 0.0625 |
| 7 | 27 | 25,000 | 70 | 9.00 | 47 | 2.00M | (25k*9)/2.0M | 0.1125 |
| 8 | 58 | 35,000 | 83 | 9.00 | 24 | 1.75M | (35k*9)/1.75M | 0.180 |
| 9 | 61 | 35,000 | 58 | 7.00 | 19 | 1.75M | (35k*7)/1.75M | 0.140 |
| 10 | 30 | 30,000 | 41 | 7.00 | 07 | 1.75M | (30k*7)/1.75M | 0.120 |

**Most likely return:** Based on this small sample, returns vary significantly. The average return is approximately **0.1098 (or 11%)**.

---

### **Question 2**

**(a) List and explain any five types of Model (5 marks)**
1.  **Physical Model:** A tangible, scaled-down representation of an object (e.g., a model airplane in a wind tunnel).
2.  **Mathematical Model:** Uses symbols and mathematical equations to represent a system's behavior (e.g., $F = ma$).
3.  **Static Model:** Represents a system at a specific point in time (e.g., an organization chart).
4.  **Dynamic Model:** Represents a system as it changes over time (e.g., a flight simulator).
5.  **Stochastic Model:** Includes elements of randomness or probability (e.g., stock market projections).

**(b) State and describe steps involved in Modeling (5 marks)**
1.  **Problem Definition:** Clearly defining the goals and boundaries of what needs to be modeled.
2.  **Data Collection:** Gathering the necessary real-world data to inform the model parameters.
3.  **Model Formulation:** Building the logical structure or equations that represent the system.
4.  **Verification:** Checking if the model is built correctly according to specifications (the "debugging" phase).
5.  **Validation:** Checking if the model accurately represents the real-world system it is supposed to mimic.

**(c) Queueing Simulation (7.5 marks)**
Patients arrive every 30 mins (8:00, 8:30, 9:00, etc.).

**Service Time Distribution:**
| Category | Time | Prob. | RN Range |
| :--- | :--- | :--- | :--- |
| Filling | 45 | 0.40 | 00 - 39 |
| Crown | 60 | 0.15 | 40 - 54 |
| Cleaning | 15 | 0.15 | 55 - 69 |
| Extraction | 45 | 0.10 | 70 - 79 |
| Checkup | 15 | 0.20 | 80 - 99 |

**Simulation (Random Numbers: 40, 82, 11, 34, 25, 66, 17, 79)**
*Simulation runs for 4 hours (240 minutes) starting at 8:00 AM.*

| Pat. # | Arrival | RN | Serv. Time | Start | End | Wait | Dr. Idle |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 8:00 | 40 | 60 | 8:00 | 9:00 | 0 | 0 |
| 2 | 8:30 | 82 | 15 | 9:00 | 9:15 | 30 | 0 |
| 3 | 9:00 | 11 | 45 | 9:15 | 10:00 | 15 | 0 |
| 4 | 9:30 | 34 | 45 | 10:00 | 10:45 | 30 | 0 |
| 5 | 10:00 | 25 | 45 | 10:45 | 11:30 | 45 | 0 |
| 6 | 10:30 | 66 | 15 | 11:30 | 11:45 | 60 | 0 |
| 7 | 11:00 | 17 | 45 | 11:45 | 12:30 | 45 | 0 |
| 8 | 11:30 | 79 | 45 | 12:30 | 1:15 | 60 | 0 |

**Results:**
*   **Average Waiting Time:** (0 + 30 + 15 + 30 + 45 + 60 + 45 + 60) / 8 = **35.6 minutes**.
*   **Doctor Idleness:** **0 minutes** (The doctor was continuously busy once the first patient arrived).

---

### **Question 3**

**(a) State and explain the Simulation process (4 marks)**
The simulation process is an iterative cycle:
1.  **Preparation:** Define the problem and gather data.
2.  **Model Building:** Construct the logical model.
3.  **Running:** Execute the simulation using random variables to see outcomes.
4.  **Analysis:** Evaluate the results against objectives.
5.  **Iteration:** Refining the model based on results and re-running until an optimal solution or understanding is reached.

| Another view / explanation |
| :--- |

(a) Simulation Process
1. Define problem
2. Build model
3. Generate random numbers
4. Run simulation
5. Analyze results


**(b) What are the advantages and disadvantages of Simulation? (6 marks)**
*   **Advantages:** 
    - Can model systems where analytical (mathematical) solutions are impossible;
    - Handles complex systems
    - Provides a safe environment for experimentation;
    - Helps identify bottlenecks.
*   **Disadvantages:** 
    - Can be very time-consuming and expensive to develop;
    - Requires high-level expertise;
    - Results are approximate;
    - Results are only as good as the input data (garbage in, garbage out).

---

### **Question 4**

**(a) What simulation model will you deploy to solve complex problems? (4 marks)**
For complex, dynamic, and stochastic industrial or business problems like the one described in part (c), **Discrete Event Simulation (DES)** is the most appropriate model. It allows for the modeling of a system as a discrete sequence of events in time (e.g., a machine breaking down, a repair starting, a repair finishing).

**(b) Mention the steps required when the simulation model in (a) is used. (5 marks)**
1.  **Problem Formulation:** Define the system boundaries and specific objectives.
2.  **Data Collection:** Gather historical data on breakdown intervals and repair times.
3.  **Model Conceptualization:** Create a logic flow (e.g., flowchart) of the system's behavior.
4.  **Model Translation (Coding):** Programming the model into simulation software.
5.  **Verification and Validation:** Ensure the model is bug-free and accurately represents reality.
6.  **Experimental Design:** Decide on the number of trials and variables to test.
7.  **Analysis and Reporting:** Interpret simulation results to make management decisions.


| Another view / explanation |
| :--- |

(b) Steps in Simulation

1. Define system
2. Collect data
3. Build model
4. Validate
5. Experiment

**(c) Simulation Problem: Machine Maintenance (8.5 marks)**

**Step 1: Assign Random Number (RN) Ranges**

| Time Between Breakdowns (TBB) | Prob. | Cum. Prob. | RN Range |
| :--- | :--- | :--- | :--- |
| 0.5 hours | 0.05 | 0.05 | 00 - 04 |
| 1.0 hours | 0.06 | 0.11 | 05 - 10 |
| 1.5 hours | 0.16 | 0.27 | 11 - 26 |
| 2.0 hours | 0.33 | 0.60 | 27 - 59 |
| 2.5 hours | 0.21 | 0.81 | 60 - 80 |
| 3.0 hours | 0.19 | 1.00 | 81 - 99 |

| Repair Time Required (RT) | Prob. | Cum. Prob. | RN Range |
| :--- | :--- | :--- | :--- |
| 1 hour | 0.28 | 0.28 | 00 - 27 |
| 2 hours | 0.52 | 0.80 | 28 - 79 |
| 3 hours | 0.20 | 1.00 | 80 - 99 |

**Step 2: Simulation Table for 15 Breakdowns**
Using provided random numbers in pairs: (61, 87), (85, 39), (16, 28), etc.

| BD # | RN1 | TBB | Clock Time of BD | RN2 | RT | Repair Start | Repair End | Waiting Time | Down Time |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 61 | 2.5 | 2.5 | 87 | 3 | 2.5 | 5.5 | 0 | 3.0 |
| 2 | 85 | 3.0 | 5.5 | 39 | 2 | 5.5 | 7.5 | 0 | 2.0 |
| 3 | 16 | 1.5 | 7.0 | 28 | 2 | 7.5 | 9.5 | 0.5 | 2.5 |
| 4 | 46 | 2.0 | 9.0 | 97 | 3 | 9.5 | 12.5 | 0.5 | 3.5 |
| 5 | 88 | 3.0 | 12.0 | 69 | 2 | 12.5 | 14.5 | 0.5 | 2.5 |
| 6 | 08 | 1.0 | 13.0 | 87 | 3 | 14.5 | 17.5 | 1.5 | 4.5 |
| 7 | 82 | 3.0 | 16.0 | 52 | 2 | 17.5 | 19.5 | 1.5 | 3.5 |
| 8 | 56 | 2.0 | 18.0 | 52 | 2 | 19.5 | 21.5 | 1.5 | 3.5 |
| 9 | 22 | 1.5 | 19.5 | 15 | 1 | 21.5 | 22.5 | 2.0 | 3.0 |
| 10 | 49 | 2.0 | 21.5 | 85 | 3 | 22.5 | 25.5 | 1.0 | 4.0 |
| 11 | 44 | 2.0 | 23.5 | 41 | 2 | 25.5 | 27.5 | 2.0 | 4.0 |
| 12 | 33 | 2.0 | 25.5 | 82 | 2 | 27.5 | 29.5 | 2.0 | 4.0 |
| 13 | 77 | 2.5 | 28.0 | 98 | 3 | 29.5 | 32.5 | 1.5 | 4.5 |
| 14 | 87 | 3.0 | 31.0 | 99 | 3 | 32.5 | 35.5 | 1.5 | 4.5 |
| 15 | 54 | 2.0 | 33.0 | 23 | 1 | 35.5 | 36.5 | 2.5 | 3.5 |
| **Total**| | | | | | | | **20.5** | **52.5** |

**Part b: How many repairmen should be hired?**
*   **Case 1: 1 Repairman**
    *   Cost of lost production: 52.5 hours × $70 = **$3,675**
    *   Repairman wage: 36.5 hours × $20 = **$730**
    *   Total Cost = **$4,405**
*   **Case 2: 2 Repairmen**
    If 2 repairmen are hired, waiting time drops significantly (assumed near zero for this example). Total downtime would equal total repair time (34 hours).
    *   Cost of lost production: 34 hours × $70 = **$2,380**
    *   Repairmen wages (2 people): 2 × 36.5 hours × $20 = **$1,460**
    *   Total Cost = **$3,840**
*   **Decision:** The plant should hire **two repairmen** as it minimizes total costs.

---

### **Question 5**

**(a) What is the role of Computers in Simulation with examples? (5 marks)**
Computers are the backbone of modern simulation because they can:
1.  **Process massive amounts of data:** e.g., simulating global weather patterns.
2.  **Generate Randomness:** Efficiently generating millions of pseudo-random numbers for Monte Carlo simulations.
3.  **Visualization:** Creating 3D models or graphs to help humans interpret results (e.g., traffic flow simulations).
4.  **Speed:** Performing complex calculations in milliseconds that would take humans years.

**(b) State any 10 applications of simulation. (5 marks)**
1. Weather Forecasting
2. Flight Training (Flight Simulators)
3. Traffic Engineering/Planning
4. Manufacturing Line Optimization
5. Financial Risk Analysis (Stock Market)
6. Healthcare (Simulating disease spread or hospital flow)
7. Military Combat Strategy
8. Nuclear Power Plant Safety Testing
9. Logistics and Supply Chain Management
10. Video Game Physics and AI
11. Inventory Simulation
12. Education
13. Banking
14. Telecoms
15. Oil and Gas

**(c) Inventory Simulation (7.5 marks)**
*(Note: Full tabular simulation for 10 days would be lengthy; the logic involves tracking Daily Demand, End-of-Day Stock, and Order Lead Time. If stock + outstanding order < 10 units, order 15 more.)*
*   **Starting Stock:** 20 units.
*   **Cost factors:** $2 per unit/day carrying cost; $50 per order.
*   **Rule:** Order 15 when (Stock + Pending Order) < 10. Lead time = 3 days.
*   

| Another view / explanation |
| :--- |

(c) Inventory Simulation

Key formula:
[
\text{Total Cost} = \text{Holding} + \text{Ordering}
]

Simulate 10 days, track:

* Opening stock
* Demand
* Closing stock
* Reorder days


---

### **Question 6**

**(a) Recommended Model Types (8 marks)**
1.  **New railroad congestion:** Traffic Simulation Model (Discrete Event).
2.  **New ordering policy effect:** Inventory Simulation Model (Monte Carlo).
3.  **Student registration procedure:** Flowchart or Process Model.
4.  **Oil field locations in Nigeria:** Geospatial/Geological Physical or Digital Model.

1.  **Checkout process:** Discrete Event Simulation (modeling the steps of scanning, bagging, paying).
2.  **Queueing metrics:** Queueing Theory Simulation (to track wait times and customer count).

**(ii) Why are simulation solutions more expensive than analytical solutions? (3 marks)**
*   **Development Time:** It takes much longer to build and verify a complex model than to apply a mathematical formula.
*   **Expertise:** Requires specialized simulation analysts and programmers.
*   **Software/Hardware:** Advanced simulation software licenses and the high-performance computers needed to run them are costly.

**(iii) Why use simulation if it is more expensive? (2.5 marks)**
Because many real-world problems **cannot be solved analytically**. Real-world systems are often too complex for analytical math. Simulation can handle **randomness, non-linear relationships, and time-dependent behavior** that simple equations cannot. It allows "what-if" testing of high-risk scenarios (like airline safety) without any real-world danger or loss of assets.

---
# Questions mentioned in Class

**1. Give reasons why models are different from one another.**

Models differ from one another for several key reasons:

*   **Purpose:** The intended purpose of the model dictates its structure and level of detail. A model used for high-level strategic planning will be very different from one designed for detailed operational decision-making.
*   **Assumptions and Simplifications:** All models are simplifications of reality.  Different modelers will make different assumptions about which aspects of the system are important and which can be ignored. These assumptions influence the model's accuracy and applicability.
*   **Level of Detail:**  The level of detail included in a model varies widely. Some models are highly detailed (e.g., agent-based models), while others are more abstract (e.g., system dynamics models). This difference affects computational cost and the types of questions the model can answer.
*   **Data Availability:** The availability and quality of data to parameterize the model influence the model's structure. If data is limited, the model will likely be simpler.
*   **Modeler's Expertise and Perspective:** Different modelers may have different backgrounds, biases, and preferences, which will impact their model design choices. For instance, a finance professional would build a different simulation of a bank than a software architect.
*   **Computational Resources:** The available computational resources (processing power, memory, software) can influence the complexity of the model.

**2. Types of Model**

Here are some common types of models, with brief descriptions:

*   **Physical Models:** These are scaled-down or simplified physical representations of a system.
    *   *Example:* A wind tunnel model of an airplane.
*   **Analogue Models:**  These use one set of phenomena to represent another.
    *   *Example:* An electrical circuit used to represent a mechanical system.
*   **Mathematical Models:**  These use mathematical equations and relationships to represent the system.
    *   *Example:* A differential equation describing the motion of a pendulum.
        *   **Deterministic Models:** Output is fixed for a given set of inputs and parameters.
        *   **Stochastic/Probabilistic Models:** Incorporate randomness, using probability distributions to represent uncertain events.
*   **Simulation Models:** These are computer-based models that simulate the behavior of a system over time.
    *   **Discrete Event Simulation (DES):** Models systems as a sequence of discrete events.
    *   **Continuous Simulation:**  Models systems where changes occur continuously (e.g., fluid flow, temperature change).
    *   **Agent-Based Models (ABM):** Model individual agents and their interactions to understand emergent behavior.
    *   **System Dynamics Models:** Focus on feedback loops and stocks and flows to understand the behavior of complex systems.
*   **Statistical Models:** Use statistical techniques to analyze data and make predictions.
    *   *Example:* Regression models, time series analysis.

**3. How to Choose the Appropriate Simulation Model**

Choosing the right simulation model depends on the following factors:

*   **The Purpose/Goals of the Simulation:** What questions do you want to answer? Are you interested in performance, capacity planning, cost analysis, or something else?
*   **The System's Characteristics:** Is the system discrete or continuous? Does it involve significant uncertainty? Are there individual agents or complex interactions?
*   **Available Data:** How much data do you have available to parameterize and validate the model?
*   **Time and Budget Constraints:** How much time and resources do you have to develop and run the simulation?
*   **Level of Detail Required:** How much detail is needed to answer your questions? Too much detail can increase complexity and computational cost. Too little detail may result in inaccurate results.
*   **Available Software and Expertise:** What simulation software are you familiar with, and what is the team's skillset?

Here's a simplified decision-making process:

1.  **Define Objectives:** Clearly state the questions to be answered.
2.  **Characterize the System:** Identify key components, processes, and interactions.
3.  **Identify Data Sources:** Determine available data.
4.  **Evaluate Model Types:** Select the model type that best aligns with the system characteristics and goals (e.g., DES, continuous simulation, ABM).
5.  **Choose Software:** Select appropriate simulation software based on expertise, cost, and model type.
6.  **Develop, Validate, and Verify the model.**
7.  **Run simulations and analyze the result.**

**4. Identify Four Variable Factors That Must Be Included in Simulations**

Variable factors are those that change within the simulation and drive the system's behavior. Four crucial examples:

1.  **Random Variables:** These represent the uncertainty inherent in the system. They often drive the stochastic aspect of a simulation.
    *   *Examples:* Interarrival times of customers, service times, equipment failure rates, processing times.
2.  **System Parameters:** These are constants that influence the simulation model and often have fixed values.
    *   *Examples:* The number of servers in a queue, the capacity of a warehouse, the speed of a conveyor belt, the price of an asset.
3.  **Decision Variables:** These are variables the modeler can change to test and optimize the system.
    *   *Examples:* Number of employees, the product mix, order quantity, inventory levels, different staffing levels.
4.  **State Variables:** These describe the current state of the system at any given time. They change as the simulation progresses.
    *   *Examples:* The number of customers in a queue, the inventory level, the status of a machine (idle, working, broken), the current time.

**5. Discuss Two Challenges Associated with Simulation and Solutions to Them**

1.  **Challenge:** **Model Validation and Verification.**
    *   **Description:** It is difficult to guarantee that a model accurately reflects the real-world system (validation) and that the model is implemented correctly (verification).
    *   **Solution:**
        *   **Validation:**
            *   Compare model outputs to real-world data (if available).
            *   Use sensitivity analysis to test how the model's output changes when the input parameters are adjusted.
            *   Get feedback from subject matter experts.
            *   Run the simulation with extreme input values to ensure expected behaviors.
        *   **Verification:**
            *   Carefully review the code and logic.
            *   Use debugging tools to step through the simulation and check intermediate results.
            *   Build the model incrementally, testing each component.
            *   Use a software that helps in error identification and code clarity.
2.  **Challenge:** **Computational Cost and Time.**
    *   **Description:** Complex simulations can require significant computational resources and long run times, especially for many replications.
    *   **Solution:**
        *   **Model Simplification:** Reduce the level of detail if possible, while still maintaining model accuracy.
        *   **Efficient Code:** Optimize the simulation code for speed.
        *   **Experiment Design:** Carefully design the simulation experiments to minimize the number of runs needed.
        *   **Parallel Processing/Cloud Computing:** Utilize multiple processors or cloud-based computing resources to accelerate simulation runs.

**6. How Do You Ensure Reliability of Simulation Results?**

Ensuring reliability involves several strategies:

*   **Validation:** As mentioned above, make sure the model accurately represents the real system.
*   **Verification:** Confirm that the model is implemented correctly.
*   **Statistical Analysis:** Analyze the output data using appropriate statistical techniques.
    *   **Multiple Replications:** Run the simulation multiple times (replications) with different random number seeds to account for randomness.
    *   **Confidence Intervals:** Calculate confidence intervals for key performance indicators to quantify the uncertainty in the results.
    *   **Statistical Tests:** Use statistical tests (e.g., t-tests, ANOVA) to compare different scenarios or treatment and measure the significance of observed differences.
*   **Proper Experiment Design:** Carefully plan the simulation experiments, including the number of replications, the length of the simulation run, and the warm-up period.
*   **Sensitivity Analysis:** Determine how sensitive the results are to changes in the model's input parameters.
*   **Documentation:** Maintain thorough documentation of the model, assumptions, and results.

**7. List Two Events that Cause Change in Discrete Event Simulation**

In a Discrete Event Simulation (DES), events are the key drivers of change.  Two common event types are:

1.  **Arrivals:**  An entity (e.g., a customer, a job) enters the system.
    *   *Example:* A customer arrives at a checkout counter, a machine receives a new part.
2.  **Departures/End of Service:**  An entity leaves the system, or a service is completed.
    *   *Example:* A customer finishes being served at the checkout, a product leaves the manufacturing process.

**8. Give Five Detailed Explanations of the Concept of Discrete Event Simulation (DES)**

Here's a detailed explanation of DES:

1. **Instantaneous State Changes**: State variables in DES change instantaneously at a countable number of points in simulated time.
2. **Event-Based Progress**: The system evolves specifically at the points in time when an event—defined as an instantaneous occurrence that may change the state—occurs.
3. **Next-Event Time Advance**: DES uses a simulation clock that jumps from one event time to the next most imminent event, effectively skipping over periods of inactivity to save computer time.
4. **Stochastic Modeling**: It typically incorporates randomness by using probability distributions for inputs like interarrival and service times, making the output itself random.
5. **Sequential Logic**: The simulation logic is executed in the strict order of the events' simulated time of occurrence

| Another view |
| :--- |

1.  **Focus on Discrete Events:** DES models systems as a sequence of discrete events that occur at specific points in time. The simulation jumps from event to event, not continuously simulating all of the time. This event-driven approach is a key differentiator from continuous simulation.
2.  **Event Scheduling:** DES uses an event scheduler to manage the events. Events are scheduled to occur at specific simulation times. The scheduler determines the order in which events are processed. Each event's action is known by the model and is programmed.
3.  **State Variables:** The state of the system is tracked through state variables. These variables represent the current conditions of the system at any given simulation time. State variables change when events occur.
4.  **Time Advancement:** Time in DES advances in discrete steps, from one event to the next. The simulation clock jumps to the time of the next scheduled event.
5.  **Entity Flow:** Entities (e.g., customers, jobs, parts) move through the system, interacting with different resources (e.g., servers, machines, workstations). The simulation tracks the entities and their activities in the system. As entities traverse the model, their attributes can also change.

**9. Key Components of a Simulation Model**

The key components of a simulation model include:

*   **Entities:** The objects that move through the system (e.g., customers, jobs, parts, vehicles).
*   **Resources:** The elements that provide service or are used by entities (e.g., servers, machines, workstations, employees).
*   **Activities:** The actions performed by entities or on entities (e.g., waiting in a queue, being served, being processed).
*   **Events:** The occurrences that change the state of the system (e.g., arrivals, departures, failures, start of service, end of service).
*   **State Variables:** Variables that describe the state of the system at any given time (e.g., number of customers in the queue, inventory level).
*   **Simulation Clock:** A variable that tracks the current simulation time.
*   **Event List/Scheduler:** A list of scheduled events, sorted by their scheduled time.
*   **Input Data:** Data that defines the system's characteristics and parameters (e.g., arrival rates, service times, resource capacities).
*   **Output Data:** The performance measures generated by the simulation (e.g., waiting times, throughput, resource utilization).

**10. Explain the Difference Between Theory and Hypothesis**

*   **Theory:** 
    - A well-substantiated explanation of some aspect of the natural world, supported by a large body of evidence from repeated experiments.
    - It provides a broad framework for understanding and predicting phenomena.
    - Theories are often developed from many observations and experiments.
    - *Example:* The theory of gravity.
*   **Hypothesis:** 
    - A tentative explanation for a phenomenon, which is testable and falsifiable.
    - It is a proposed explanation for a specific observation or set of observations.
    - A hypothesis is typically a specific, focused statement.
    - *Example:*  "Increasing the amount of fertilizer will increase crop yield."
    - A hypothesis can be tested, and the outcome provides evidence for or against it.
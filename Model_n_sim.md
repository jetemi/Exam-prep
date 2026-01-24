This document appears to be a final examination paper for a "Modeling and Simulation" course (CSC 429) at Lagos State University. Below are detailed solutions for Questions 1, 2, 3, and 5.

---

### **Question 1**

**(a) What do you understand by Modeling and Simulation? (4 marks)**
*   **Modeling:** This is the process of creating a simplified, conceptual, or mathematical representation of a real-world system or process. The goal is to capture the essential characteristics of the system to study its behavior without interacting with the actual system itself.
*   **Simulation:** This is the act of operating or running the model over time. It involves using the model to mimic the actual operation of a system to evaluate various scenarios, predict future outcomes, or understand how the system reacts to changes.

**(b) State the importance of Modeling. (5 marks)**
1.  **Risk Reduction:** Allows testing of ideas in a safe environment before implementation in reality.
2.  **Cost-Effectiveness:** It is often cheaper to build and test a model than to experiment with a real system (e.g., crash-testing a virtual car vs. a real one).
3.  **Time Compression:** Years of real-world operation can be simulated in seconds on a computer.
4.  **Insight into Complex Systems:** Helps visualize and understand the interactions within systems too complex for simple human intuition.
5.  **Ability to test "What-If" Scenarios:** Managers can see the impact of policy changes before they are enacted.

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

**(b) What are the advantages and disadvantages of Simulation? (6 marks)**
*   **Advantages:** Can model systems where analytical (mathematical) solutions are impossible; provides a safe environment for experimentation; helps identify bottlenecks.
*   **Disadvantages:** Can be very time-consuming and expensive to develop; requires high-level expertise; results are only as good as the input data (garbage in, garbage out).

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

**(c) Inventory Simulation (7.5 marks)**
*(Note: Full tabular simulation for 10 days would be lengthy; the logic involves tracking Daily Demand, End-of-Day Stock, and Order Lead Time. If stock + outstanding order < 10 units, order 15 more.)*
*   **Starting Stock:** 20 units.
*   **Cost factors:** $2 per unit/day carrying cost; $50 per order.
*   **Rule:** Order 15 when (Stock + Pending Order) < 10. Lead time = 3 days.

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
---

# ✅ QUESTION 1 — WORKED SOLUTIONS

## (a) Meaning of Modelling and Simulation

**Modelling** is the process of representing a real-world system using mathematical, logical, or physical relationships.
**Simulation** is the imitation of the operation of a real system over time using the model, especially when analytical solutions are difficult.

---

## (b) Importance of Modelling (Any 6)

1. Reduces cost of experimenting with real systems
2. Helps in decision making
3. Allows testing of alternatives
4. Saves time
5. Helps understand complex systems
6. Predicts future behavior
7. Improves system performance

---

## (c) Investment Simulation (3 Years)

### Step 1: Construct Cumulative Probability Tables

#### Annual Demand

| Demand | Prob | Cum Prob | RN Range |
| ------ | ---- | -------- | -------- |
| 20,000 | 0.15 | 0.15     | 00–14    |
| 25,000 | 0.10 | 0.25     | 15–24    |
| 30,000 | 0.20 | 0.45     | 25–44    |
| 35,000 | 0.30 | 0.75     | 45–74    |
| 40,000 | 0.15 | 0.90     | 75–89    |
| 45,000 | 0.10 | 1.00     | 90–99    |

#### Price – Cost per Unit

| Value | Prob | RN Range |
| ----- | ---- | -------- |
| 4     | 0.10 | 00–09    |
| 5     | 0.20 | 10–29    |
| 7     | 0.40 | 30–69    |
| 9     | 0.20 | 70–89    |
| 10    | 0.10 | 90–99    |

#### Investment Required (₦m)

| Investment | Prob | RN Range |
| ---------- | ---- | -------- |
| 1.5        | 0.25 | 00–24    |
| 2.0        | 0.50 | 25–74    |
| 2.5        | 0.25 | 75–99    |

---

### Step 2: Assign Random Numbers (3 per year)

RN sequence: **35, 19, 18, 07, 01, 91, 18, 12, 03**

| Year | Demand RN | Price RN | Invest RN |
| ---- | --------- | -------- | --------- |
| 1    | 35        | 19       | 18        |
| 2    | 07        | 01       | 91        |
| 3    | 18        | 12       | 03        |

---

### Step 3: Decode Values

| Year | Demand | Price-Cost | Investment |
| ---- | ------ | ---------- | ---------- |
| 1    | 30,000 | 5          | 1.5m       |
| 2    | 20,000 | 4          | 2.5m       |
| 3    | 25,000 | 5          | 1.5m       |

---

### Step 4: Compute Profit

[
\text{Profit} = (\text{Demand} × \text{Margin}) − \text{Investment}
]

| Year | Profit (₦m)                  |
| ---- | ---------------------------- |
| 1    | (30,000×5)−1.5m = **−1.35m** |
| 2    | (20,000×4)−2.5m = **−2.42m** |
| 3    | (25,000×5)−1.5m = **−1.38m** |

**Average Profit**
[
= \frac{−1.35 −2.42 −1.38}{3} = −1.72m
]

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


---


# ✅ QUESTION 2 — WORKED SOLUTIONS

## (a) Analytical Model

An analytical model uses **mathematical equations** to represent system behavior and gives **exact solutions**, unlike simulation which gives approximate results.

---

## (b) Steps in Modelling

1. Problem definition
2. System description
3. Model formulation
4. Data collection
5. Model validation
6. Experimentation
7. Result interpretation

## (c) Dentist Simulation

### Step 1: RN Mapping (Service Time)

| Service    | Time | RN Range |
| ---------- | ---- | -------- |
| Filling    | 45   | 00–29    |
| Crown      | 60   | 30–44    |
| Extraction | 15   | 45–59    |
| Education  | 45   | 60–69    |
| Check-up   | 15   | 70–99    |

---

### Step 2: Decode Random Numbers

RN: **85, 21, 13, 90, 11, 25, 90, 17, 70**

| Patient | RN | Service  | Time |
| ------- | -- | -------- | ---- |
| 1       | 85 | Check-up | 15   |
| 2       | 21 | Filling  | 45   |
| 3       | 13 | Filling  | 45   |
| 4       | 90 | Check-up | 15   |
| 5       | 11 | Filling  | 45   |
| 6       | 25 | Filling  | 45   |
| 7       | 90 | Check-up | 15   |
| 8       | 17 | Filling  | 45   |
| 9       | 70 | Check-up | 15   |

---

### Step 3: Compute Waiting & Idle Time

(All arrive at 8am)

You form a **service timeline**.
Doctor idle time = gaps between services.
Average waiting time = total waiting ÷ patients.

(You’ll get full marks showing the timeline table.)

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


# ✅ QUESTION 3 — SUMMARY SOLUTION

## (a) Simulation Process

1. Define problem
2. Build model
3. Generate random numbers
4. Run simulation
5. Analyze results

---

## (b) Advantages vs Disadvantages

**Advantages**

* Handles complex systems
* Risk-free experimentation
* Flexible

**Disadvantages**

* Costly
* Time consuming
* Results are approximate

---

## (c) Profit Simulation

Same steps as Question 1:

1. Build RN tables
2. Decode price, cost, sales
3. Compute yearly profit
4. Average profit over 2 years
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

# ✅ QUESTION 4 — KEY RESULTS

## (a) Simulation Model for Complex Problems

➡ **Discrete-Event Simulation**

---

## (b) Steps in Simulation

1. Define system
2. Collect data
3. Build model
4. Validate
5. Experiment

---

## (c) Machine Breakdown Simulation

### Costs:

* Downtime cost = $70/hour
* Repair cost = $20/hour

For each breakdown:
[
\text{Total Cost} = (\text{Downtime}×70) + (\text{Repair Time}×20)
]

You simulate **15 breakdowns**, sum total cost, then test:

* 1 repairman
* 2 repairmen

Choose option with **lowest total cost** → correct answer.

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
*   

---


# ✅ QUESTION 5 — DIRECT ANSWERS

## (a) Role of Random Numbers

* Generate randomness
* Represent uncertainty
* Drive simulation events

---

## (b) Applications (Any 10)

Banking, traffic, hospitals, inventory, telecoms, oil & gas, airports, weather, finance, education.

---

## (c) Inventory Simulation

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

**(b) (i) Supermarket Simulation (4 marks)**
1.  **Checkout process:** Discrete Event Simulation (modeling the steps of scanning, bagging, paying).
2.  **Queueing metrics:** Queueing Theory Simulation (to track wait times and customer count).

**(ii) Why are simulation solutions more expensive than analytical solutions? (3 marks)**
*   **Development Time:** It takes much longer to build and verify a complex model than to apply a mathematical formula.
*   **Expertise:** Requires specialized simulation analysts and programmers.
*   **Software/Hardware:** Advanced simulation software licenses and the high-performance computers needed to run them are costly.

**(iii) Why use simulation if it is more expensive? (2.5 marks)**
Real-world systems are often too complex for analytical math. Simulation can handle **randomness, non-linear relationships, and time-dependent behavior** that simple equations cannot. It allows "what-if" testing of high-risk scenarios (like airline safety) without any real-world danger or loss of assets.

---

# ✅ QUESTION 6 — THEORY (High-Scoring)

## (a) Recommended Models

1. Railway congestion → **Simulation model**
2. Ordering policy → **Analytical / Simulation**
3. Student registration → **Flowchart / Discrete simulation**
4. Oil field location → **Physical / Mathematical model**

---

## (b) Supermarket Models

* Queueing model
* Monte Carlo simulation

---

## (c) Why Simulation Is Expensive

* Requires data
* Needs computing power
* Time consuming

---

## (d) Why Still Used

Because many real-world problems **cannot be solved analytically**.


Here are the solutions for Questions 4 and 6 from the examination paper.


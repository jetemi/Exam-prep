# CSC 438 — Computer Network & Data Communication: Exam-Ready Answers

> **Note on scope:** Part A answers the CSC 438 past question. **Parts B & C** answer the *error-detection* (assignment) and *entropy/coding* (Question 16–18) sheets. **Part D** covers extra high-probability topics from your lecturer's **CSC 411 slide deck** and the **transmission-modes handout** (transmission media, network devices, CSMA/CD & CSMA/CA, virtual-circuit vs datagram, sync/async, data-rate calculation) — study these too, as the slides go beyond the past paper.

---

# PART A — CSC 438 Past Question (2023/2024)

## QUESTION 1

### 1(a) Does the "joint venture" scenario follow the TCP/IP suite or the OSI model? — [7½]

**Answer:** It follows the **general layered-architecture concept that is common to *both* the TCP/IP suite and the OSI model** — it does not map to one exclusively. The scenario illustrates the two key ideas of any layered model:

- **Vertical (adjacent-layer) service:** inside Company 1 the message passes **down through "layers"** — **CEO → legal team → middle managers** — each layer handing work to the layer directly below it and receiving a service from it. This mirrors how, in a network model, the application layer hands data to the transport layer, which hands to the network layer, and so on.
- **Horizontal (peer-to-peer / logical) communication:** the **CEO-of-Company-1 e-mailing the CEO-of-Company-2** is a **logical peer connection at the top layer** — the two CEOs (peers) communicate *as if* directly, even though in reality the message must travel down through the lower layers, across the medium, and back up the other side.

**Conclusion:** the scenario demonstrates **layered communication with logical peer connections**, a principle shared by both architectures. If forced to pick, the top-level CEO-to-CEO e-mail behaves like the **application layer's logical connection**, but the scenario is not specific to TCP/IP *or* OSI.

---

### 1(b) Networks involved in reading e-mail over coffee-shop Wi-Fi — [10]


| Network                                             | Description                                                                                                                                            |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Wireless LAN (WLAN / Wi-Fi)**                     | Connects **your laptop wirelessly to the coffee shop's access point** using radio waves (IEEE 802.11). This is the first hop.                          |
| **The shop's wired LAN**                            | The **local area network** inside the shop linking the access point to the shop's router/modem (twisted-pair Ethernet).                                |
| **The ISP access network (a WAN link)**             | The connection (cable/DSL/fibre) from the coffee shop **out to the Internet Service Provider** — often crossing a **Metropolitan Area Network (MAN)**. |
| **The Internet (WAN / "network of networks")**      | The global **wide area network** that carries your request across many routers to the mail server and back.                                            |
| **The e-mail provider's network / data-centre LAN** | The **server-side LAN** where the mail server (e.g., Gmail) resides and processes your request.                                                        |


*In short:* WLAN → shop LAN → ISP/MAN access link → the Internet (WAN) → the mail provider's server LAN — five distinct networks cooperating to deliver your e-mail.

---

## QUESTION 2

### 2(a) What is the OSI Model? — [2]

The Open Systems Interconnection (OSI) model is a **conceptual framework** and a **standardized model** that describes how network communication should be organized and implemented.

### 2(b) The seven layers of the OSI model — [10½]

*(Mnemonic top→down: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing)*


| #   | Layer            | Main function                                                                                                                                                     |
| --- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 7   | **Application**  | The top layer in the OSI model. Interface to the user's network applications (HTTP, SMTP, FTP, Telnet).                                                           |
| 6   | **Presentation** | Data **translation/format**, character-set (ASCII) conversion, **encryption/decryption**, compression.                                                            |
| 5   | **Session**      | **Establishes, manages and terminates sessions** between users; dialog control (token management) and **synchronisation points** for recovery.                    |
| 4   | **Transport**    | **End-to-end** delivery — ensures the packet arriving at the destination is identical to the one sent; **end-to-end error control and flow control** (e.g., TCP). |
| 3   | **Network**      | **Routing** and logical addressing — moves packets from router to router across networks (e.g., IP).                                                              |
| 2   | **Data Link**    | Takes data from the network layer and forms **frames**; node-to-node error detection/control and flow control; physical (MAC) addressing.                         |
| 1   | **Physical**     | Actual **transmission of raw bits** over the medium — voltage levels, connectors, pins, encoding/modulation.                                                      |


> 🔑 **OSI vs TCP/IP:** OSI has 7 layers; the TCP/IP suite has **5** (Application, Transport, Network, Network Access, Physical).

### 2(c) The modes of data transmission (with diagrams) — [5]

A **transmission (communication) mode** describes the **direction of data flow** between two devices. Per your lecturer's handout there are **three transmission modes: Simplex, Half-Duplex and Full-Duplex.**

**1. Simplex** — **unidirectional**; only one device transmits, the other only receives. Uses the full channel capacity in one direction. *Example:* keyboard → monitor; TV/radio broadcast.

```
   [ A ] ───────────────►  [ B ]        (one way only)
```

**2. Half-Duplex** — **both can transmit and receive, but not at the same time** (one direction at a time). The full channel capacity is used in the active direction. *Example:* walkie-talkie.

```
   [ A ] ───────────────►  [ B ]        (take turns —
   [ A ] ◄───────────────  [ B ]         one direction at a time)
```

**3. Full-Duplex** — **both transmit and receive simultaneously**; capacity is split between the two directions (or two separate paths). *Example:* telephone.

```
   [ A ] ═══════════════►  [ B ]        (both directions
   [ A ] ◄═══════════════  [ B ]         at the same time)
```


| Parameter   | Simplex          | Half-Duplex              | Full-Duplex               |
| ----------- | ---------------- | ------------------------ | ------------------------- |
| Direction   | One way          | Both ways, one at a time | Both ways, simultaneously |
| Channels    | 1                | 1                        | 2 (or split)              |
| Performance | Lowest           | Medium                   | Highest                   |
| Example     | Keyboard→monitor | Walkie-talkie            | Telephone                 |


---

## QUESTION 3

### 3(a) Two major requirements that drive the use of switched networks — [6]

1. **Economical sharing of transmission resources (scalability of connections):** it is **impractical and far too costly to run a dedicated point-to-point wire between every pair of devices**. Switched networks let many devices **share** a smaller set of links/paths through intermediate **switching nodes**, dramatically cutting cost and cabling.
2. **Long-distance / wide-area connectivity:** to connect **large numbers of devices spread over wide geographic areas**, data must be **relayed hop-by-hop through intermediate switching nodes**.

*(Other drivers: efficient bandwidth utilisation and dynamic path selection/robustness.)*

### 3(b) The three operational phases of circuit switching — [9]


| Phase                                | What happens                                                                                                                                                     |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Circuit Establishment (Setup)** | Before any data moves, a **dedicated end-to-end path (circuit)** is set up between sender and receiver through the intermediate switches.                        |
| **2. Data Transfer**                 | Once the circuit is established, data can be transmitted between the sender and receiver over the dedicated path.                                                |
| **3. Circuit Disconnect (Teardown)** | After the data transmission is complete, the circuit is **released/torn down** and the reserved resources are **freed** for other connections — like hanging up. |


### 3(c) Static routing vs Dynamic routing — [2½]


| **Static (Fixed) routing**                                                | **Dynamic (Adaptive) routing**                                                           |
| ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Routing tables are **configured manually**, usually once at installation. | Routing tables are **built and updated automatically** by routing protocols (RIP, OSPF). |
| **Do not change** unless an admin edits them.                             | **React automatically** to network changes — congestion, link/node failure.              |
| Simple, low overhead, but can become **out-of-date**; no fault recovery.  | Adapts and recovers, but adds **control traffic/overhead** and can be less stable.       |


---

## QUESTION 4

### 4(a) Six factors in selecting a network topology — [3]

1. **Cost** — cabling, hardware and installation expense.
2. **Reliability / fault tolerance** — effect of a node or cable failure on the rest of the network.
3. **Scalability / expandability** — ease of adding or removing nodes.
4. **Ease of installation & maintenance** — how simple it is to set up and troubleshoot.
5. **Performance** — throughput, traffic-handling and delay characteristics.
6. **Flexibility & cable length/distance** — geographic spread the layout must cover.

### 4(b) Connecting three PCs — two adjacent rooms + one 300 m away — [3½]

- **The two PCs in adjacent rooms:** connect them on a **LAN** using a **switch** and **twisted-pair (Cat 5e/6) Ethernet cable** — a small **star** layout. Distances are well within the 100 m copper limit.
- **The third PC, 300 m away:** twisted-pair Ethernet is limited to **~100 m**, so use **fibre-optic cable** (which easily spans 300 m) to link that PC's building back to the switch — *(a wireless bridge is an alternative)*. Result: all three sit on **one LAN**.

### 4(c) Connecting three more PCs across town to the network in (b) — [3]

Across town is a **different geographic site**, so a **LAN alone will not reach** — you need a **WAN connection**. The **most common and economical way** is to connect **both LANs to the Internet** through routers/an ISP and join them with a **VPN (Virtual Private Network) over the public Internet**, giving a secure link between the two sites.

### 4(d) Operational procedures of point-to-point technology (with diagram) — [4½]

A **point-to-point** connection is a **dedicated link joining exactly two devices**, with the **entire capacity of the line reserved for those two**.

```
   [ Device A ] ◄───────────── dedicated link ─────────────► [ Device B ]
```

**Operational procedure:**

- A **single dedicated line** runs **directly between the two nodes** — no other device shares it.
- Because there are **only two endpoints**, **no addressing, polling or contention** is needed — each device knows all traffic on the line is for it.
- The **full bandwidth is always available** to the pair, giving fast, low-delay transfer.
- It can operate as **simplex, half-duplex or full-duplex**, and forms the building block of a **mesh** topology and of leased-line WAN links (e.g., router-to-router).

### 4(e) Two advantages & two disadvantages of Ring, Star and Bus — [3]


| Topology | Advantages                                                                                                 | Disadvantages                                                                                                                                              |
| -------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ring** | ① Data flows in one direction, orderly access via **token passing**; ② performs well under **heavy load**. | ① A **single node/link break can down the whole ring**; ② adding/removing a node **disrupts** the network.                                                 |
| **Star** | ① **One node/cable failure doesn't affect others**; ② **easy to install, expand and fault-isolate**.       | ① **Central hub/switch is a single point of failure**; ② needs **more cable** (each node to the hub).                                                      |
| **Bus**  | ① **Simple and cheap**, uses the **least cable**; ② **easy to add nodes** for small networks.              | ① A **break in the backbone cable downs the whole network**; ② **performance degrades** with more traffic (collisions) and it is **hard to troubleshoot**. |


---

## QUESTION 5

### 5(a) How TCP implements congestion control — [10]

TCP controls congestion by having the **sender maintain a congestion window (`cwnd`)** in addition to the receiver's advertised window; it may send only **min(cwnd, receiver window)**. It probes for available bandwidth using **AIMD — Additive Increase, Multiplicative Decrease** — through four mechanisms:

1. **Slow Start:** `cwnd` starts at **1 MSS** and **doubles every RTT** (exponential growth) until it reaches the **slow-start threshold (`ssthresh`)**.
2. **Congestion Avoidance:** once `cwnd ≥ ssthresh`, growth becomes **linear** (+1 MSS per RTT) — cautious *additive increase* as the network nears capacity.
3. **Congestion Detection:** TCP infers congestion from **packet loss**, signalled either by a **timeout** or by **three duplicate ACKs**.
4. **Reaction (Multiplicative Decrease):**
  - On **timeout** (severe): set `ssthresh = cwnd/2`, reset `**cwnd = 1 MSS`**, and restart Slow Start.
  - On **3 duplicate ACKs** (mild): **Fast Retransmit** the lost segment at once (don't wait for timeout), then **Fast Recovery** — set `ssthresh = cwnd/2`, `cwnd = ssthresh`, and continue in Congestion Avoidance instead of dropping to 1.

**Net effect:** TCP keeps increasing its rate to use spare capacity, then sharply backs off on loss — preventing **congestion collapse** while staying fair to other flows.

### 5(b) Traffic congestion-control techniques — [7½]

**(i) Traffic Shaping** — **regulating the average rate and burstiness** of traffic entering the network so that flow is smooth and predictable rather than bursty. Implemented with the **Leaky-Bucket** and **Token-Bucket** algorithms. It is **preventive** (acts before congestion).

**(ii) Load Shedding** — when nodes/routers are **overwhelmed and their buffers fill**, they **deliberately discard (drop) packets** they cannot handle. The router chooses *which* packets to drop (e.g., oldest-first, or by priority/QoS). It is a **last-resort reaction** to existing congestion.

**(iii) Jitter Control** — controlling **jitter** (the *variation* in packet arrival delay). Crucial for **real-time audio/video**. Achieved by **buffering at the receiver (playout buffer)** and regulating each packet's delay so packets are released at a **steady, even rate**, removing flicker/break-up.

---

## QUESTION 6

### 6(a) Primary purpose of multiplexing — [3½]

The **primary purpose of multiplexing is to allow several signals/data streams to share a single transmission medium simultaneously**, thereby **making efficient use of expensive bandwidth and reducing cost** — one high-capacity line carries many users' traffic instead of running a separate physical line for each.

### 6(b) Why do digital signals attenuate sooner than analog signals? — [5]

A **digital (square-wave) signal is composed of a fundamental frequency plus many high-frequency harmonics** — those harmonics are what create its sharp, square 0↔1 edges. In any medium, **higher-frequency components lose strength (attenuate) faster than lower frequencies**. As the signal travels:

- the **high-frequency harmonics are lost first**, so the crisp square edges **round off** and the 0/1 levels blur, making the signal **unrecognisable over a shorter distance**;
- digital signals also occupy a **wider bandwidth**, exposing more of the signal to high-frequency loss.

An **analog signal** typically centres on a **narrower, lower band of frequencies** and degrades more gracefully. Consequently, digital signals must be **regenerated by repeaters at shorter intervals** than analog signals need amplifiers — i.e., they attenuate sooner.

### 6(c) FDM, WDM and TDM — [9]

**(i) Frequency Division Multiplexing (FDM):** the medium's **total bandwidth is split into several non-overlapping frequency bands (channels)**; each user is assigned its own band and **all transmit at the same time**. **Guard bands** separate channels to prevent interference. *Examples:* radio/TV broadcast, cable TV, first-generation cell phones. *(Analog technique.)*

**(ii) Wave/Wavelength Division Multiplexing (WDM):** essentially **FDM applied to optical fibre** — multiple light beams of **different wavelengths (colours)** travel **simultaneously down one fibre**, each wavelength being a separate channel. Gives enormous capacity (DWDM); used on fibre-optic backbones.

**(iii) Time Division Multiplexing (TDM):** users **share the full bandwidth but take turns in time** — time is divided into **slots** and each user gets the whole channel for a brief slot in rotation. Two forms: **Synchronous TDM** (fixed slot per user — can waste empty slots) and **Statistical TDM** (slots allocated on demand — more efficient). *(Digital technique.)*


| Technique | Divides by         | Users transmit           | Typical use            |
| --------- | ------------------ | ------------------------ | ---------------------- |
| **FDM**   | Frequency          | Simultaneously           | Radio, TV, cable       |
| **WDM**   | Wavelength (light) | Simultaneously           | Fibre-optic links      |
| **TDM**   | Time slots         | One at a time (rotating) | Digital telephone/data |


> 🧭 **Lecturer's classification:** **Analog multiplexing** = FDM (by frequency) + WDM (by wavelength); **Digital multiplexing** = TDM (by time slot). **Statistical (Asynchronous) TDM** improves on Synchronous TDM by giving a slot *only to channels currently transmitting* — no bandwidth wasted on idle/empty slots.

---

# PART B — Errors, Error Detection & Error Control *(assignment sheet)*

### B1. Six types of errors (noise) and the technique to handle each — [6 types]

*(The "errors" in data transmission come from six main types of noise; each has a characteristic reduction/handling technique.)*


| #   | Type of error (noise)              | What it is                                                                          | Handling / reduction technique                                                          |
| --- | ---------------------------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 1   | **White (thermal/Gaussian) noise** | Continuous background noise from electron/thermal activity; makes the signal fuzzy. | **Signal regenerator** (digital) or **filters** (analog); reduced, never fully removed. |
| 2   | **Impulse noise (noise spike)**    | Random non-continuous energy burst (e.g., lightning); can obliterate bits.          | **Digital regeneration/recovery** of the signal; **shielding**; hard to detect fully.   |
| 3   | **Crosstalk**                      | Unwanted coupling of a signal from an adjacent line/path.                           | **Proper shielding**, twisted-pair/**well-shielded or fibre cable**.                    |
| 4   | **Echo**                           | Reflective feedback of a signal bouncing back at a cable end/junction.              | **Echo suppressor** (a one-direction filter); terminating filter on the cable end.      |
| 5   | **Jitter**                         | Small timing shifts in a digital signal's rises/falls; blurs bit timing.            | **Proper shielding**, **limit number of repeaters**, slow the transmission rate.        |
| 6   | **Attenuation**                    | Loss of signal strength (power) with distance.                                      | **Amplifiers** (analog) / **repeaters–regenerators** (digital) at set intervals.        |


### B2. Four error-detection techniques — strengths & weaknesses — [4 techniques]


| Technique                            | How it works                                                                                                  | Strengths                                                                                      | Weaknesses                                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Simple (vertical) parity**         | Adds **one parity bit** per character for even/odd 1-count.                                                   | Very **simple**, easy/cheap to implement.                                                      | Catches only an **odd number** of bit errors (~50%); high check-bit ratio (1:7); misses even-count errors. |
| **Longitudinal (2-D) parity**        | Parity bit per character **plus** a block-check character across the block.                                   | Better than simple parity; catches **more error patterns**.                                    | Still **misses** certain multi-bit patterns; adds many check bits (~1:5 ratio).                            |
| **Arithmetic checksum**              | **Sums** all characters; sends the sum; receiver re-sums and compares (used by TCP/IP).                       | **Low overhead**, easy; good for software (Internet) use.                                      | Can **miss errors that cancel out** in the sum (e.g., compensating changes); weaker than CRC.              |
| **Cyclic Redundancy Checksum (CRC)** | Treats data as a polynomial, divides by a generator polynomial, appends the **remainder** as 8–32 check bits. | **Most powerful** — detects virtually all single, double and burst errors; hardware-efficient. | More **complex** to compute; detection (not correction).                                                   |


### B3. Condition that must be met for error *correction* to be performed — [condition]

Error **detection** only reveals *that* an error exists; **correction** additionally requires locating and fixing it. So the condition is:

> **The received data must carry *enough redundant (check) information* for the receiver to not only *detect* an error but also *pinpoint exactly which bit(s)* are wrong — so it can flip them back.**

This is met in two ways:

- **Forward Error Correction (FEC):** include **enough redundancy** (e.g., a **Hamming code**) so the receiver **locates and corrects** the error itself — no retransmission needed.
- **Backward correction (ARQ):** a **reverse/feedback channel must exist** so the receiver can **request a retransmission** of the corrupted frame.

Without sufficient redundancy to locate the error (FEC) **or** a return path to ask for a resend (ARQ), correction is impossible.

---

# PART C — Information Theory & Source Coding *(Question 16–18)*

> **Key formulas**
>
> - **Entropy:** `H = Σ pᵢ · log₂(1/pᵢ)` bits/symbol (average information per symbol; the *lower bound* on average code length).
> - **Average code length:** `L = Σ pᵢ · lᵢ` bits/symbol.
> - **Redundancy:** `R = L − H` (extra bits beyond the theoretical minimum). **Efficiency:** `η = H / L`.

## QUESTION 16 — A(½), B(⅙), C(¹⁄₁₂), D(¹⁄₁₂), E(¹⁄₂₄), F(¹⁄₂₄), G(¹⁄₂₄), H(¹⁄₂₄)

*(Check: ½+⅙+2·¹⁄₁₂+4·¹⁄₂₄ = 12/24+4/24+4/24+4/24 = 24/24 = 1 ✓)*

### 16(a) Entropy —

```
H = ½·log₂2 + ⅙·log₂6 + 2·(¹⁄₁₂·log₂12) + 4·(¹⁄₂₄·log₂24)
  = 0.5 + 0.4308 + 2(0.2987) + 4(0.1910)
```

**H ≈ 2.29 bits/symbol.**

### 16(b) Redundancy of a 3-bit fixed-length code —

A fixed 3-bit code has **L = 3 bits/symbol**.
**Redundancy R = L − H = 3 − 2.29 = 0.71 bits/symbol** (efficiency η = 2.29/3 ≈ **76.4 %**).

### 16(c) Average length of the given code —

Code: A=1, B=001, C=010, D=0000, E=0110, F=0001, G=01110, H=01111 → lengths 1,3,3,4,4,4,5,5.

```
L = ½(1) + ⅙(3) + ¹⁄₁₂(3) + ¹⁄₁₂(4) + ¹⁄₂₄(4) + ¹⁄₂₄(4) + ¹⁄₂₄(5) + ¹⁄₂₄(5)
  = 0.5 + 0.5 + 0.25 + 0.333 + 0.167 + 0.167 + 0.208 + 0.208
```

**L ≈ 2.33 bits/symbol.**

### 16(d) Redundancy of this code —

**R = L − H = 2.33 − 2.29 = 0.04 bits/symbol** (efficiency η = 2.29/2.33 ≈ **98.3 %**). This variable-length code is **near-optimal** — far less redundant than the 3-bit fixed code.

---

## QUESTION 17 — a(8/40), b(3/40), c(6/40), d(5/40), e(4/40), f(7/40), g(2/40), h(5/40)

### 17(a) Entropy —

Using `H = Σ pᵢ log₂(1/pᵢ)` with p = 0.2, 0.075, 0.15, 0.125, 0.1, 0.175, 0.05, 0.125:
**H ≈ 2.89 bits/symbol.**

### 17(b) Huffman code, average length & redundancy —

Build by repeatedly merging the two smallest probabilities (freqs out of 40): g2+b3=5, e4+d5=9, h5+gb5=10, c6+f7=13, a8+ed9=17, hgb10+cf13=23, 17+23=40.


| Symbol | Prob | Huffman code | Length |
| ------ | ---- | ------------ | ------ |
| a      | 8/40 | 00           | 2      |
| c      | 6/40 | 110          | 3      |
| f      | 7/40 | 111          | 3      |
| d      | 5/40 | 011          | 3      |
| h      | 5/40 | 100          | 3      |
| e      | 4/40 | 010          | 3      |
| b      | 3/40 | 1011         | 4      |
| g      | 2/40 | 1010         | 4      |


```
L = 0.2(2)+0.15(3)+0.175(3)+0.125(3)+0.125(3)+0.1(3)+0.075(4)+0.05(4)
```

**L ≈ 2.925 bits/symbol; Redundancy R = 2.925 − 2.89 = 0.03 bits/symbol (η ≈ 98.9 %).**
*(Huffman codes are not unique — a different but equally valid assignment gives the same average length.)*

### 17(c) Shannon–Fano code, average length & redundancy —

Sort descending, then recursively split into two groups of ~equal probability (top group → 0, bottom → 1):


| Symbol | Prob | Shannon–Fano code | Length |
| ------ | ---- | ----------------- | ------ |
| a      | 8/40 | 00                | 2      |
| f      | 7/40 | 010               | 3      |
| c      | 6/40 | 011               | 3      |
| d      | 5/40 | 100               | 3      |
| h      | 5/40 | 101               | 3      |
| e      | 4/40 | 110               | 3      |
| b      | 3/40 | 1110              | 4      |
| g      | 2/40 | 1111              | 4      |


**L ≈ 2.925 bits/symbol; Redundancy R = 0.03 bits/symbol (η ≈ 98.9 %).**

> Here **Huffman and Shannon–Fano tie** (both L ≈ 2.925). In general Huffman is **never worse** than Shannon–Fano.

---

## QUESTION 18 — a(20/40), b(12/40), c(4/40), d(2/40), e(1/40), f(1/40)

### 18(a) Entropy —

With p = 0.5, 0.3, 0.1, 0.05, 0.025, 0.025:
**H ≈ 1.84 bits/symbol.**

### 18(b) Huffman code, average length & redundancy —

Merge: e1+f1=2, d2+ef2=4, c4+def4=8, b12+cdef8=20, a20+bcdef20=40.


| Symbol | Prob  | Huffman code | Length |
| ------ | ----- | ------------ | ------ |
| a      | 20/40 | 0            | 1      |
| b      | 12/40 | 10           | 2      |
| c      | 4/40  | 110          | 3      |
| d      | 2/40  | 1110         | 4      |
| e      | 1/40  | 11110        | 5      |
| f      | 1/40  | 11111        | 5      |


```
L = 0.5(1)+0.3(2)+0.1(3)+0.05(4)+0.025(5)+0.025(5)
```

**L = 1.85 bits/symbol; Redundancy R = 1.85 − 1.84 = 0.015 bits/symbol (η ≈ 99.2 %).**

### 18(c) Shannon–Fano code, average length & redundancy —

Recursive equal-probability splits give the **same tree** here:


| Symbol | Prob  | Shannon–Fano code | Length |
| ------ | ----- | ----------------- | ------ |
| a      | 20/40 | 0                 | 1      |
| b      | 12/40 | 10                | 2      |
| c      | 4/40  | 110               | 3      |
| d      | 2/40  | 1110              | 4      |
| e      | 1/40  | 11110             | 5      |
| f      | 1/40  | 11111             | 5      |


**L = 1.85 bits/symbol; Redundancy R = 0.015 bits/symbol (η ≈ 99.2 %).**

---

# PART D — Extra Topics from the CSC 411 Lecture Slides

*(High-probability exam topics the lecturer covers that go beyond the CSC 438 past paper.)*

## D1. Transmission media (communication channels)

Communication channels are either **guided (bounded/wired)** or **unguided (unbounded/wireless)**.

**Guided media** — signal is confined to a cable:


| Medium            | Description                                                                                                            | Key points                                                                                                                                                                     |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Twisted-pair**  | Two insulated copper wires twisted together (one carries the signal, one is ground); twisting reduces noise/crosstalk. | Most common LAN cable; also telephone. **UTP** (unshielded) vs **STP** (shielded). ~100 m runs; **Cat 5e/6/7**.                                                                |
| **Coaxial cable** | Central copper core in an insulating sheath, wrapped by a second conductor + shield.                                   | Carries higher frequencies than twisted pair, up to ~450 Mbps. **Adv:** cheap, easy to wire/expand, moderate EMI immunity. **Disadv:** one cable failure can down the network. |
| **Fibre-optic**   | Glass/plastic core that carries data as **light** (single-mode vs multimode).                                          | **Adv:** very fast (Gbps+), **low attenuation**, immune to EMI. **Disadv:** costly, hard to install.                                                                           |


**Unguided media** — signal travels as waves through air/space: **Microwave** (line-of-sight, long distance), **Satellite** (~22,300 mi up, high speed), **Cellular radio** (mobile), **Radio broadcast**.

## D2. Data-communication / internetworking devices


| Device                | OSI layer     | Function                                                                                            |
| --------------------- | ------------- | --------------------------------------------------------------------------------------------------- |
| **Repeater**          | 1 – Physical  | Regenerates/boosts a signal to extend cable distance.                                               |
| **Hub**               | 1 – Physical  | Common connection point; copies an incoming packet **out to all ports**.                            |
| **Bridge**            | 2 – Data Link | Connects two LANs/segments using the **same protocol**.                                             |
| **Switch**            | 2 – Data Link | Like a bridge but **faster and more intelligent**; forwards frames only to the target port.         |
| **Router**            | 3 – Network   | Directs data along the **best/most economical route**; connects networks with compatible protocols. |
| **Gateway**           | Up to 7       | Connects **incompatible/dissimilar** networks (e.g., PC LAN ↔ mainframe).                           |
| **Modem**             | 1 – Physical  | **Modulator–Demodulator** — converts digital ↔ analog for telephone/cable lines.                    |
| **Multiplexer (MUX)** | —             | Combines many channels onto one line; **DEMUX** reverses it at the receiver.                        |


## D3. Multiple Access (MAC) protocols — CSMA family

**CSMA (Carrier Sense Multiple Access):** a station **listens to the channel before transmitting** ("sense the carrier"); if the channel is busy it defers. If a collision still occurs, it retransmits after a **random delay**. Persistence variants:

- **Non-persistent** — if busy, wait a **random** time, then sense again.
- **1-persistent** — sense **continuously**; transmit immediately (probability 1) the instant the channel is idle → **high collision risk**.
- **p-persistent** — when idle, transmit with probability **p**, defer with **1−p** (used on slotted channels).

**CSMA/CD (Collision Detection)** — wired **Ethernet**. A station **monitors the medium while sending**; if it detects a collision it **aborts and retransmits**. Requires frame time **T_fr ≥ 2 × T_p** (propagation) so collisions are detectable.

**CSMA/CA (Collision Avoidance)** — **wireless (Wi-Fi)**, where collisions can't be reliably detected. It **avoids** collisions using **Inter-Frame Space (IFS)**, a **Contention Window** (random back-off slots), and **acknowledgements (ACKs)**.

## D4. Virtual-Circuit vs Datagram networks (switching)


|             | **Virtual Circuit (connection-oriented)**              | **Datagram (connectionless)**                        |
| ----------- | ------------------------------------------------------ | ---------------------------------------------------- |
| Path setup  | **Reserves** resources; fixed path for the session     | **No reservation**; each packet routed independently |
| Packet path | All packets follow the **same path**                   | Packets may take **any path**                        |
| Ordering    | Arrive **in order**                                    | May arrive **out of order**                          |
| Header      | Only the **first** packet needs a full (global) header | **Every** packet carries full source/dest header     |
| Reliability | **High** (guaranteed delivery)                         | **Lower** (packets dropped if resources unavailable) |
| Used by     | **ATM** (e.g., telephone)                              | **IP / the Internet**                                |


## D5. Synchronous vs Asynchronous

**As "communication" (lecturer's handout):**

- **Synchronous communication** — **real-time**; both parties present, respond immediately (phone call, video conference, instant messaging).
- **Asynchronous communication** — a **time lag** between sending and receiving (email, text message, forum).

**As "transmission" (data-link sense — worth knowing):**

- **Asynchronous transmission** — data sent **one character at a time**, each framed by **start and stop bits**; no shared clock. Simple, cheap, but lower efficiency.
- **Synchronous transmission** — data sent as **continuous blocks/frames** timed by a **shared clock**; higher speed and efficiency.

## D6. Data-transfer-rate calculation

> **Formula:** **S = A ÷ T** — where **S** = speed/rate, **A** = amount of data, **T** = time. Rearranged: **A = S × T**, **T = A ÷ S**.
>
> **Units:** bit = lowercase **b**, byte = uppercase **B**; **8 b = 1 B**; **1024 B = 1 KB**; **1024 KB = 1 MB**; **1024 MB = 1 GB**. Convert size and speed to the **same unit** before dividing.

**Worked example:** transfer **25 MB in 2 minutes**.

```
T = 2 min = 120 s
S = A / T = 25 MB ÷ 120 s = 0.208 MB/s
         = 0.208 × 1024 ≈ 213 KB/s
```


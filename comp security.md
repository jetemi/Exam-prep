# CSC 420 — Introduction to Computer Security: Exam-Ready Answers

> **Rubric reminder:** Answer **THREE** questions; **Question 1 is compulsory.** All questions are answered below so you can pick your best three. Marks per part are shown in brackets.

---

## QUESTION 1 *(Compulsory)*

### 1(a) Define the following terms — [8 marks]

**(i) Computer security** — the discipline (also called IT security or information security) of **protecting computer systems, networks, programs and data from unauthorized access, misuse, alteration, disclosure, destruction or damage**. Its core aim is to preserve the **CIA triad**: **C**onfidentiality, **I**ntegrity and **A**vailability of information.

**(ii) Passwordless authentication** — an authentication method that **verifies a user's identity without requiring them to type a password**. Instead it uses an alternative factor such as a **biometric** (fingerprint, face), a **security key/hardware token**, a **push notification** to a trusted device, or a **magic link / one-time code** sent by email or SMS. It removes the risks tied to passwords (theft, reuse, phishing, weak/guessable passwords).

> 💡 Passwordless ≠ MFA. Passwordless *replaces* the password; MFA *adds* extra factors. A system can be both (e.g., fingerprint + security key).

---

### 1(b) Primary purpose of key distribution in a cryptographic system — [4 marks]

The **primary purpose of key distribution is to securely deliver/share the cryptographic keys** to the legitimate communicating parties so that they can encrypt and decrypt messages, **without the keys being exposed to an attacker**.

- In **symmetric** cryptography both parties must hold the **same secret key**, so key distribution solves the **"key distribution problem"** — getting that shared secret to both sides over a possibly insecure channel (via pre-shared keys or a key-exchange protocol like Diffie–Hellman).
- In **asymmetric** cryptography it distributes **public keys reliably** and binds each public key to its true owner (via PKI/certificates) so no one can substitute a fake key.

**In one line:** key distribution ensures the *right keys* reach the *right parties* while staying secret from everyone else — without it, encryption cannot even begin.

---

### 1(c) "Least privilege": definition and implementation in Windows — [3 + 5 marks]

**Definition (3):** The **Principle of Least Privilege (PoLP)** states that every user, process or program should be granted **only the minimum access rights and permissions needed to perform its legitimate task — and no more.** This limits the damage from mistakes, malware or compromised accounts.

In Windows:

- Users should not be given administrator access unless necessary.
- Use of User Account Control (UAC) helps limit the execution of tasks that require admin privileges.
- Folder and file permissions should be set so that users can only access resources relevant to their role.
- Software installation rights can be restricted using Group Policies.  
This minimizes the damage if an account or system is compromised.

**How it is implemented in a Windows OS environment (5):**


| Mechanism                              | How it enforces least privilege                                                                                                                                        |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Standard (non-admin) user accounts** | Users do day-to-day work as a **Standard user**, not Administrator, so malware runs with limited rights.                                                               |
| **User Account Control (UAC)**         | Even admins run with a *standard* token; the elevation prompt ("Run as administrator") grants admin rights only per-task, on demand.                                   |
| **NTFS permissions & ACLs**            | Each file/folder has a **security descriptor** with an **Access Control List (ACL)** granting specific rights (Read, Write, Modify, Execute) to specific users/groups. |
| **Security groups / RBAC**             | Users are placed in groups (e.g., *Users*, *Power Users*); permissions are assigned to the **group/role**, giving each role only what its job needs.                   |
| **Group Policy (GPO)**                 | Administrators centrally restrict rights, software installation and system settings across the domain.                                                                 |


---

### 1(d) Compare & contrast symmetric and asymmetric encryption (+ one example each) — [4 + 4 + 2 marks]


| Aspect               | **Symmetric (Private-key)**                                              | **Asymmetric (Public-key)**                                               |
| -------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| **Keys used**        | **One** shared secret key for both encryption and decryption             | **A pair** — public key encrypts, private key decrypts (kept secret)      |
| **Speed**            | **Fast**, efficient — good for bulk/large data                           | **Slower** — computationally heavy                                        |
| **Key distribution** | **Hard** — the secret must be shared securely (key-distribution problem) | **Easy** — public key can be shared openly                                |
| **Scalability**      | Poor: *n(n−1)/2* keys for *n* users                                      | Better: each user needs just one key pair                                 |
| **Main services**    | Confidentiality                                                          | Confidentiality **+** digital signatures, authentication, non-repudiation |
| **Weakness**         | If the key leaks, all traffic is exposed                                 | Slow; needs PKI to trust public keys                                      |
| **Example**          | **AES** (also DES, 3DES)                                                 | **RSA** (also ECC, Diffie–Hellman)                                        |


**Similarity (contrast note):** both convert plaintext ↔ ciphertext using keys to provide confidentiality. **Key difference:** symmetric uses *the same* secret key on both ends; asymmetric uses a *mathematically linked pair*, solving key distribution at the cost of speed.

> 🔑 In practice they are combined as **hybrid cryptography** (e.g., SSL/TLS): RSA/ECC securely exchanges a symmetric key, then AES encrypts the bulk data.

---

## QUESTION 2

### 2(a) Man-in-the-middle (MITM) attack & its effect on authentication — [4 + 6 marks]

**What it is (4):** A **man-in-the-middle attack** is an attack in which an adversary **secretly positions themselves between two communicating parties, intercepting (and possibly altering or relaying) the messages** while each party believes they are communicating directly and securely with the other. The attacker can eavesdrop, modify, inject or replay traffic.

**How it affects authentication processes (6):**

- **Credential capture:** if login runs over an unencrypted/weak channel, the attacker reads **usernames, passwords, PINs or OTPs** in transit and later replays them.
- **Session hijacking:** the attacker steals **session tokens/cookies** issued after login and impersonates the authenticated user.
- **Impersonation / relay:** the attacker authenticates to the server *as the victim* and to the victim *as the server*, relaying challenges — defeating simple challenge–response.
- **Defeating unauthenticated key exchange:** plain **Diffie–Hellman** has no identity check, so the attacker establishes *two* separate keys (one with each side) and transparently decrypts everything.
- **Certificate/downgrade tricks:** presenting a **fake or self-signed certificate**, or forcing a **downgrade** to weaker protocols, tricks the victim into trusting the attacker.

**Countermeasures (bonus):** mutual authentication, **CA-signed certificates** and **TLS**, **authenticated** key exchange, HSTS, and MFA reduce MITM impact.

---

### 2(b) MFA vs SFA, and the security risks of SSO — [6 + 4 marks]

**How MFA enhances security over SFA (6):**

- **Single-Factor Authentication (SFA)** verifies identity with **one factor**, almost always **something you know** (a password). If that one secret is stolen, guessed or phished, the account is fully compromised.
- **Multi-Factor Authentication (MFA)** requires **two or more factors from *different* categories**:
  - **Something you know** — password/PIN
  - **Something you have** — phone, OTP token, security key
  - **Something you are** — fingerprint, face, iris
- MFA is stronger because an attacker must **defeat several independent factors at once**. A stolen password alone is useless without the second factor, sharply reducing account takeover, phishing and brute-force success.


|                    | SFA                 | MFA                                |
| ------------------ | ------------------- | ---------------------------------- |
| Factors            | 1                   | 2 or more (different types)        |
| If password stolen | Account compromised | Still protected by other factor(s) |
| Security level     | Low                 | High                               |


**Potential security risks of Single Sign-On (SSO) (4):**

- **Single point of failure / "keys to the kingdom":** if the SSO credentials are compromised, the attacker gains access to **all linked applications** at once.
- **Availability risk:** if the SSO/identity provider is **down**, users cannot reach *any* connected service.
- **Larger attack surface & high-value target:** the SSO provider becomes a prime target for phishing and attacks.
- **Weak-link propagation:** a session or token stolen at one point grants broad access across federated services.

> ✅ Best practice: **combine SSO with MFA** so a stolen SSO password alone is not enough.

---

## QUESTION 3

### 3(a) Symmetric vs asymmetric **key distribution** (+ advantage & disadvantage of each) — [2 + 4 + 4 marks]

**Compare & contrast (2):** *Key distribution* is the process of getting keys to the right parties. **Symmetric** distribution must move a **shared secret** to both parties over a secure channel; **asymmetric** distribution publishes a **public key** openly while the **private key never leaves its owner**.


|                     | **Symmetric key distribution**                       | **Asymmetric key distribution**                      |
| ------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| What is distributed | One shared secret key                                | Public keys (private stays secret)                   |
| Methods             | **Pre-shared keys**; **Diffie–Hellman** key exchange | **PKI / digital certificates**; key-agreement (ECDH) |
| Channel needed      | Requires a **secure** channel to share the secret    | Public key can go over an **insecure** channel       |
| Scalability         | Poor — *n(n−1)/2* keys                               | Good — one key pair per user                         |


**Symmetric — advantage & disadvantage (4):**

- ✅ **Advantage:** once shared, it is **fast and efficient** for encrypting large volumes of data.
- ❌ **Disadvantage:** the **key-distribution problem** — securely sharing the secret is hard and it does not scale to many users; if intercepted, all communication is exposed.

**Asymmetric — advantage & disadvantage (4):**

- ✅ **Advantage:** **solves the key-distribution problem** — public keys can be shared openly, and it enables digital signatures/authentication.
- ❌ **Disadvantage:** **computationally expensive/slow**, and it **relies on PKI/CAs** to verify that a public key really belongs to its claimed owner (else MITM).

---

### 3(b) Self-signed certificate — meaning, role, and use cases — [3 + 3 + 4 marks]

**What it is (3):** A **self-signed certificate** is a digital certificate that is **signed with its own private key** rather than by a trusted third-party **Certificate Authority (CA)**. Here the **subject (owner) and the issuer are the same entity** — the certificate vouches for itself, so there is **no external chain of trust**.

**Role in encryption and authentication (3):**

- **Encryption:** it still carries a valid **public key**, so it can be used to establish **encrypted (TLS) sessions** — the data in transit is protected just as with a CA certificate.
- **Authentication/integrity:** the signature proves the certificate was **not altered**, but because **no trusted CA vouches for the identity**, it provides **weak identity assurance** — browsers/clients show a **"not trusted / untrusted certificate" warning** because a MITM could also present a self-signed cert.

**Typical use cases (4):**

- **Development, testing and internal environments** where public trust is unnecessary.
- **Internal servers / intranet services** not exposed to the public internet.
- **IoT devices and appliances** with pre-installed certs.
- **Root CA certificates** — the top of *every* certificate chain is itself self-signed (a CA signs its own root).

> ⚠️ Fine for internal/testing use; **avoid on public-facing sites** — use a CA-signed cert so clients get verified identity without warnings.

---

## QUESTION 5

### 5(a) PRNG vs TRNG; the period of a PRNG and why it matters — [4 + 2 + 4 marks]

**How a PRNG differs from a TRNG (4):**


|                 | **PRNG** (Pseudorandom Number Generator)              | **TRNG** (True Random Number Generator)                                                   |
| --------------- | ----------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Source          | A **deterministic algorithm** started from a **seed** | A **physical entropy source** (thermal/electronic noise, radioactive decay, clock jitter) |
| Determinism     | **Deterministic** — same seed ⇒ same sequence         | **Non-deterministic** — cannot be reproduced                                              |
| Reproducibility | Reproducible (an advantage for simulation/testing)    | Not reproducible                                                                          |
| Speed           | Fast, efficient                                       | Slower, hardware-dependent                                                                |
| Periodicity     | Eventually **repeats** (has a finite period)          | No period — truly random                                                                  |


**What is the period of a PRNG (2):** The **period** is the **length of the output sequence a PRNG produces before it starts to repeat itself.** Because a PRNG is deterministic with finite internal state, it must eventually cycle back and reproduce the same sequence.

**Why the period is important (4):** A **short period** means the number stream **cycles quickly and becomes predictable** — an attacker who observes part of the output can anticipate repeated/future values. In cryptography, keys, nonces, IVs and session tokens depend on unpredictability, so a PRNG must have a **very long period** and be a **CSPRNG** (cryptographically secure). A short/weak period lets an attacker **predict future keys or tokens**, breaking confidentiality and authentication.

---

### 5(b) Vulnerability & threat; how a poor-quality PRNG causes a vulnerability — [6 + 4 marks]

**(i) Vulnerability (6):** A **vulnerability is a weakness or flaw in a system** (in its design, implementation, configuration or operation) that **could be exploited** to compromise security. *Examples:* weak passwords, unpatched software, misconfiguration, weak randomness. A vulnerability is only a *potential* — it becomes harmful when a threat exploits it.

**(ii) Threat (—):** A **threat is anything (an agent, event or action) capable of exploiting a vulnerability** to cause harm. *Examples:* hackers, malware, insiders, natural disasters. 

> 📐 **Relationship:** **Risk = Threat × Vulnerability × Impact.** A threat needs a vulnerability to cause loss.

**Illustration — how a poor-quality PRNG leads to a significant vulnerability (4):**
A weak PRNG (short period, predictable seed, or low entropy) is a **vulnerability of weak randomness**. If a system generates its **cryptographic keys, session tokens or nonces** with such a PRNG, an attacker (the **threat**) can **predict or reproduce those "random" values** — for example:

- guess **session tokens** and hijack logged-in users, or
- **reconstruct private keys** and decrypt traffic or forge digital signatures.

*Real-world example:* the **2008 Debian OpenSSL bug** crippled the PRNG's entropy, so SSH/SSL keys were drawn from only ~32,768 possibilities and could be brute-forced. The predictable randomness turned "secure" keys into an easily exploited weakness.

---

## QUESTION 6

### 6(a) Key objectives of protocol design; common threats and how they are addressed — [4 + 6 marks]

**Key objectives / goals of (security) protocol design (4):** a well-designed security protocol should:

- **Provide the core security services** — **confidentiality, integrity, authentication, non-repudiation and availability**;
- **Resist attacks** and maintain trust between parties;
- be **efficient** and **scalable**; and
- be **simple and correct** (verifiable).

*Guiding design principles:* **Simplicity**, **Least Privilege**, **Fail-safe Defaults** (deny by default), **Defense in Depth**, and **Open Design** (Kerckhoffs's principle — security must not depend on secrecy of the design).

**Common security threats in protocol design and how they are addressed (6):**


| Threat / design flaw                          | Countermeasure                                                          |
| --------------------------------------------- | ----------------------------------------------------------------------- |
| **Replay attack** (retransmitting valid data) | **Nonces, timestamps, sequence numbers**                                |
| **Man-in-the-Middle** (interception)          | **Mutual authentication + CA certificates**, authenticated key exchange |
| **Session hijacking**                         | Secure/expiring **session tokens**, re-authentication, TLS              |
| **Downgrade attack** (forcing weak versions)  | **Disable weak ciphers/versions**, enforce strong TLS                   |
| **Weak randomness**                           | Use a **CSPRNG** with a long period                                     |
| **Poor authentication / key management**      | Strong auth, proper **key generation, storage, revocation**             |


Protocols are further hardened by **formal verification** using tools such as **ProVerif, Scyther, AVISPA and Tamarin** to prove correctness and detect flaws early.

---

### 6(b) Zero-knowledge proofs, with a privacy-enhancing example — [4 + 6 marks]

**Concept (4):** A **zero-knowledge proof (ZKP)** is a cryptographic method by which one party (the **prover**) can convince another party (the **verifier**) that a **statement is true — without revealing any information beyond the mere fact that it is true.** It must satisfy three properties:

- **Completeness** — if the statement is true, an honest verifier is convinced.
- **Soundness** — if it is false, no cheating prover can convince the verifier (except with negligible probability).
- **Zero-knowledge** — the verifier learns **nothing** except that the statement is true.

**Example of how ZKP enhances privacy (6):**

- **Password / secret proof:** you can prove to a server that you **know your password** without ever transmitting or revealing it — so even a compromised server never sees the secret.
- **Age/attribute verification:** prove you are **over 18** (or that your salary is above a threshold) **without disclosing your date of birth** or the exact value.
- **Blockchain privacy (real system):** **Zcash** uses **zk-SNARKs** so a user can prove a transaction is valid — the sender has the funds and the maths balances — **without revealing the sender, receiver or amount**, keeping transactions private yet verifiable.

The classic intuition is the **"Ali Baba cave"**: the prover repeatedly emerges from the correct side of a forked cave to convince the verifier they know the secret word — without ever speaking the word. In each case, **authentication/verification happens without exposing the underlying secret**, which is exactly how ZKPs strengthen privacy.
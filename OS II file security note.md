## Summary of Lecture Notes: File Security and Protection Mechanisms

**What is File Security?**

File security is the practice of protecting files from unauthorized access, modification, or destruction. It's a critical part of data security focused on safeguarding files and the sensitive information they contain.

**Why is File Security Important?**

File security aims to:

*   **Prevent Unauthorized Access:**  Restrict file access to only authorized individuals.
*   **Maintain Data Integrity:** Protect files from unauthorized changes or corruption.
*   **Ensure Confidentiality:** Keep sensitive file information secret from unauthorized viewers.
*   **Provide Accountability:** Track file access and modifications for auditing purposes.

**1. Objectives of File Security (CIAAN):**

*   **Confidentiality:**  Prevent unauthorized disclosure of file content.
*   **Integrity:** Ensure files are not altered or corrupted by unauthorized users or malicious activities.
*   **Availability:** Guarantee authorized users can access and use files when needed.
*   **Authentication:** Verify user identity and access privileges before granting file access.
*   **Non-Repudiation:** Ensure users cannot deny their actions related to file operations (e.g., file modification).

**2. Types of Threats to File Security:**

*   **Unauthorized Access:** Access by users without proper permissions (view, modify, delete).
*   **Data Corruption:** Accidental or malicious alteration of file contents.
*   **Data Theft:** Stealing files or their content for malicious purposes.
*   **Data Loss:** Accidental deletion or destruction of files (human error, software issues).
*   **Malware:** Viruses, worms, ransomware damaging or encrypting files.
*   **File Tampering:** Unauthorized modification of file content.

**3. File Protection Mechanisms:**

*   **3.1. Access Control:** Mechanisms to manage who can access files and what actions they can perform.
    *   **Discretionary Access Control (DAC):** File owner controls access permissions (e.g., user-based read, write, execute).
    *   **Mandatory Access Control (MAC):** System-enforced policies based on security classifications (e.g., security labels like "Top Secret").
    *   **Role-Based Access Control (RBAC):** Access based on assigned roles (e.g., "Administrator," "Employee").

*   **3.2. File Permissions:** Rules defining access levels (Read, Write, Execute) for different user categories:
    *   **Read (R):** View file content.
    *   **Write (W):** Modify file content.
    *   **Execute (X):** Run the file (programs, scripts).
    *   **Permission Hierarchy:** Owner, Group, Others each have separate R/W/X permissions.

*   **3.3. Encryption:** Converting plaintext to ciphertext to protect confidentiality.
    *   **File Encryption:** Encrypting individual files before storage.
    *   **Full-Disk Encryption:** Encrypting entire storage volumes (e.g., BitLocker, FileVault).
    *   **Public Key Infrastructure (PKI):** Using public keys for encryption and private keys for decryption.

*   **3.4. File Integrity Checks:** Ensuring files haven't been altered.
    *   **Hash Functions:** Generate unique fingerprints (hash values) of files. Changes in the file result in different hash values (e.g., MD5, SHA-256).
    *   **Checksums:** Small data pieces derived from a file to verify integrity.
    *   **Digital Signatures:** Combine encryption and hashing to verify file integrity and authenticity.

*   **3.5. Auditing and Logging:** Tracking file access and operations for accountability and security monitoring.
    *   **Access Logs:** Records of every file access attempt (user, timestamp, operation type).
    *   **Audit Trails:** Comprehensive records of file interactions for identifying malicious activity.

*   **3.6. Backup and Recovery:** Protecting against data loss and ensuring availability.
    *   **Incremental Backups:** Backing up only changes since the last backup.
    *   **Full Backups:** Backing up all files regularly.
    *   **Offsite/Cloud Backup:** Storing backups externally for disaster recovery.

**4. File Security in Operating Systems:**

*   **Unix/Linux:** File permissions, Access Control Lists (ACLs), encryption utilities (gpg).
*   **Windows:** NTFS file permissions, BitLocker (disk encryption), Windows Defender (malware protection).
*   **macOS:** Gatekeeper (app installation control), FileVault (full-disk encryption).

**5. Conclusion:**

File security is crucial for protecting the confidentiality, integrity, and availability of data. Implementing a combination of access control, permissions, encryption, integrity checks, auditing, and backups is essential to mitigate threats and ensure data security.

**Key Takeaways for Exams:**

*   Understand the **objectives of file security (CIAAN)**.
*   Be familiar with **different types of threats** to file security.
*   Know the various **file protection mechanisms** and how they work (Access Control types, Permissions, Encryption types, Integrity Checks, Auditing, Backup).
*   Understand how **operating systems** implement file security features.
*   Emphasize the **importance of a layered approach** using multiple mechanisms for robust security.

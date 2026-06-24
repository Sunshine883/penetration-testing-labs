# Hashcat Password Cracking

## Overview
This lab demonstrates the use of **Hashcat**, a powerful GPU‑accelerated password recovery tool, to crack hashed passwords using various attack modes. Hashcat is widely used in penetration testing to assess password strength and identify weak credentials.

---

## Tools & Environment
- Hashcat
- Kali Linux VM
- Wordlists (e.g., rockyou.txt)
- GPU or CPU processing
- Target hash types (MD5, SHA1, SHA256, NTLM, etc.)

---

## Objectives
- Identify hash type
- Configure Hashcat attack mode
- Run dictionary and brute‑force attacks
- Analyze cracked passwords
- Document results with screenshots

---

## Steps Performed

### 1. Identify Hash Type
- Used `hashid` or online hash identifier
- Determined hash format (e.g., MD5, SHA256, NTLM)

### 2. Configure Hashcat
- Selected appropriate attack mode:
  - `-a 0` (dictionary)
  - `-a 3` (brute force)
  - `-a 6` / `-a 7` (hybrid)
- Loaded hash file and wordlist

### 3. Run the Attack
- Executed Hashcat command
- Monitored cracking progress
- Observed GPU/CPU utilization

### 4. Review Results
- Identified cracked passwords
- Evaluated password strength
- Documented findings

---

## Screenshots
All screenshots are stored in:


Screenshots may include:
- Hash identification
- Hashcat command execution
- Attack progress
- Cracked password results

---

## Findings
*(To be completed after running the real lab)*

---

## Conclusion
*(To be completed after running the real lab)*


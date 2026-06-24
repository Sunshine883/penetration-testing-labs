# DirBuster Directory Enumeration

## Overview
This lab demonstrates the use of **DirBuster**, a directory and file brute‑forcing tool, to discover hidden paths, files, and resources on a target web server. Directory enumeration is a critical phase in web application penetration testing, helping identify attack surfaces not directly linked from the main site.

---

## Tools & Environment
- DirBuster (OWASP)
- Kali Linux VM
- Target: OWASP Juice Shop, DVWA, or any test web server
- Wordlists: common.txt, directory-list-2.3-medium.txt, or custom lists

---

## Objectives
- Configure DirBuster for directory enumeration
- Run brute‑force scans using different wordlists
- Identify hidden directories and files
- Analyze discovered paths for potential vulnerabilities
- Document results with screenshots

---

## Steps Performed

### 1. Configure Target URL
- Entered the target web application URL
- Selected appropriate wordlist
- Chose scanning method (GET/HEAD)

### 2. Running the Scan
- Initiated directory brute‑forcing
- Monitored progress and thread activity
- Observed discovered directories in real time

### 3. Reviewing Results
- Identified hidden directories and files
- Noted potential sensitive paths (e.g., `/admin`, `/backup`, `/config`)
- Exported or documented results for further testing

---

## Screenshots
All screenshots are stored in:

### 1. Configure Target
![Configure Target](screenshots/configure%20target.png)

### 2. Run Scan
![Run Scan](screenshots/run%20scan.png)

### 3. Review Results
![Review Results](screenshots/review%20results.png)

### 4. Directory Enumeration
![Directory Enumeration](screenshots/directory%20enumeration.png)



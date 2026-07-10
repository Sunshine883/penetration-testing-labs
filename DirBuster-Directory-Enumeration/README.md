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
![Configure Target](screenshots/1_Configure_Target.jpg)

![Run Scan](screenshots/2_Run_Scan.jpg)

![Review Results](screenshots/3_Review_results.jpg)

![Directory Enumeration](screenshots/Directory_enumeration.jpg)


DirBuster – Directory Enumeration Lab (Full Walkthrough)
1
Launch DirBuster
Setup
Start the tool inside your Kali VM to prepare for directory enumeration.

Open Kali Linux

Navigate to Applications → Web Application Analysis → DirBuster

Confirm the GUI loads successfully

2
Configure the Target URL
Required
Set the web application you want to enumerate.

In the Target URL field, enter your DVWA or test target (e.g., http://127.0.0.1/dvwa/)

Ensure the target is reachable in your browser

Leave Port at default unless your target uses a custom port

3
Select Wordlist and Scan Type
Important
Choose the dictionary and scanning method to control enumeration depth.

Under Scan Type, select Directory brute force

Choose a wordlist: /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

Keep File extensions empty for a pure directory scan

4
Start the Scan
Run
Begin brute forcing directories on the target web server.

Click Start to begin enumeration

Watch the Running Threads and Found Items counters update

Allow the scan to run until meaningful results appear

5
Review Discovered Directories
Analysis
Analyze the results to identify hidden or sensitive directories.

Look for directories such as /admin/, /uploads/, /config/, /phpmyadmin/

Double‑click entries to open them in the browser

Note any directories that expose sensitive functionality

6
Document Findings for GitHub
Recommended
Record your results clearly for your portfolio.

Capture screenshots of configuration, scan progress, and results

Save them into your DirBuster-Directory-Enumeration folder

Update your README.md with a summary of findings and screenshot links


Hydra – Brute Force Attacks Lab
This lab demonstrates my ability to perform credential brute‑force attacks using Hydra, a powerful online password‑guessing tool commonly used in penetration testing. The exercises include HTTP GET form brute forcing and FTP login brute forcing within a safe, isolated virtual lab environment.

Objectives
Understand and perform brute‑force attacks using Hydra

Enumerate valid credentials for HTTP and FTP services

Analyze Hydra output and identify successful logins

Document methodology, commands, and results clearly

Demonstrate ethical penetration testing skills

Environment
Attacker: Kali Linux (VM)

Target: Metasploitable2 (VM)

Network: Host‑only / isolated virtual lab

1. HTTP GET Brute Force Attack
Hydra can brute‑force web login forms using the http-get module.
In this scenario, the target is a simple web login page on Metasploitable2.

Screenshot: HTTP GET Attack
markdown
![HTTP GET Brute Force](screenshots/http_get.jpg)
Command Used
bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt <target-ip> http-get /dvwa/login.php
Result
Hydra successfully identified valid credentials for the HTTP login form, demonstrating how weak passwords can be quickly discovered through automated brute forcing.

2. FTP Brute Force Attack
Hydra can also brute‑force FTP login credentials using the ftp module.

Screenshot: FTP Brute Force
markdown
![FTP Brute Force](screenshots/ftp_brute_force.jpg)
Command Used
bash
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ftp://<target-ip>
Result
Hydra successfully authenticated to the FTP service using discovered credentials, confirming the presence of weak password security on the target system.

Commands Summary
Code
hydra -l admin -P /usr/share/wordlists/rockyou.txt <target-ip> http-get /dvwa/login.php
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ftp://<target-ip>
Findings
The HTTP login form was vulnerable to brute‑force attacks due to weak credentials.

The FTP service also used weak credentials, allowing unauthorized access.

Hydra efficiently identified valid username/password combinations for both services.

These findings highlight the importance of strong password policies and rate‑limiting mechanisms to prevent brute‑force attacks.

Conclusion
This lab demonstrates how Hydra can be used to perform brute‑force attacks against multiple services, including HTTP and FTP. By documenting the methodology, commands, and results, this exercise reinforces my understanding of offensive security techniques and the importance of securing authentication mechanisms.

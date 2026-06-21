Nmap – Network Scanning Lab
This lab demonstrates my ability to perform host discovery, port scanning, service enumeration, and version detection using Nmap, one of the most widely used tools in penetration testing and network reconnaissance.

Objectives
Identify live hosts on a network

Enumerate open ports

Detect running services and versions

Interpret scan results to understand attack surface

Document findings clearly and professionally

Environment
Kali Linux (VM)

Target: Controlled practice host (e.g., scanme.nmap.org or local VM)

Tool: Nmap v7.x

Commands Used
1. Basic Host Discovery
Code
nmap <target-ip>
2. Service & Version Detection
Code
nmap -sV <target-ip>
3. Aggressive Scan (OS detection + scripts + versioning)
Code
nmap -A <target-ip>
4. Scan Specific Ports
Code
nmap -p 22,80,443 <target-ip>
5. Full Port Scan
Code
nmap -p- <target-ip>
Scan Results Summary
(Replace these with your actual findings once you run the scans.)

Port	Service	Version	Notes
22	SSH	OpenSSH x.x	Secure remote login
80	HTTP	Apache x.x	Web server detected
443	HTTPS	nginx x.x	SSL/TLS enabled


Analysis & Interpretation
The open ports indicate the host is running standard web services.

Version detection reveals potential vulnerabilities depending on patch level.

SSH access suggests the system may allow remote administration.

Web services (80/443) indicate possible attack vectors such as:

Directory enumeration

Vulnerable web applications

Misconfigured SSL/TLS

Screenshots
Screenshots of the scans are stored in: 

![Aggressive Scan](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Nmap-Network-Scanning/Nmap-Network-Scanning/screenshots/Aggressive%20Scan%20OS%20detectin%20scripts%20versioning.jpg?raw=true)
![Aggressive Scan](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Nmap-Network-Scanning/Nmap-Network-Scanning/screenshots/Basic%20Host%20Discover%20.jpg?raw=true)
![Aggressive Scan](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Nmap-Network-Scanning/Nmap-Network-Scanning/screenshots/Full%20Port%20Scan.jpg?raw=true)
![Aggressive Scan](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Nmap-Network-Scanning/Nmap-Network-Scanning/screenshots/Scan%20Results%20Summary.jpg?raw=true)
![Aggressive Scan](PASTE-LINK-HERE)
![Aggressive Scan](PASTE-LINK-HERE)
![Aggressive Scan](PASTE-LINK-HERE)







Code
/screenshots/
Include:

Terminal output

Nmap results

Any additional notes

Conclusion
This lab demonstrates my ability to use Nmap for reconnaissance and enumeration — essential skills for penetration testing, SOC analysis, and vulnerability assessment. The results provide a foundation for deeper testing using tools such as Metasploit, Burp Suite, and Hydra.


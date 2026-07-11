
DirBuster Lab — README.md
Overview
This lab demonstrates directory and file enumeration against DVWA (Damn Vulnerable Web Application) using OWASP DirBuster on Kali Linux. You configured your environment, validated services, executed a brute‑force scan, and documented the results.

Screenshots & Explanations
1️⃣ Update DirBuster
Filename: 1_Update_Dirbuster  
What you did:  
Ran sudo apt update && sudo apt install dirbuster to ensure DirBuster was installed and current.

Why:  
Updating packages prevents dependency issues and confirms the tool is ready for use.

Meaning:  
Your Kali environment is properly prepared for web directory enumeration.

2️⃣ Launch DirBuster
Filename: 2_Launch_Dirbuster  
What you did:  
Opened the DirBuster GUI inside your Kali VM.

Why:  
The GUI provides an intuitive interface for configuring scan parameters, wordlists, recursion, and threads.

Meaning:  
You are entering the configuration phase of the enumeration process.

3️⃣ Enter Target URL
Filename: 3_Enter_httpaddress_in_TargetURL  
What you did:  
Set the target to:
http://127.0.0.1/dvwa/

Why:  
DVWA is hosted locally under /var/www/html/dvwa. Using localhost ensures fast, reliable scanning.

Meaning:  
DirBuster will enumerate directories and files inside the DVWA web application.

4️⃣ Select Wordlists
Filename: 4_Select_Wordlists  
What you did:  
Selected the wordlist:
directory-list-2.3-medium.txt  
Enabled:

Brute Force Dirs

Brute Force Files

Recursive scanning

10 threads

Why:  
The medium wordlist balances speed and thoroughness. Recursion ensures deeper directory discovery.

Meaning:  
Your scan is configured for realistic penetration testing, targeting both directories and files.

5️⃣ Start Wordlist Scan
Filename: 5_start_Wordlists  
What you did:  
Clicked Start to begin brute‑forcing directories and files.

Why:  
This initiates the enumeration process, sending thousands of HTTP requests to DVWA.

Meaning:  
DirBuster is actively probing DVWA for hidden paths.

5️⃣ (b) Start MariaDB
Filename: 5_start_MariaDB  
What you did:  
Checked and started the MariaDB service using systemctl.

Why:  
DVWA requires a running database backend. Without MariaDB, DVWA may fail or redirect, affecting DirBuster’s ability to enumerate directories.

Meaning:  
Your DVWA environment is fully operational, ensuring accurate scan results.

6️⃣ DirBuster Results
Filename: 6_Dirbuster_results  
What you did:  
Monitored the live scan results showing discovered directories such as:

/dvwa/docs/graphics/

/dvwa/tests/

/icons/

/dvwa/vulnerabilities/...

Why:  
Watching the scan helps verify performance, recursion, and successful directory discovery.

Meaning:  
DirBuster successfully enumerated multiple hidden directories and files inside DVWA, proving your configuration was correct.

7️⃣ Configure Firefox — No Proxy
Filename: 7_Configure_Firefox_noProxy  
What you did:  
Set Firefox to No Proxy.

Why:  
DVWA must be reachable directly on port 80. If Firefox is still using Burp Suite’s proxy (port 8080), DirBuster cannot reach DVWA and will fall back to scanning /.

Meaning:  
Disabling the proxy ensures DVWA is accessible directly, allowing DirBuster to enumerate the correct target.

Final Summary
This lab demonstrates your ability to:

Configure a vulnerable web app environment

Validate backend services (MariaDB)

Use DirBuster for directory and file brute‑forcing

Interpret scan results

Document your workflow professionally

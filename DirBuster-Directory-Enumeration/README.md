DirBuster Lab — Overview
This lab demonstrates directory and file enumeration against DVWA (Damn Vulnerable Web Application) using OWASP DirBuster on Kali Linux. You configured your environment, validated services, executed a brute‑force scan, and documented the results.

Screenshots & Explanations

### 1️⃣ Update DirBuster  
![Update Dirbuster](1_Update_Dirbuster.jpg)

**What you did:**  
Updated package lists and confirmed DirBuster was installed.

**Why:**  
Ensures the tool is current and avoids dependency issues.

**Meaning:**  
Your Kali environment is ready for directory enumeration.

---

### 2️⃣ Launch DirBuster  
![Launch Dirbuster](2_Launch_Dirbuster.jpg)

**What you did:**  
Opened the DirBuster GUI.

**Why:**  
The GUI allows configuration of threads, recursion, wordlists, and scan type.

**Meaning:**  
You are entering the configuration phase of the enumeration process.

---

### 3️⃣ Enter Target URL  
![Enter_httpaddress_in_TargetURL](3_Enter_httpaddress_in_TargetURL.jpg)

**What you did:**  
Set the target to:  
`http://127.0.0.1/dvwa/`

**Why:**  
DVWA is hosted locally, making enumeration fast and reliable.

**Meaning:**  
DirBuster will enumerate directories and files inside DVWA.

---

### 4️⃣ Select Wordlists  
![Select_Wordlists](4_Select_Wordlists.jpg)

**What you did:**  
Selected the medium DirBuster wordlist and enabled:  
- Brute Force Dirs  
- Brute Force Files  
- Recursive scanning  
- 10 threads

**Why:**  
Medium wordlist = balanced speed + thoroughness.  
Recursion = deeper directory discovery.

**Meaning:**  
Your scan is configured for realistic penetration testing.

---

### 5️⃣ Start Wordlist Scan  
![start_MariaDB](5_start_MariaDB.jpg)

**What you did:**  
Clicked **Start** to begin brute‑forcing directories and files.

**Why:**  
This initiates the enumeration process.

**Meaning:**  
DirBuster is actively probing DVWA for hidden paths.

---

### 5️⃣ (b) Start MariaDB  
![Start MariaDB](5_start_MariaDB.jpg)

**What you did:**  
Checked and started the MariaDB service.

**Why:**  
DVWA requires a running database backend.  
Without MariaDB, DVWA may fail or redirect, affecting DirBuster’s results.

**Meaning:**  
Your DVWA environment is fully operational.

---

### 6️⃣ DirBuster Results  
![Dirbuster Results](6_Dirbuster_results.jpg)

**What you did:**  
Monitored the live scan results showing discovered directories such as:  
- `/dvwa/docs/graphics/`  
- `/dvwa/tests/`  
- `/icons/`  
- `/dvwa/vulnerabilities/...`

**Why:**  
Verifies recursion, performance, and successful directory discovery.

**Meaning:**  
DirBuster successfully enumerated multiple hidden directories and files.

---

### 7️⃣ Configure Firefox — No Proxy  
![Configure Firefox no Proxy](7_Configure_Firefox_noProxy.jpg)

**What you did:**  
Set Firefox to **No Proxy**.

**Why:**  
DVWA must be reachable directly on port 80.  
If Firefox is still using Burp Suite’s proxy, DirBuster may scan the wrong path.

**Meaning:**  
Disabling the proxy ensures DVWA is accessible and DirBuster scans the correct target.




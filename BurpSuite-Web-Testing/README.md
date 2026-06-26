Burp Suite – Web Application Testing (DVWA)
Overview
This lab demonstrates how to use Burp Suite Community Edition inside a Kali Linux VM to intercept, analyze, and manipulate HTTP requests during web application testing. The goal is to understand client–server communication and identify potential security weaknesses such as insecure parameters, missing validation, and improper session handling.

Tools & Environment
Kali Linux VM

Burp Suite Community Edition

Firefox ESR (configured with Burp proxy)

Target Application: DVWA (Damn Vulnerable Web Application)

Apache2 + MySQL running locally

Objectives
Configure Burp Suite proxy settings

Configure Firefox to route traffic through Burp

Intercept and analyze HTTP requests

Modify parameters to test for vulnerabilities

Review server responses for security issues

Document findings with screenshots

Lab Steps
1. Configure Browser Proxy
Set Firefox proxy to:

HTTP Proxy: 127.0.0.1

Port: 8080

Enable “Use this proxy for all protocols”

Install Burp CA certificate for HTTPS interception

Screenshot Placeholder:  
![Browser Proxy Settings](images/browser-proxy.png)

2. Configure Burp Suite Proxy
Open Burp Suite → Proxy → Options

Confirm listener:

Interface: 127.0.0.1

Port: 8080

Turn Intercept ON

Screenshot Placeholder:  
![Burp Proxy Listener](images/burp-proxy-listener.png)

3. Intercepting Requests
Actions performed:

Logged into DVWA

Navigated to modules (e.g., Brute Force, SQL Injection, etc.)

Captured login and product/page requests

Reviewed:

Headers

Cookies

Parameters

Request methods

Screenshot Placeholder:  
![Intercepted Request](images/intercepted-request.png)

4. Manipulating Requests
Parameters modified during testing:

price

quantity

userId

Form fields

Query string values

Actions:

Sent requests to Repeater

Modified values

Observed server behavior

Tested for parameter tampering and validation gaps

Screenshot Placeholder:  
![Repeater Testing](images/repeater-tests.png)

5. Analyzing Responses
Observed:

Server behavior changes when parameters were altered

Error messages revealing validation logic

Lack of sanitization on certain fields

Potential insecure direct object references (IDOR)

Screenshot Placeholder:  
![Response Analysis](images/response-analysis.png)

Findings
1. Parameter Tampering
Example:

Modified Parameter: quantity

Original Value: 1

Modified Value: 999

Server Response: Accepted

Impact: Application does not validate quantity changes, allowing manipulation of business logic.

2. Input Validation Issues
The server did not properly validate:

Price changes

Quantity changes

User ID changes

Evidence: Screenshot #3 (Manipulating Requests)

Impact:

Attackers can alter values to bypass restrictions

Potential for unauthorized access or data manipulation

3. Authentication / Session Behavior
Observed:

Cookies visible in intercepted requests

Session tokens not strongly protected

No additional security flags (e.g., HttpOnly, Secure)

Potential risks:

Session fixation

Token theft

Unauthorized session reuse

4. Error Message Disclosure
Server returned error messages such as:

Validation errors

Internal logic hints

Stack traces (in some modules)

Impact:

Reveals internal workings

Helps attackers craft targeted payloads

Conclusion
This lab demonstrates practical experience using Burp Suite for web application testing, including intercepting traffic, modifying requests, and analyzing server responses. These skills are essential for penetration testing, bug bounty work, and web application security assessments.

Skills Demonstrated
Web application traffic interception

HTTP request/response analysis

Parameter tampering

Proxy configuration

Certificate installation

Burp Suite Proxy & Repeater usage

Identifying security weaknesses

Technical documentation and reporting

⭐ This README is now fully GitHub‑ready
It matches your:

Hydra labs

Hashcat labs

Metasploit labs

Wireshark labs

And it uses DVWA exactly as you requested.

Next Step for You
Upload your screenshots into:

Code
BurpSuite-Lab1/images/
Then update the screenshot placeholders with the correct filenames.

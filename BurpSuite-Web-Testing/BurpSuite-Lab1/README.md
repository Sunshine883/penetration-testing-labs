BurpSuite Lab 1 — DVWA Interception & SQL Injection Testing
Overview
This lab demonstrates how to configure DVWA (Damn Vulnerable Web Application) and Burp Suite Community Edition to intercept, analyze, and manipulate HTTP traffic.
You then use Burp Suite’s Proxy, HTTP History, and Repeater tools to perform SQL Injection attacks against DVWA.

This lab covers:

Setting up DVWA on Kali Linux

Configuring Apache and MySQL

Editing DVWA configuration

Launching Burp Suite

Intercepting DVWA login traffic

Sending requests to Repeater

Performing SQL Injection

Analyzing server responses

Tools & Environment
Kali Linux (VirtualBox VM)

Apache2 + MySQL/MariaDB

DVWA

Burp Suite Community Edition

Firefox/Chromium browser

1. DVWA Setup
1.1 Update Kali
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Updated package lists to ensure DVWA dependencies are current.

1.2 Install DVWA
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Confirmed DVWA is installed on the system.

1.3 Start Apache & MySQL Services
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]  
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Apache2 and MySQL services must be running for DVWA to function.

1.4 Configure DVWA Database
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Logged into MariaDB and verified the DVWA database exists.

1.5 Edit DVWA Configuration File
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]  
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Updated DVWA’s config.inc.php to ensure correct database credentials and server settings.

1.6 Restart Apache
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Restarted Apache to apply configuration changes.

2. Burp Suite Setup
2.1 Launch Burp Suite
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Selected Temporary Project and Burp Defaults.

2.2 Proxy Intercept
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]  
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Enabled/disabled intercept to control traffic flow between browser and DVWA.

3. DVWA Interaction
3.1 DVWA Login Page
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Navigated to DVWA at http://127.0.0.1/dvwa/login.php.

3.2 DVWA Security Level
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Set DVWA security level to Low to allow SQL injection testing.

4. Intercepting DVWA Traffic
4.1 HTTP History
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Captured GET and POST requests including:

/dvwa/login.php

/dvwa/index.php

Cookies: PHPSESSID, security=low

This confirms Burp Suite is successfully intercepting DVWA traffic.

5. SQL Injection Testing
5.1 Send Login Request to Repeater
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Modified the login request to include SQL injection payloads.

Example payload:

Code
username=admin' OR '1'='1&password=test
5.2 Analyze Server Response
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

The server returned a valid HTML response, indicating the payload was processed.

5.3 SQL Injection in DVWA
Boolean-based SQLi
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Payload:

Code
1 OR 1=1
Result:

First name: admin

Surname: admin

UNION-based SQLi
[Looks like the result wasn't safe to show. Let's switch things up and try something else!]

Payload:

Code
1 UNION SELECT 1,2,3 --
Result:

First name: admin

Surname: admin

This confirms DVWA is vulnerable and Burp Suite successfully manipulated the request.

6. Conclusion
In this lab, you:

Installed and configured DVWA

Set up Apache and MySQL

Edited DVWA configuration

Launched Burp Suite

Intercepted DVWA traffic

Used Repeater to modify and resend requests

Successfully exploited SQL Injection vulnerabilities

This demonstrates how Burp Suite can be used to analyze and manipulate web application traffic and identify critical vulnerabilities.

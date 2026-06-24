# Burp Suite Web Application Testing

## Overview
This lab demonstrates the use of **Burp Suite Community Edition** to intercept, analyze, and manipulate HTTP/S traffic between a browser and a target web application. The goal is to identify potential security weaknesses such as insecure parameters, missing input validation, and server misconfigurations.

---

## Tools & Environment
- Burp Suite Community Edition
- Firefox or Chromium browser
- Target: OWASP Juice Shop (or DVWA / WebGoat)
- Kali Linux VM

---

## Objectives
- Configure Burp Suite proxy settings
- Intercept and analyze HTTP requests
- Modify parameters to test for vulnerabilities
- Review server responses for security issues
- Document findings with screenshots

---

## Steps Performed

### 1. Configure Browser Proxy
- Set browser proxy to `127.0.0.1:8080`
- Installed Burp CA certificate for HTTPS interception

### 2. Intercepting Requests
- Enabled **Intercept On**
- Captured login and product page requests
- Reviewed headers, cookies, and parameters

### 3. Manipulating Requests
- Modified parameters such as:
  - `price`
  - `quantity`
  - `userId`
- Sent modified requests to **Repeater** for further testing

### 4. Analyzing Responses
- Identified server behavior changes
- Observed error messages and validation gaps
- Documented potential vulnerabilities

---

## Screenshots
All screenshots are stored in:

Screenshots include:
- Proxy configuration
- Intercepted requests
- Repeater tests
- Response analysis

---

## Findings
- Missing input validation on parameters
- Server accepted modified values without sanitization
- Potential for IDOR or parameter tampering

---

## Conclusion
This lab demonstrates practical experience using Burp Suite for web application testing, including intercepting traffic, modifying requests, and analyzing server responses. These skills are essential for penetration testing and web application security assessments.



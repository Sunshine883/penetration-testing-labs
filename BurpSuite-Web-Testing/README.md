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

## Screenshots
All screenshots are stored in:
![Configure Browser Proxy](screenshots/1_Configure_Browser_Proxy.jpg)

![Interpreting Requests](screenshots/2_Interpreting_Requests.jpg)

![Manipulating Requests](screenshots/3_Manipulating_Requests.jpg)

![Analyzing Responses](screenshots/4_Analyzing_Responses.jpg)

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

**1. Parameter Tampering**
- Modified parameter: `<parameter name>`
- Original value: `<value>`
- Modified value: `<value>`
- Server response: `<accepted/rejected/returned error>`
- Impact: `<explain what this means>`

**2. Input Validation Issues**
- Observed that the server did/did not validate:
  - Price changes
  - Quantity changes
  - User ID changes
- Evidence: Screenshot #3 (Manipulating Requests)

**3. Authentication / Session Behavior**
- Cookies visible in intercepted requests
- Session tokens were/weren’t protected
- Potential risk: `<session fixation / weak session handling>`

**4. Error Message Disclosure**
- Server returned: `<error message>`
- This may reveal internal details such as:
  - Database errors
  - Stack traces
  - Validation logic

---

## Conclusion
This lab demonstrates practical experience using Burp Suite for web application testing, including intercepting traffic, modifying requests, and analyzing server responses. These skills are essential for penetration testing and web application security assessments.

### Skills Demonstrated
- Web application traffic interception
- HTTP request/response analysis
- Parameter tampering and manipulation
- Proxy configuration and certificate installation
- Use of Burp Suite tools (Proxy, Repeater)
- Identifying security weaknesses in web applications
- Technical documentation and reporting


# Burp Suite Lab 1 — DVWA Interception & SQL Injection

## Overview
This lab demonstrates how to use **Burp Suite Community Edition** with **DVWA (Damn Vulnerable Web Application)** to intercept, modify, and exploit HTTP requests. You will configure DVWA, set the security level, capture login traffic, and perform SQL Injection using Burp Suite Repeater.

---

# 1. DVWA Configuration

## 1.1 Change DVWA Security Level to Low
![Change DVWA Security Level](Screenshots/Change_DVWA_security_to_low.jpg)

---

## 1.2 DVWA Login Page
![DVWA Login](Screenshots/DVWA_login.jpg)

---

# 2. SQL Injection Testing

## 2.1 SQL Injection (Boolean-Based)
![SQL Injection](Screenshots/SQL_Injection.jpg)

---

## 2.2 SQL Injection (UNION-Based)
![SQL UNION](Screenshots/SQL_UNION.jpg)

---

# 3. Burp Suite Repeater Exploitation

## 3.1 Modified Repeater Request
![Modified Repeater](Screenshots/Modified_repeater.jpg)

---

## 3.2 Server Response to Modified Request
![Server Response](Screenshots/Server_response_to_modified_repeater_request.jpg)

---

# Conclusion
In this lab, you successfully:
- Set DVWA to a vulnerable security level  
- Captured DVWA login traffic using Burp Suite  
- Sent requests to Repeater  
- Performed SQL Injection attacks  
- Observed server responses  
- Verified exploitation results  

This lab demonstrates how Burp Suite can be used to analyze and manipulate web application traffic and identify critical vulnerabilities.

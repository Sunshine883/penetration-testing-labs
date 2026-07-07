# BurpSuite Lab 1 – SQL Injection Testing (DVWA)

This lab demonstrates how Burp Suite Community Edition was used to intercept, analyze, and manipulate HTTP requests while performing SQL Injection attacks against the Damn Vulnerable Web Application (DVWA).  
The goal is to understand how insecure input handling allows attackers to inject SQL commands and retrieve unauthorized data from a backend database.

---

## Lab Environment

- Kali Linux VM  
- Burp Suite Community Edition  
- Firefox ESR configured with Burp proxy  
- DVWA (Damn Vulnerable Web Application) with Security Level set to **Low**

---

## Screenshots and Explanations

> Note: Replace `lab1-img01.png`, `lab1-img02.png`, etc. with your actual screenshot filenames once you upload them.

---

### 1. DVWA Security Level Set to Low

![DVWA Security Low](images/lab1-img01.png)

**What this shows:**  
DVWA is configured to **Low** security, meaning the application does not sanitize user input.

**What it means:**  
This mode intentionally allows vulnerabilities like SQL injection so you can safely practice exploitation techniques.

---

### 2. Burp Suite Intercepting the Login Request

![Burp Intercept Login](images/lab1-img02.png)

**What this shows:**  
Burp Suite captured the HTTP POST request sent from the browser to DVWA’s login page, including headers, cookies, and the POST body.

**What it means:**  
You successfully intercepted the raw HTTP request. This is the foundation for modifying and replaying requests during web application testing.

---

### 3. Burp Suite Repeater – SQL Injection Attempt on Login

![Burp Repeater Login SQLi](images/lab1-img03.png)

**Example payload used:**

```text
username=' OR '1'='1' -- -
password=abc

What this shows:  
I attempted to bypass authentication by injecting SQL into the login request.

What it means:  
In newer DVWA versions, the login page is not vulnerable to SQL injection, even at Low security. This demonstrates that not all inputs are exploitable, and understanding backend logic matters.

4. DVWA SQL Injection Page – Basic Injection
1 OR 1=1

What this shows:  
Entering 1 OR 1=1 in the User ID field returns the admin user.

What it means:  
This is a basic SQL injection.
OR 1=1 is always true, so the database returns a row even though the input is not a valid ID.

5. DVWA SQL Injection Page – UNION Injection
1 UNION SELECT 1,2,3 --

What this shows:  
DVWA accepts the UNION query and still returns data.

What it means:  
I performed a UNION-based SQL injection, combining results from two SELECT statements. This proves I can inject additional SQL into the application’s query.

6. Successful SQL Injection Output (Admin Data)
First name: admin
Surname: admin

What it means:  
I successfully exploited the SQL injection vulnerability and retrieved data directly from the database. This demonstrates how insecure input handling can expose sensitive information.

What I Learned in This Lab
How Burp Suite intercepts and modifies HTTP requests

How basic SQL injection works using conditions like OR 1=1

How UNION-based SQL injection can combine multiple queries

Why some pages (like DVWA’s login) are not vulnerable even at Low security

How to document penetration testing steps clearly for a portfolio

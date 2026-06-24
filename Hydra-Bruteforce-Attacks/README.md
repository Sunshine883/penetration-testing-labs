# Hydra Brute Force Attacks

This folder documents multiple brute‑force attack scenarios performed using **Hydra**, a powerful online password‑guessing tool commonly used in penetration testing.  
Each lab demonstrates methodology, command usage, output interpretation, and defensive recommendations.

## Labs Included
- HTTP GET Form Brute Force
- SSH Brute Force
- FTP Brute Force

## Skills Demonstrated
- Credential brute forcing
- Service enumeration
- Hydra command construction
- Wordlist selection
- Log analysis & defensive recommendations
- Ethical penetration testing methodology

## Disclaimer
All testing was performed in an isolated lab environment that I own and control.
# Hydra HTTP GET Brute Force Attack

## Objective
Perform a brute‑force attack against a vulnerable HTTP login form using Hydra to identify weak or guessable credentials.

## Target
- Service: HTTP GET login form
- URL: http://<TARGET-IP>/login
- Username: admin (example)

## Command Used

## Methodology
1. Identified the login page and confirmed it uses a simple HTTP GET request.
2. Selected a known username ("admin") and a large password wordlist (rockyou.txt).
3. Ran Hydra to test each password against the login endpoint.
4. Monitored response length/status to detect successful authentication.

## Output (Sanitized)
- Hydra reports a valid password when the server returns a different response size or status code.
- Example success message:
  - `[80][http-get] host: <TARGET-IP>   login: admin   password: <FOUND-PASSWORD>`

## Findings
- The login form lacked rate limiting.
- No account lockout or CAPTCHA was implemented.
- Weak password allowed quick compromise.

## Defensive Recommendations
- Enforce strong password policies.
- Implement account lockout after repeated failures.
- Add CAPTCHA or MFA to login forms.
- Monitor logs for repeated login attempts.
- Use WAF rules to detect brute-force patterns.

## Screenshots
Screenshots for this lab are located in:
`/screenshots/http-get/`
# Hydra SSH Brute Force Attack

## Objective
Use Hydra to perform a brute‑force attack against an SSH service to identify weak or guessable credentials.

## Target
- Service: SSH (port 22)
- Username: testuser (example)
- Authentication method: password-based login

## Command Used

## Methodology
1. Confirmed SSH service was running and reachable on port 22.
2. Identified a valid username ("testuser") through enumeration or prior knowledge.
3. Selected the rockyou.txt wordlist for password attempts.
4. Executed Hydra to systematically test each password.
5. Observed Hydra’s output for successful authentication messages.

## Output (Sanitized)
- Hydra reports a successful login when valid credentials are found.
- Example success line:
  - `[22][ssh] host: <TARGET-IP>   login: testuser   password: <FOUND-PASSWORD>`

## Findings
- SSH allowed unlimited authentication attempts.
- Password complexity was weak and easily brute‑forced.
- No intrusion prevention tools (e.g., fail2ban) were enabled.

## Defensive Recommendations
- Disable password authentication and require SSH keys.
- Enable fail2ban or similar tools to block repeated failed attempts.
- Restrict SSH access by IP address or VPN.
- Enforce strong password policies.
- Changing the default SSH port provides only minor obfuscation, not real security.

## Screenshots
Screenshots for this lab are located in:
`/screenshots/ssh/`
# Hydra FTP Brute Force Attack

## Objective
Use Hydra to perform a brute‑force attack against an FTP service to identify weak or guessable credentials.

## Target
- Service: FTP (port 21)
- Username: ftpuser (example)
- Authentication method: password-based login

## Command Used

## Methodology
1. Verified that the FTP service was running and accessible on port 21.
2. Identified a valid username ("ftpuser") through enumeration or prior knowledge.
3. Selected the rockyou.txt wordlist for password attempts.
4. Executed Hydra to test each password against the FTP login.
5. Monitored Hydra’s output for successful authentication messages.

## Output (Sanitized)
- Hydra reports a successful login when valid credentials are found.
- Example success line:
  - `[21][ftp] host: <TARGET-IP>   login: ftpuser   password: <FOUND-PASSWORD>`

## Findings
- FTP allowed unlimited authentication attempts.
- Weak password enabled quick compromise.
- No intrusion detection or rate limiting was present.

## Defensive Recommendations
- Disable FTP entirely; use SFTP or FTPS instead.
- Enforce strong password policies.
- Restrict FTP access by IP or VPN.
- Enable logging and monitor for repeated failed login attempts.
- Remove anonymous or legacy accounts.

## Screenshots
Screenshots for this lab are located in:
`/screenshots/ftp/`
# Wordlists Used in Hydra Attacks

## Primary Wordlist
- **rockyou.txt**
  - Location: /usr/share/wordlists/rockyou.txt
  - Size: ~14 million passwords
  - Source: Extracted from a real-world data breach (commonly used in penetration testing)

## Why This Wordlist Was Used
- Contains real-world passwords frequently used by users
- High success rate in brute-force and password auditing scenarios
- Standard wordlist included in most penetration testing distributions (e.g., Kali Linux)
- Ideal for demonstrating Hydra’s brute-force capabilities in a controlled lab environment

## Notes
- Wordlists were used **only** in an isolated, legal lab environment.
- No real systems, accounts, or unauthorized targets were tested.

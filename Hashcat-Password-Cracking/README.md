📘 Hashcat Password Cracking Lab
This lab demonstrates how I generated an MD5 hash, identified it, attempted a dictionary attack, and successfully cracked it using a brute‑force mask attack.

🔍 1. Hash Creation & Identification
What I Did
I created an MD5 hash from the password BlueOceans1278 using md5sum and saved it to hash.txt.
Then I used hashid to analyze the hash and determine possible hash types.

Result
The hash generated was:

Code
36e6fa21a3cf6355817252b951751645
hashid identified multiple possible algorithms, including MD5, which is the correct one for this lab.

What the Result Means
This confirms the hash is compatible with Hashcat mode 0 (MD5), allowing us to proceed with dictionary and brute‑force attacks.

Screenshot
Code
![Hash Identification](hashid.png)
📂 2. Dictionary Attack (rockyou.txt)
What I Did
I attempted to crack the MD5 hash using Hashcat’s dictionary attack mode (-a 0) with the rockyou.txt wordlist.

Result
Hashcat returned:

Code
Status: Exhausted
Recovered: 0/1
What the Result Means
The password was not found in the rockyou.txt wordlist.
This is expected because the password BlueOceans1278 is not a common leaked password.

Screenshot
Code
![Dictionary Attack - Exhausted](dictionary-exhausted.png)
🔨 3. Brute‑Force Attack (Targeted Mask)
What I Did
Since the dictionary attack failed, I used a targeted brute‑force mask:

Code
BlueOceans?d?d?d?d
This brute‑forces only the last four digits, dramatically reducing the keyspace.

Result
Hashcat successfully cracked the password:

Code
36e6fa21a3cf6355817252b951751645:BlueOceans1278
What the Result Means
The brute‑force attack succeeded because the mask matched the password structure.
This demonstrates how targeted masks can crack long passwords efficiently.

Screenshot
Code
![Brute Force Attack](bruteforce.png)
🔐 4. Final Cracked Password Output
What I Did
I used the --show option to display the cracked password from Hashcat’s potfile.

Result
Hashcat displayed:

Code
36e6fa21a3cf6355817252b951751645:BlueOceans1278
What the Result Means
This confirms the password was successfully cracked and stored in Hashcat’s potfile.

Screenshot
Code
![Cracked Password Output](cracked-password.png)
🧠 Summary
Hash created and identified as MD5

Dictionary attack: Failed (Exhausted)

Brute‑force attack: Successful

Final password: BlueOceans1278

Tools used: Hashcat, Kali Linux, VirtualBox

This lab demonstrates practical password‑cracking techniques and the importance of strong, unpredictable passwords.

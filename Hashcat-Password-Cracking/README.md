📘 Hashcat Password Cracking Lab
This repository documents my hands‑on lab using Hashcat to identify, attack, and successfully crack an MD5 password hash using both dictionary and brute‑force methods.

🔍 Hash Identification
I began by identifying the hash type using Hashcat’s built‑in mode reference.
The hash used in this lab:

Code
36e6fa21a3cf6355817252b951751645
Hashcat mode: 0 (MD5)

Screenshot
(![Hash_Identification](screenshots/1_Hash_Identification.png)

📂 Dictionary Attack
I attempted a dictionary attack using the rockyou.txt wordlist.

Result:
The attack completed with:

Code
Status: Exhausted
Recovered: 0/1
This means the password was not found in the dictionary.

Screenshot
(![2 Dictionary attack status Exhausted](screenshots/2_Dictionary_attack_status_Exhausted.png)


🔨 Brute‑Force Attack
Since the dictionary attack failed, I performed a brute‑force attack using a targeted mask based on the known password structure.

Mask used:
Code
BlueOceans?d?d?d?d
This brute‑forced only the last four digits, dramatically reducing the keyspace.

Result:
Hashcat successfully cracked the password:

Code
36e6fa21a3cf6355817252b951751645:BlueOceans1278
Screenshot
Screenshot
(!3 Bruteforce Cracked password](screenshots/3_Bruteforce_Crackedpassword.png)


✅ Final Cracked Password
BlueOceans1278

🧠 Summary
Dictionary attack: Failed (Exhausted)

Brute‑force attack: Successful

Hash type: MD5

(![4 Final show Output](screenshots/4_Final_show_Output.png)

Tools used: Hashcat, Kali Linux, VirtualBox

This lab demonstrates practical password‑cracking techniques and the importance of strong, unpredictable passwords.

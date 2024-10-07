# VulnHub-ICA-1

## Objective
The objective of the VulnHub ICA:1 project was to enhance my cybersecurity skills by completing a Capture The Flag (CTF) challenge. This involved systematically identifying and exploiting vulnerabilities within a virtual machine environment to gain unauthorized access and escalate privileges. The project aimed to develop proficiency in network scanning, vulnerability exploitation, password cracking, and privilege escalation, while utilizing various cybersecurity tools and techniques. Through this exercise, I aimed to demonstrate my ability to apply theoretical knowledge in practical scenarios, effectively analyze security weaknesses, and implement solutions to overcome them.

### Skills Learned
- Enumeration: Identifying open ports and services.
- Exploitation: Using vulnerabilities to gain access.
- Password Cracking: Decoding and cracking password hashes.
- Privilege Escalation: Gaining higher-level access on the system.
- Scripting: Automating tasks with scripts.
- Database Management: Interacting with MySQL databases.

### Tools Used
Nmap: For network scanning and enumeration.

Hydra: For brute-forcing SSH login.

MySQL: For database interaction and dumping credentials.

Base64: For decoding password hashes.

Online Hash Crackers: For cracking MD5 hashes.

Linux Commands: For navigating and manipulating the file system.

Custom Scripts: For exploiting SUID binaries.

## Steps
Scan the Machine:
Use nmap to scan for open ports and services.
nmap -sV <target-ip>

Enumerate Web Application:
Access the web application on port 80 and look for vulnerabilities.

Exploit Web Application:
Find and exploit a vulnerability to gain access to the database credentials.

Dump Database Credentials:
Use MySQL to connect to the database and dump user credentials.
mysql -u <username> -p -h <target-ip>

Decode and Crack Passwords:
Decode the password hashes from Base64 to MD5 and crack them using online tools.

Brute Force SSH Login:
Use Hydra to brute-force SSH login with the cracked credentials.
hydra -l <username> -P <password-list> ssh://<target-ip>

Privilege Escalation:
Find a binary with the SUID bit set and exploit it to gain root access.
Create a fake command in /tmp and modify the PATH variable.
export PATH=/tmp:$PATH

Capture Flags:
Locate and read the flags in the home directories and root directory.

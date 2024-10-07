# VulnHub-ICA-1

## Objective
[Brief Objective - Remove this afterwards]

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

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

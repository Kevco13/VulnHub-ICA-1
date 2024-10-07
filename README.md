# VulnHub-ICA-1

## Objective
[Brief Objective - Remove this afterwards]

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

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

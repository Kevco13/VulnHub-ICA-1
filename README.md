# VulnHub-ICA-1

## Objective
The objective of the VulnHub ICA:1 project was to enhance my cybersecurity skills by completing a Capture The Flag (CTF) challenge. This involved systematically identifying and exploiting vulnerabilities within a virtual machine environment to gain unauthorized access and escalate privileges. The project aimed to develop proficiency in network scanning, vulnerability exploitation, password cracking, and privilege escalation, while utilizing various cybersecurity tools and techniques. Through this exercise, I aimed to demonstrate my ability to apply theoretical knowledge in practical scenarios, effectively analyze security weaknesses, and implement solutions to overcome them.

### Skills Learned
- **Enumeration**: Identifying open ports and services.
- **Exploitation**: Using vulnerabilities to gain access.
- **Password Cracking**: Decoding and cracking password hashes.
- **Privilege Escalation**: Gaining higher-level access on the system.
- **Scripting**: Automating tasks with scripts.
- **Database Management**: Interacting with MySQL databases.

## Tools Used

- **nmap**: Network exploration and security auditing.
- **MySQL**: Open-source relational database management.
- **Hydra**: Fast and flexible login cracker.
- **Nikto**: Web server scanner.

# Penetration Testing Workflow

This guide outlines the steps to perform penetration testing, including scanning, enumerating, exploiting, and privilege escalation.

## 1. Scan the Machine

Use `nmap` to scan for open ports and services.

| Command | Description |
|---------|-------------|
| `nmap -sV <target-ip>` | Scans the target machine for open ports and enumerates services. |

## 2. Enumerate Web Application

Access the web application on port 80. Investigate for potential vulnerabilities using tools like **Nikto** or manual inspection.

## 3. Exploit Web Application

Find and exploit a vulnerability to gain access to the database credentials.

## 4. Dump Database Credentials

Use **MySQL** to connect to the database and dump user credentials.

| Command | Description |
|---------|-------------|
| `mysql -u <username> -p -h <target-ip>` | Connects to the MySQL database on the target machine. |

## 5. Decode and Crack Passwords

Decode the password hashes from **Base64** to **MD5** and crack them using online tools like [CrackStation](https://crackstation.net/).

## 6. Brute Force SSH Login

Use **Hydra** to brute-force SSH login with the cracked credentials.

| Command | Description |
|---------|-------------|
| `hydra -l <username> -P <password-list> ssh://<target-ip>` | Brute-forces SSH login using a wordlist. |

## 7. Privilege Escalation

Search for binaries with the **SUID** bit set, then exploit one to escalate privileges to root. Modify the `PATH` variable to gain further control.

| Command | Description |
|---------|-------------|
| `export PATH=/tmp:$PATH` | Modifies the `PATH` to prioritize custom binaries. |

## 8. Capture Flags

Locate and read the flags in the home directories and root directory. Use the following commands to list files and navigate through directories.

| Command | Description |
|---------|-------------|
| `ls -la /home` | Lists all home directories. |
| `cat /root/flag.txt` | Reads the final flag located in the root directory. |

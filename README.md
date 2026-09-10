# Nmap Network Reconnaissance

## 📌 Project Overview

This project documents hands-on network reconnaissance and vulnerability assessment techniques using Nmap in an authorized lab environment.

The objective is to identify active hosts, discover open ports and services, analyze potential security risks, and document findings using a structured penetration testing methodology.

## 🎯 Objectives

- Perform host discovery
- Identify open ports
- Detect running services and versions
- Perform basic operating system enumeration
- Use Nmap scripts for vulnerability assessment
- Analyze and document security findings
- Recommend remediation strategies

## 🛠️ Tools Used

- Nmap
- Linux
- Virtual Machine
- GitHub

## 🧪 Lab Environment

This project was conducted in an isolated and authorized virtual lab environment.

- **Attacker Machine:** Parrot Security OS
- **Target Machine:** Metasploitable 2
- **Virtualization:** VMware Workstation Pro
- **Network Configuration:** Host-only virtual network
- **Target IP:** 192.168.157.128

All reconnaissance and vulnerability testing was performed exclusively against an intentionally vulnerable system within the local lab environment.

## 🔎 Methodology

### 1. Service and Version Detection

Nmap was used to identify open ports, running services, and service versions on the Metasploitable 2 target.

```bash
nmap -sV 192.168.157.128
```

### 2. Vulnerability Identification

After identifying the FTP service and version, Nmap's scripting engine was used to assess the service for known vulnerabilities.

The scan identified **vsFTPd 2.3.4** as potentially vulnerable to the **vsFTPd 2.3.4 Backdoor Command Execution vulnerability (CVE-2011-2523)**.

The Nmap results reported the service as:

**VULNERABLE (Exploitable)**

This finding was documented for further validation within the authorized lab environment.

### 3. Vulnerability Validation

After Nmap identified vsFTPd 2.3.4 as potentially vulnerable, Metasploit Framework was used to validate the finding within the isolated lab environment.

The Metasploit module identified the FTP banner as vsFTPd 2.3.4 and reported that the target appeared vulnerable. During validation, the backdoor behavior was triggered; however, no interactive session was established.

**Validation Result:** Target appeared vulnerable, but exploitation did not result in an active session.

This outcome was documented accurately rather than reported as a successful compromise.

## 📸 Evidence & Results
### Nmap Service & Version Detection

Nmap identified multiple exposed services and their versions on the Metasploitable 2 target, including vsFTPd 2.3.4 on TCP port 21.

![Nmap Service and Version Detection](screenshots/Screenshot%202026-09-09%20205907.png)

### Nmap Vulnerability Identification

Nmap's scripting engine identified vsFTPd 2.3.4 as vulnerable to the vsFTPd backdoor vulnerability (CVE-2011-2523), reporting the service as **VULNERABLE (Exploitable)**.

![Nmap Vulnerability Identification](screenshots/Screenshot%202026-09-09%20184048.png)

### Metasploit Vulnerability Validation

Metasploit Framework was used to validate the vsFTPd 2.3.4 finding. The target was identified as vulnerable and the backdoor behavior was triggered; however, no active session was established.

![Metasploit Vulnerability Validation](screenshots/Screenshot%202026-09-09%20202655.png)

### Validation Outcome

The validation attempt confirmed that the target appeared vulnerable, but the exploit did not produce an active session. This result demonstrates the importance of documenting both successful and unsuccessful validation attempts accurately.

![Validation Outcome](screenshots/Screenshot%202026-09-09%20202932.png)

## ⚠️ Ethical Use Disclaimer

All scanning and testing performed in this project is conducted in an authorized lab environment for educational purposes only. No systems are tested without permission.

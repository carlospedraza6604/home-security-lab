# 🛡️ Home Security Lab

A personal cybersecurity lab built to develop hands-on offensive and defensive security skills. This project follows a full attack → document → patch → verify cycle on intentionally vulnerable machines to build practical knowledge in penetration testing, vulnerability assessment, and system hardening.

---

## 🎯 Project Goals

- Gain real-world experience exploiting and patching common vulnerabilities
- Build a methodology for vulnerability assessment and remediation
- Document findings clearly to reinforce learning and demonstrate technical depth
- Develop proficiency with industry-standard tools used in security roles

---

## 🖥️ Lab Environment

| Machine | Role | OS |
|---|---|---|
| Kali Linux | Attacker | Debian-based |
| Metasploitable 2 | Vulnerable Target | Linux |
| DVWA | Vulnerable Web App | Linux |
| Windows 11 | Vulnerable Target / Hardening Practice | Windows |

All machines run locally in VirtualBox on a **Host-Only network** — completely isolated from the internet.

### Network Topology

```
Host Machine (Physical PC)
│
├── [Attacker]  Kali Linux       192.168.56.x
├── [Target]    Metasploitable 2  192.168.56.x
├── [Target]    DVWA              192.168.56.x
└── [Target]    Windows 11        192.168.56.x
        │
        └── Host-Only Adapter (no internet access)
```

---

## 🔁 Methodology

Every machine follows this cycle:

```
1. Recon       → Discover open ports, services, and versions
2. Exploit     → Research and execute known vulnerabilities
3. Document    → Record findings, tools used, and impact
4. Patch       → Apply fixes, config changes, and hardening measures
5. Verify      → Re-run exploit to confirm the vulnerability is closed
```

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| `nmap` | Network scanning and enumeration |
| `Metasploit` | Exploit framework |
| `Burp Suite` | Web application testing |
| `Wireshark` | Packet capture and analysis |
| `Netcat` | Manual shells and connections |
| `Hashcat / John the Ripper` | Password cracking |
| `Lynis` | Linux system hardening audits |

---

## 📂 Machine Writeups

| Machine | Status | Key Vulnerabilities Covered |
|---|---|---|
| [Metasploitable 2](./machines/metasploitable2/report.md) | 🟡 In Progress | FTP backdoor, weak SSH, Samba misconfig |
| [DVWA](./machines/dvwa/report.md) | 🔲 Planned | SQLi, XSS, CSRF, File Upload, Command Injection |
| [Windows 11](./machines/windows11/report.md) | 🔲 Planned | RDP exposure, SMBv1, PowerShell abuse, weak credentials |

---

## 📁 Repository Structure

```
home-security-lab/
│
├── README.md
├── lab-setup/
│   ├── setup-notes.md          # How the lab was built
│   └── network-diagram.png     # Visual topology
│
├── machines/
│   ├── metasploitable2/
│   │   ├── report.md
│   │   └── screenshots/
│   ├── dvwa/
│   │   ├── report.md
│   │   └── screenshots/
│   └── windows11/
│       ├── report.md
│       └── screenshots/
│
└── techniques/
    ├── privilege-escalation.md
    ├── sql-injection.md
    └── smb-exploitation.md
```

---

## 📝 Writeup Format

Each machine report follows this structure:

```
## Target: <Machine Name>
Date | IP Address | Difficulty

### Findings
- Port / Service / Version — vulnerability description

### Exploitation
- Tool used, CVE reference, steps taken, outcome

### Patches Applied
- Specific changes made to close each vulnerability

### Verification
- Confirmed attack no longer succeeds — how tested
```

---

## 📌 Techniques Reference

The `/techniques` folder contains notes on attack categories encountered across multiple machines — useful for pattern recognition and interview prep.

- [Privilege Escalation](./techniques/privilege-escalation.md)
- [SQL Injection](./techniques/sql-injection.md)
- [SMB Exploitation](./techniques/smb-exploitation.md)

---

## 🚀 Progress

- [x] Lab environment set up
- [x] Kali Linux configured
- [ ] Metasploitable 2 — full report complete
- [ ] DVWA — full report complete
- [ ] Windows 11 — full report complete
- [ ] 3+ VulnHub boxes documented

---

> *This lab is for educational purposes only. All testing is performed on intentionally vulnerable machines in an isolated local environment.*

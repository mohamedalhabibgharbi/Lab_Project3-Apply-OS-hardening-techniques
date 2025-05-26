# Cybersecurity Incident Report: Brute Force Web Server Compromise

This project presents a detailed security incident report and supporting materials for an event involving a brute force attack on a web server.

## 🧠 Scenario Overview

The website **yummyrecipesforme.com** was compromised by a disgruntled former employee who used a brute force attack to gain administrative access. Once inside, they injected malicious JavaScript into the website source code, prompting users to download and run a disguised malware file. This resulted in a redirect to a fake website (**greatrecipesforme.com**) and ultimately infected visitors' computers.

### Key Actions Taken:
- Captured live network activity using `tcpdump`
- Analyzed the DNS and HTTP traffic
- Documented attack behavior and entry vectors
- Provided remediation strategies to prevent future brute force attacks

---

## 📂 Project Files

| File Name                                    | Description |
|---------------------------------------------|-------------|
| `Security-incident-report-template.docx`     | template |
| `tcpdump-traffic-log.docx`                   | Raw network capture log showing DNS and HTTP request activity during the incident. |
| `How-to-read-the-tcpdump-traffic-log.docx`   | Guide to interpreting `tcpdump` output to trace network activity. |

---

## 🛡️ Remediation Recommendations

**Key defenses implemented:**
- Enforced password complexity requirements
- Introduced regular password expiration
- Enabled Two-Factor Authentication (2FA) for all admin accounts
- Limited login attempts to mitigate brute force strategies

---

## 🧰 Tools Used

- `tcpdump` for packet capture
- Secure sandbox environment for safe analysis
- Internal auditing and manual source code review

---

## 📘 Learning Objectives

This project demonstrates:
- Real-world application of packet analysis
- Protocol tracing across DNS and HTTP
- Cybersecurity incident documentation
- Remediation and risk mitigation strategies

---

## 📌 Important Notes

The files and findings are part of a simulated cybersecurity training scenario and are not based on a real-world compromise.

---

# This lab is from Google Cybersecurity certificate: Cybersecurity Incident Report - Brute-Force Web-Server Compromise

This project presents a detailed incident report and supporting materials for a brute-force attack that compromised **yummyrecipesforme.com**. The attacker planted malicious JavaScript, lured users into downloading malware, and redirected them to a spoofed site (**greatrecipesforme.com**).

---

## 🧠 Scenario Overview
A former employee brute-forced the admin account (default password still active), altered the site’s source code, and delivered malware via an HTTP download prompt. Users who executed the file were silently redirected to a fake domain hosting additional malware.

### Key Actions Taken
- Captured live traffic with `tcpdump`
- Identified DNS → HTTP flow and malware download
- Documented attack vectors and timeline
- Recommended defenses against brute-force attacks

---

## 🔎 Section 1 – Network Protocol Identified
**Hypertext Transfer Protocol (HTTP)**  
The protocol involved in the incident is the Hypertext Transfer Protocol (HTTP). Since the issue was with accessing the web server for yummyrecipesforme.com, we know that requests for web pages use HTTP traffic. When we ran tcpdump and accessed the website, the log file showed the use of the HTTP protocol. The malicious file was seen being sent to users' computers using the HTTP protocol at the application layer.

---

## 📝 Section 2 – Incident Summary
Several customers contacted the website's helpdesk saying that when they visited the site, they were prompted to download and run a file claiming to offer access to new recipes. Since then, their personal computers have been running slowly. The website owner also tried to log into the web server but found they were locked out of their account.
The cybersecurity analyst used a sandbox environment to visit the website without affecting the company network. The analyst then ran tcpdump to capture the network traffic while interacting with the site. The analyst was prompted to download a file claiming to provide free recipes, accepted the download, and ran it. After running the file, the browser redirected to a fake website (greatrecipesforme.com).
The analyst reviewed the tcpdump log and found that the browser first requested the IP address for the yummyrecipesforme.com website. Once the connection was made over the HTTP protocol, the analyst recalled downloading and running the file. The logs showed a sudden shift in network traffic, as the browser then requested the IP address for the greatrecipesforme.com URL. The traffic was rerouted to the new IP address for the fake website.
A senior cybersecurity professional analyzed the source code for both websites and the downloaded file. It was discovered that an attacker had modified the website to include code that prompted users to download a malicious file disguised as a browser update. Since the website owner had been locked out of their admin account, the team believes the attacker used a brute force attack to gain access to the account and change the admin password. Running the malicious file compromised the users’ computers.


---

## 🛡️ Remediation Recommendations
- Enforce strong, unique passwords and prevent reuse of previous or default credentials  
- Enable Two-Factor Authentication (2FA) for all admin accounts  
- Configure account-lockout after repeated failed logins  
- Monitor and alert on unusual login activity

---

## 📂 Project Files

| File Name                                  | Description                                                              |
|-------------------------------------------|--------------------------------------------------------------------------|
| `Security-incident-report-template.docx`  | Completed incident report template                                       |
| `tcpdump-traffic-log.docx`                | Raw network-capture data showing DNS and HTTP activity                   |
| `How-to-read-the-tcpdump-traffic-log.docx`| Guide to interpreting the captured `tcpdump` output                      |

---

## 🧰 Tools Used
- `tcpdump` for packet capture  
- Isolated sandbox VM for safe malware execution  
- Manual log inspection and source-code review

---

## 📘 Learning Objectives
- Apply packet analysis for incident response  
- Map protocols to TCP/IP layers (DNS + HTTP)  
- Produce clear incident documentation  
- Recommend practical security controls

---

## 📌 Important Notes
All data and findings are part of a simulated training scenario; no real user information was exposed.

---

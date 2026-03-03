# Suspicious Indicators in DNS, HTTP, and TCP Traffic

## 📌 Purpose

This document outlines behavioral indicators that may suggest malicious or abnormal activity when analyzing network traffic using Wireshark.

The focus is on DNS, HTTP, and TCP protocols from a SOC / blue-team perspective.

---

# 🔴 DNS Suspicious Indicators

## 1️⃣ Repeated NXDOMAIN Responses
- Multiple DNS queries returning `NXDOMAIN`
- May indicate Domain Generation Algorithm (DGA) activity
- Possible failed Command & Control (C2) lookups

---

## 2️⃣ High-Frequency Repeated Queries
- Same domain queried repeatedly within short intervals
- Could indicate beaconing behavior from infected host

---

## 3️⃣ Random or High-Entropy Subdomains
Example: ajd83jd92j3k2.example.com

- Long, random-looking strings
- Possible DNS tunneling or encoded data exfiltration

---

## 4️⃣ Excessive TXT Record Usage
Filter: dns.qry.type == 16

- Large or repeated TXT responses
- Possible data exfiltration via DNS

---

## 5️⃣ Unusual DNS Resolver IP
- Queries sent to unknown external IP instead of ISP or known DNS server
- May indicate malware-configured DNS server

---

# 🔴 HTTP Suspicious Indicators

## 1️⃣ Unexpected File Downloads
- `.exe`, `.zip`, `.dll`, `.js` downloads
- `application/octet-stream` content type
- Possible malware payload delivery

---

## 2️⃣ Suspicious URI Paths
Examples:
/gate.php

/update.exe

/shell.php

- Often used in exploit kits or C2 infrastructure

---

## 3️⃣ Abnormal POST Requests
- Large POST payloads to unknown domains
- May indicate data exfiltration

---

## 4️⃣ Communication to Raw IP Addresses
- HTTP requests made directly to IP instead of domain
- Common in malicious infrastructure

---

## 5️⃣ Strange or Missing User-Agent
- Empty or uncommon User-Agent strings
- Often used by malware or automated tools

---

# 🔴 TCP Suspicious Indicators

## 1️⃣ Multiple SYN Packets Without Completion
Filter: tcp.flags.syn == 1 and tcp.flags.ack == 0
- May indicate port scanning or reconnaissance

---

## 2️⃣ Excessive RST Packets
Filter: tcp.flags.reset == 1

- Could indicate blocked scanning activity
- Possible firewall rejection of malicious traffic

---

## 3️⃣ Large Number of Short-Lived Connections
- Rapid connect → disconnect patterns
- Possible brute force or automated scanning

---

## 4️⃣ Connections to Unusual Ports
- Outbound traffic to high or uncommon ports
- Possible Command & Control communication

---

# 🧠 Analyst Reminder

Suspicious behavior is not defined by a single packet, but by patterns and context.

When analyzing traffic, always ask:

- Is this expected?
- Is the frequency normal?
- Is the destination legitimate?
- Does this behavior align with standard application usage?

Understanding normal traffic behavior is essential before identifying anomalies.

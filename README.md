# Wireshark Network Traffic Analysis

## 📌 Overview

This repository documents hands-on packet analysis using Wireshark from a blue-team perspective.

The focus is on inspecting real network traffic, understanding protocol behavior at packet level, and identifying suspicious or abnormal activity through PCAP investigations.

Networking theory (OSI, TCP/IP, ports, etc.) is covered separately. This repository emphasizes practical packet-level analysis.

---

## 🎯 Objectives

- Analyze PCAP files using Wireshark
- Understand how common protocols appear in packet captures
- Identify abnormal traffic patterns
- Simulate SOC-style investigations
- Develop packet-level threat detection skills

---

## 🔍 Protocol Analysis Covered

- HTTP traffic inspection
- DNS query analysis
- TCP handshake & flag behavior
- ICMP traffic patterns
- Port-based traffic filtering

Each protocol section includes:
- Relevant Wireshark filters
- Normal traffic behavior
- Suspicious indicators
- SOC relevance

---

## 🧪 PCAP Investigations

Each investigation includes:

- Objective
- Methodology
- Observations
- Analysis
- Potential Indicators of Compromise (IOCs)
- Conclusion

The goal is to simulate real-world network investigation scenarios.

---

## 🛠 Tools Used

- Wireshark
- Public PCAP datasets
- Network display filters
- Traffic statistics analysis

---

## 🧠 SOC Relevance

Packet-level visibility is critical for:

- Detecting reconnaissance activity
- Identifying brute-force attempts
- Recognizing suspicious outbound connections
- Investigating potential C2 communication
- Supporting incident response workflows

This repository builds foundational skills required for SOC and blue-team roles.

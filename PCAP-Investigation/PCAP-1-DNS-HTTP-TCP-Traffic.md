# PCAP 1 - Basic HTTP & DNS Traffic Analysis

## 🎯 Objective

Analyze a sample PCAP file to understand normal HTTP and DNS traffic behavior and identify any suspicious patterns.

---

## 🛠 Methodology

1. Opened the PCAP file in Wireshark.
2. Applied protocol filters to isolate traffic.
3. Observed packet details including source IP, destination IP, ports, and payload information.

Filters used:

DNS: dns

HTTP: http

TCP: tcp

---

## 🔎 Observations

### DNS Traffic
<img width="1843" height="507" alt="dns" src="https://github.com/user-attachments/assets/4b4453a6-1116-4a45-bb5d-4dcf11553ddb" />

Each DNS query had a corresponding response.

No incomplete or hanging queries observed.

Standard query/response pattern maintained.



### HTTP Traffic
<img width="1337" height="330" alt="http" src="https://github.com/user-attachments/assets/37a0a014-4d72-4d0f-9a03-36ba1ba9eede" />
HTTP traffic consists of standard GET requests followed by 200 OK responses. 

No suspicious URIs, file downloads, or abnormal request methods were identified.

Traffic appears consistent with normal web browsing activity.

### TCP Behavior
<img width="1706" height="896" alt="tcp" src="https://github.com/user-attachments/assets/297e665f-b60b-4c27-be9a-87600dd716ff" />

Observed proper TCP three-way handshake (SYN → SYN-ACK → ACK).

HTTP GET request initiated after connection establishment.

Server responded with expected HTTP response.

Connection terminated cleanly using FIN/ACK sequence.

No abnormal TCP flag behavior detected.


---

## 🧠 Analysis

The DNS, HTTP, and TCP traffic collectively reflect expected client-server communication patterns. 

- DNS queries resolved successfully with no abnormal repetition or failed lookups.
- HTTP sessions consisted of standard GET requests followed by 200 OK responses.
- TCP connections were established and terminated cleanly using proper handshake and FIN/ACK sequences.

---

## ✅ Conclusion

The analyzed PCAP demonstrates normal web browsing activity. All observed network protocols (DNS, HTTP, and TCP) behaved as expected without evidence of scanning, payload delivery, command-and-control activity, or abnormal connection patterns.

This exercise establishes a baseline understanding of legitimate network behavior for future comparison against suspicious traffic.






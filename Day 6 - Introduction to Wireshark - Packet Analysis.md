
## 🎯 **Objective**  
The objective of this lab is to introduce **Wireshark**, a powerful packet analysis tool used by SOC analysts to investigate network traffic. By the end of this lab, I will learn the interface, how to capture packets, apply filters, and identify suspicious communication patterns.

## Lab Setup
**System Requirements**
- **Operating System:** Windows, Linux, or macOS
- **Network Adapter:** Required for packet capture

**Software Required**
- [Wireshark](https://www.wireshark.org/download.html) (latest stable version)
- [Download Sample PCAP file](https://github.com/0xrajneesh/90-Days-SOC-Challenge-Beginner/raw/refs/heads/main/Protocol_Analysis_pcap.pcapng)


## What is Wireshark?

**Wireshark** is an open-source network protocol analyzer that lets you capture and interactively browse network traffic. It allows analysts to view data packets flowing in and out of a system in real time or from saved PCAP files.

## Wireshark Use Cases for SOC Analysts

- **Incident Investigation:** Analyze malicious traffic patterns (e.g., C2 communication, lateral movement)
- **Malware Analysis:** Extract indicators like domains, IPs, and payloads from suspicious network behavior
- **Threat Hunting:** Detect anomalies like DNS tunneling, beaconing, or unauthorized FTP/SSH usage
- **Protocol Troubleshooting:** Identify service failures, misconfigurations, or latency issues



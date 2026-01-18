
## Objective
The objective of this lab is to introduce students to analyzing TCP (Transmission Control Protocol) traffic using Wireshark. By the end of this lab, I will learn how TCP establishes connections, the 3-way handshake process, and how to interpret common TCP fields and flags.

## Lab Setup
**System Requirements**
- **Operating System:** Windows 10/11 (or Linux/macOS)
- **Software:** Wireshark (latest version)

**Files Needed**
- [Download Sample PCAP file](https://github.com/0xrajneesh/90-Days-SOC-Challenge-Beginner/raw/refs/heads/main/Protocol_Analysis_pcap.pcapng)

## TCP Packet Structure and Fields
TCP is a **Layer 4 (Transport Layer)** protocol that ensures reliable, ordered, and error-checked delivery of data between applications.

 **Key TCP Fields:**

| Field Name         | Description                                  |
|--------------------|----------------------------------------------|
| **Source Port**     | Sender’s port number                         |
| **Destination Port**| Receiver’s port number                       |
| **Sequence Number** | Number of the first byte in the segment      |
| **Acknowledgment No** | Confirms received data                    |
| **Flags**           | Control bits (SYN, ACK, FIN, RST, PSH, URG) |
| **Window Size**     | Buffer size available                        |
| **Checksum**        | Error-checking field                         |


## Most Common TCP Display Filters
Use these filters in Wireshark’s Display Filter bar:

| Filter                  | Description                              |
|--------------------------|------------------------------------------|
| `tcp`                   | Show all TCP packets                     |
| `tcp.flags.syn == 1`    | Show SYN packets (start of connection)   |
| `tcp.flags.fin == 1`    | Show FIN packets (end of connection)     |
| `tcp.port == 80`        | Show TCP packets on port 80              |
| `ip.addr == 192.168.1.1`| TCP traffic to/from a specific host      |


## Conclusion
- TCP ensures reliable and ordered data delivery through its 3-way handshake and flow control.
- Understanding TCP flags is essential for:
 - Connection state tracking
 - Troubleshooting dropped or reset connections
 - Detecting scanning and abnormal behavior (e.g., RST floods)

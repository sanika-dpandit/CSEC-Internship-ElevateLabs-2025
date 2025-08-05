# wireshark-packet-analysis
# Task 5: Capture and Analyze Network Traffic Using Wireshark

Objective
The goal of this task was to perform a live packet capture using Wireshark, identify different network protocols, and develop hands-on skills in protocol analysis and network troubleshooting.

Tools Used
Wireshark
Operating System
Browser/Command Line: Used to generate HTTP, DNS, and TCP traffic

Steps Followed

1. Installed and opened Wireshark.
2. Started capturing packets on the active network interface.
3. Generated traffic by:
   - Visiting websites using a web browser (to capture HTTP traffic).
   - Running `ping google.com` (to capture ICMP and DNS traffic).
4. Stopped the capture after approximately one minute.
5. Used protocol filters (`http`, `dns`, `tcp`) to isolate specific traffic.
6. Saved the capture file as `network_capture.pcapng`.
7. Analyzed packets to identify and summarize at least three protocols.

Protocols Identified
HTTP (HyperText Transfer Protocol)
-Port: 80 (TCP)
- Description: Used for loading web pages from servers to browsers. The HTTP GET and response packets were visible, showing unencrypted content including URLs and headers.

DNS (Domain Name System)
-Port: 53 (UDP)
-Description: DNS queries were sent to resolve domain names (e.g., `google.com`) into IP addresses. Responses returned the mapped IPs.

TCP (Transmission Control Protocol)
- Ports: Varying (common: 80, 443)
- Description: TCP is a reliable, connection-oriented protocol. The 3-way handshake (SYN, SYN-ACK, ACK) was visible, establishing connections for both HTTP and DNS traffic.

Summary

This task helped build foundational skills in using Wireshark for real-time packet analysis. By analyzing captured traffic, I learned to recognize different protocols, interpret network behavior, and understand the structure of DNS, HTTP, and TCP packets. These skills are essential for troubleshooting network issues and conducting cybersecurity investigations.

Useful Filters Used
http
dns
tcp
tcp.port == 80
udp.port == 53

Extra Research Insight
Wireshark is one of the most powerful tools for real-time packet analysis, widely used in both cybersecurity investigations and routine network troubleshooting. One of its key strengths lies in its ability to visually dissect packets layer-by-layer—from the Ethernet frame to the transport and application layers. This granularity makes it ideal for spotting anomalies, detecting malicious behavior, and learning protocol structure.

A packet is a formatted unit of data carried by a network. Each packet includes headers (protocol-specific metadata like source/destination IP, ports, sequence numbers) and payload (actual data).

While analyzing my capture, I observed how protocols work together: for example, how DNS (UDP) resolves the domain, and TCP carries HTTP traffic once a site is accessed. Protocol filters like http, tcp.port == 443, and udp.port == 53 made isolating specific flows easy. However, Wireshark cannot decrypt encrypted protocols like HTTPS (port 443) unless the private key is available and SSL debug logging is enabled.

Packet capture is also incredibly useful for diagnosing issues like latency, dropped packets, and connection resets by examining the TCP 3-way handshake, retransmissions, or ICMP errors.

Interview Q&A Summary (written as informative text)
Wireshark is a packet sniffer and network protocol analyzer used to inspect real-time traffic across a network interface. It's commonly used in cybersecurity, network diagnostics, and protocol learning. It allows users to view all packets sent or received and filter based on protocols or endpoints.

A packet is a small segment of data sent over a network. It typically contains headers (which define routing and control information) and a payload (the actual data being transmitted).

Filtering in Wireshark is essential when dealing with large volumes of captured traffic. Filters like http, dns, or expressions like tcp.port == 443 help focus on relevant packets.

TCP and UDP are two transport layer protocols. TCP is connection-oriented, reliable, and performs handshakes (SYN, SYN-ACK, ACK), ensuring data is delivered in order. UDP is connectionless, faster, and doesn't guarantee delivery, making it suitable for streaming or DNS queries.

A DNS query packet is a request sent from a client to a DNS server to resolve a domain name into an IP address. This usually occurs over UDP port 53.

Packet capture aids troubleshooting by allowing engineers to trace connection flows, examine retransmissions, and pinpoint causes of failures like timeouts or misconfigurations.

A protocol is a set of rules governing how data is transmitted over a network. Examples include HTTP (web), FTP (file transfer), and ICMP (ping).

Wireshark can capture encrypted traffic, but it cannot decrypt it without proper keys or setup (e.g., SSL key logging). Therefore, only protocol headers are visible for encrypted data, not the actual payload.

Nmap Network Scan Task

Objective
To perform a TCP SYN scan using Nmap and analyze network exposure and open ports on the local network.

Tools Used
- Nmap for port scanning
- Wireshark for packet capture and analysis

Files Included
- `scan_results.txt` – Text output of the Nmap scan
- `scan_results.xml` – XML format of the Nmap scan
- `scan_results.html` – HTML report (converted from XML)
- `nmap_scan_capture.pcapng` – Packet capture of the scan

Observations
- Hosts up: `192.168.91.1`, `192.168.91.144`
- Open ports found: 135, 139, 445, 902, 912, 3306, 5357

Security Risks Identified
| Port | Service         | Risk Description                                                                 |

| 135  | msrpc           | Can be used for lateral movement in Windows environments                         |
| 139  | netbios-ssn     | Exposes legacy Windows file sharing services                                     |
| 445  | microsoft-ds    | Vulnerable to SMB exploits like EternalBlue; commonly abused by ransomware       |
| 902  | iss-realsecure  | Used by VMware; could expose remote console access                               |
| 912  | apex-mesh       | Unknown service; needs investigation; could be a custom/legacy component         |
| 3306 | mysql           | Database should not be exposed to the network without strong access controls     |
| 5357 | wsdapi          | Windows device discovery protocol; often unnecessary in secure environments      |

Recommendations
- Use firewall rules to restrict access to unnecessary ports.
- Disable unneeded services (e.g., SMB, NetBIOS).
- Protect MySQL with authentication, SSL, and network restrictions.
- Investigate unknown services like `apex-mesh` and disable if not used.
- Monitor and log port activity regularly.

Wireshark Analysis
Captured TCP SYN packets (filtered using `tcp.flags.syn == 1 && tcp.flags.ack == 0`) showed the scanner sending connection attempts to various IPs and ports.
This confirms the behavior of a typical TCP SYN scan, where the scanner sends SYN packets and waits for SYN-ACK responses.

--Beyond the Basics: Stealth Scanning and Intrusion Detection Evasion
While TCP SYN scanning (-sS) is a popular method due to its speed and relatively stealthy nature (as it doesn't complete the TCP handshake), it can still be detected by modern Intrusion Detection Systems (IDS) and firewalls. To evade such detection, attackers may use fragmented packets, decoy scans, or timing variations (slow scans). Nmap supports advanced evasion options such as:

-f for fragmenting packets,

--scan-delay to slow down scans,

-D to generate decoy IPs.

This knowledge is essential not only for ethical hackers performing red teaming but also for defenders configuring IDS tools like Snort or Suricata to detect and respond to stealthy port scans.

Real-World Relevance:
Understanding how attackers modify scans to bypass detection helps security professionals design better defensive strategies and alert rules in security monitoring tools.

## Interview Q&A Summary
Open ports are essentially communication endpoints that accept connections from external sources. While they are necessary for services like web servers or databases, they can also become security risks if misconfigured or exposed unnecessarily. This is why understanding how port scanning tools like Nmap work is critical.

Nmap’s TCP SYN scan technique works by sending a SYN (synchronize) packet to a target port. If the port is open, the host replies with a SYN-ACK, indicating it's ready to establish a connection. Rather than completing the handshake, Nmap immediately sends a reset (RST) packet, making the scan stealthy and less likely to be logged compared to a full TCP connection.

The presence of open ports can expose a system to various threats. For example, attackers may exploit services running on those ports or use them as a foothold to move laterally within a network. Therefore, it's crucial to close unnecessary ports, restrict access using firewalls, and regularly audit services.

TCP scanning is generally more reliable than UDP scanning because TCP includes connection responses that confirm port status. In contrast, UDP is connectionless and doesn’t guarantee a response, making results harder to interpret and increasing the chance of false negatives. Both types of scans are valuable in different contexts.

To secure open ports, administrators should disable unused services, configure firewalls to limit exposure, and enable intrusion detection systems to monitor suspicious traffic. Regular patching and access controls also help minimize risk.

Firewalls play a key role in network security by filtering traffic based on rules, allowing or denying connections to specific ports. They help enforce the principle of least privilege and reduce the network’s attack surface.

Port scanning itself is a reconnaissance technique used by attackers to discover vulnerable services. By identifying which ports are open and which services are running, attackers can tailor their strategies to exploit known vulnerabilities. Ethical hackers and defenders use the same technique to strengthen security by identifying and mitigating risks early.

Wireshark complements port scanning by allowing analysts to inspect packet-level traffic in real time. During a scan, it can confirm whether SYN, SYN-ACK, and RST packets were exchanged as expected, verify scan timing, and detect whether a system is silently dropping or responding to probe attempts. This makes Wireshark invaluable for validating scan results and understanding network behavior at a granular level.

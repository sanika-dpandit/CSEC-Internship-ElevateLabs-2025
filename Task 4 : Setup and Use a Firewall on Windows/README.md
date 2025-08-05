# firewall-configuration-task
Task 4: Setup and Use a Firewall on Windows/Linux

Objective
Configure and test basic firewall rules to allow or block traffic using UFW (Linux) and Windows Defender Firewall.

Steps Performed
Linux (UFW)
- Enabled UFW
- Listed current rules
- Blocked port 23 (Telnet)
- Allowed port 22 (SSH)
- Tested rules
- Removed test rules

Windows Firewall
- Opened firewall tool
- Created new inbound rule to block port 23
- Tested using Telnet client
- Removed the rule

  Extra Research Insight
During this task, I explored how modern firewalls integrate with both network-level controls and application-layer policies, making them essential tools for layered security. In Linux, UFW serves as a user-friendly interface to iptables, greatly simplifying command syntax for basic rule management. It is especially useful in small environments or personal systems. On Windows, the Defender Firewall allows granular control over inbound and outbound rules based on port, program, or protocol.

One key realization was the risk of misconfiguration—for example, accidentally blocking essential services or leaving high-risk ports like Telnet (23) open. It's also important to consider that firewalls are most effective when used in conjunction with other tools, like IDS/IPS and endpoint protection. Stateful firewalls, which track session information, are particularly effective in today's dynamic network environments. Finally, I learned how Network Address Translation (NAT) is often tied to firewalls in routers, allowing internal systems to access the internet using a single external IP while hiding internal IP addresses from public exposure.

Firewall Interview Q&A Summary
A firewall is a security mechanism that monitors and filters incoming and outgoing network traffic based on predetermined rules. It acts as a barrier between a trusted internal network and untrusted external sources, helping to prevent unauthorized access and attacks. Firewalls can be either hardware-based (as in routers) or software-based (like UFW or Windows Firewall), and modern systems often use both for layered protection.

There are two main types: stateful and stateless. A stateful firewall tracks the state of active connections and makes decisions based on the context of traffic (e.g., allowing response packets), whereas a stateless one treats each packet in isolation, which can lead to more rigid and error-prone filtering.

Inbound rules control which external connections are allowed into the system (like allowing SSH on port 22), while outbound rules determine what internal processes can reach the outside world. Tools like UFW simplify firewall management by abstracting complex iptables syntax into readable commands like ufw deny 23/tcp or ufw allow 22/tcp.

Blocking Telnet (port 23) is a standard security measure because Telnet transmits credentials in plaintext, making it an easy target for attackers using packet sniffers. Instead, secure alternatives like SSH (port 22) should be used.

Common firewall mistakes include leaving unnecessary ports open, misconfiguring default rules, forgetting to test changes, or creating overly permissive rules that defeat the firewall’s purpose. Firewalls improve network security by limiting attack surfaces, controlling access, and preventing unauthorized lateral movement within networks.

Lastly, NAT (Network Address Translation) in firewalls allows multiple devices on a private network to share a single public IP address, while also providing a layer of obfuscation from external attackers. NAT often works hand-in-hand with firewall rules to both conserve IPs and enhance security.

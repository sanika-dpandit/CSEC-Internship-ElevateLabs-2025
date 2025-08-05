## Task 4: Setup and Use a Firewall on Windows/Linux

**Objective:**  
Gain hands-on experience configuring basic firewall rules to allow or block network traffic using either Windows Firewall or UFW (Uncomplicated Firewall) on Linux.

### Tools Used:
- **UFW** (Uncomplicated Firewall on Linux)  
  _or_  
- **Windows Defender Firewall** (on Windows OS)

### What I Did:
- Listed current firewall rules using terminal commands (Linux) or GUI (Windows)
- Added a rule to **block incoming traffic** on a specific port (e.g., port 23 for Telnet)
- Verified that the block was working using local connection tests
- Configured a rule to **allow SSH (port 22)** if applicable
- Removed the test rule after verification to restore default state
- Documented the commands used and included screenshots of the firewall settings

### Learning Outcomes:
- Understood how firewalls control incoming and outgoing traffic
- Learned how to apply rules for specific ports using both GUI and command-line tools
- Gained awareness of **network security principles** like port management and service exposure
- Practiced safe testing and rollback of firewall rules

### Key Concepts Covered:
`Firewall Rules`, `Inbound vs Outbound Traffic`, `UFW`, `Windows Firewall`, `Port Blocking`, `SSH`, `Telnet`, `Traffic Filtering`, `Stateful vs Stateless Firewalls`

### Reflection Questions I Explored:
- What’s the difference between **stateful** and **stateless** firewalls?
- Why is port 23 commonly blocked in modern systems?
- How does a firewall differ from antivirus or intrusion detection systems?
- What are some risks of misconfigured firewall rules?
- What role does NAT (Network Address Translation) play in firewall security?


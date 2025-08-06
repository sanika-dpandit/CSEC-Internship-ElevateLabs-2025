# vpn-privacy-task

Overview
This task involved gaining hands-on experience with a Virtual Private Network (VPN) and understanding its role in protecting user privacy. It also included identifying and removing suspicious browser extensions to enhance digital security.


Tools Used
- VPN Client: Riseup VPN (Free, No Signup Required)
- Browser: Google Chrome
- IP Test Site: [whatismyipaddress.com](https://whatismyipaddress.com)


VPN Setup Steps
1. Downloaded Riseup VPN from [https://riseup.net/en/vpn](https://riseup.net/en/vpn).
2. Installed the client and connected to the default VPN server.
3. Verified IP change using [whatismyipaddress.com].
4. Ensured traffic encryption by browsing HTTPS-secured sites (e.g., DuckDuckGo).
5. Disconnected the VPN and compared browsing speed and IP address again.

VPN Research Summary
 What is a VPN?
A VPN (Virtual Private Network) is a service that creates a secure, encrypted connection over the internet by routing your traffic through a remote server. It hides your IP address and protects your data from surveillance or interception.

How Does It Protect Privacy?
- IP masking: Hides your real IP and shows the VPN server’s IP.
- Encryption: Secures your data from eavesdropping on public or insecure networks.
- Traffic tunneling: Prevents ISPs, advertisers, and attackers from tracking online activity.

VPN vs. Proxy
- VPN: Encrypts all device traffic, more secure, slower due to encryption.
- Proxy: Routes traffic for specific apps or browsers only, no encryption.

What is Encryption in VPN?
Encryption scrambles data during transmission. VPNs use encryption protocols like OpenVPN, IKEv2, or in Riseup’s case, LEAP (LEAP Encryption Access Protocol), to prevent interception or snooping.

Can a VPN Guarantee Complete Anonymity?
No. A VPN hides your IP but doesn't anonymize everything. Websites can still track you via cookies, browser fingerprinting, or account logins.

VPN Protocols Used
- Common protocols: OpenVPN, WireGuard, IKEv2/IPSec
- Riseup VPN uses LEAP protocol, designed for secure communication with minimal setup.

VPN Limitations
- Slight decrease in browsing speed due to encryption.
- May not bypass all geo-restrictions or censorship.
- Doesn’t protect against malware or phishing.

Impact on Network Speed
VPNs can slow down speed slightly because:
- Data is encrypted and routed through remote servers.
- Server distance and load also affect performance.

  Beyond the Basics: VPNs vs Deep Packet Inspection (DPI)
In regions with heavy censorship, governments and ISPs often use Deep Packet Inspection (DPI) to identify and block VPN traffic. Advanced VPNs like Riseup use obfuscation techniques to disguise VPN data as regular HTTPS traffic, making it harder for DPI systems to detect or throttle it. This capability is crucial for activists, journalists, and individuals in restrictive regimes, allowing them to bypass censorship and communicate freely. VPNs thus serve not only as privacy tools but also as enablers of digital rights and freedom of expression.

Conclusion
This task demonstrated the importance of VPNs in securing online activity and the need to regularly audit browser extensions for security hygiene. Using Riseup VPN provided a quick and effective way to understand VPN functionality without requiring account creation or configuration.

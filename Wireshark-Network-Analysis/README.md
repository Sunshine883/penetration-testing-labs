Wireshark – Network Packet Analysis Lab
This lab demonstrates my ability to capture, filter, inspect, and interpret network traffic using Wireshark, one of the most widely used tools for network forensics, SOC analysis, and packet‑level troubleshooting.

Objectives
Capture live network traffic

Apply display filters to isolate specific protocols

Analyze packet structure (Ethernet, IP, TCP/UDP, ICMP, HTTP, DNS, etc.)

Interpret protocol behavior and communication patterns

Identify anomalies or suspicious activity

Document findings clearly and professionally

Environment
Kali Linux (VM)

Wireshark v3.x or v4.x

Network Interface: eth0 (VM NAT or Bridged)

Sample PCAPs: HTTP, DNS, ICMP, ARP (from Wireshark sample captures or lab traffic)

Workflow & Techniques Used
1. Opening a PCAP or Starting a Capture
Launch Wireshark

Select interface:

Code
eth0
OR open a saved capture:

Code
File → Open → sample.pcap
2. Applying Display Filters
Common filters used in this lab:

Code
http
dns
icmp
tcp
udp
arp
ip.addr == <target-ip>
tcp.port == 80
These filters isolate specific traffic types for deeper inspection.

3. Packet Structure Analysis
For each packet, I examined:

Frame (capture metadata)

Ethernet II (MAC addresses)

Internet Protocol (IP)

Source/Destination

TTL

Flags

Transport Layer

TCP flags (SYN, ACK, FIN)

UDP headers

Application Layer

HTTP GET/POST

DNS queries/responses

ICMP echo requests/replies

4. Protocol‑Specific Analysis
HTTP Traffic
Identified GET and POST requests

Viewed full request/response details

Followed TCP streams to reconstruct conversations

DNS Traffic
Analyzed query types (A, AAAA, NS)

Observed response codes

Identified domain resolution patterns

ICMP Traffic
Echo request/reply behavior

TTL values

Round‑trip timing

ARP Traffic
Mapped IP → MAC relationships

Observed ARP broadcasts and replies

Findings
(You will fill this in after you redo the lab.)

Examples of what to include:

HTTP request paths and server responses

DNS domains queried

ICMP echo patterns

Suspicious or malformed packets

Unexpected ports or traffic types

Screenshots
Screenshots are stored in:

![HTTP GET Request](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Wireshark-Network-Analysis/Wireshark-Network-Analysis/screenshots/1%20Opening%20a%20PCAP%20.jpg?raw=true)





![DNS Query](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Wireshark-Network-Analysis/Wireshark-Network-Analysis/screenshots/2%20Starting%20a%20Capture.jpg?raw=true)





![ICMP Echo Reply](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Wireshark-Network-Analysis/Wireshark-Network-Analysis/screenshots/3%20Applying%20Display%20Filters.jpg?raw=true)




![ARP Broadcast](https://github.com/Sunshine883/penetration-testing-labs/blob/main/Wireshark-Network-Analysis/Wireshark-Network-Analysis/screenshots/4%20Location%20of%20screen%20shots.jpg?raw=true)


Code
/screenshots/
Include:

Filtered views (http, dns, icmp, arp)

Packet Details pane expanded

Follow TCP Stream output

Any anomalies or interesting packets

Example Markdown format for your README:

Code

Conclusion
This lab demonstrates my ability to use Wireshark for packet‑level analysis, protocol inspection, and network forensics. It highlights essential SOC and blue‑team skills such as filtering traffic, interpreting protocol behavior, identifying anomalies, and documenting findings clearly.

Wireshark – Network Traffic Analysis Lab
This lab demonstrates my ability to capture, inspect, and analyze network traffic using Wireshark, one of the most widely used packet analysis tools in cybersecurity. The exercises include opening packet capture files, performing live captures, and applying display filters to isolate relevant traffic.

Objectives
Open and analyze packet capture (PCAP) files

Perform live packet captures

Apply Wireshark display filters to isolate protocols

Interpret packet details and network behavior

Document findings clearly and professionally

Environment
Tool: Wireshark (Kali Linux VM)

Traffic Source: Sample PCAP files + live capture

Network: Host‑only / isolated virtual lab


1. Opening a PCAP File
Wireshark allows analysts to open existing packet capture files for offline analysis.
This step demonstrates loading a PCAP and viewing the packet list, details, and byte pane.

screenshot location
![Opening a PCAP](screenshots/1_Opening_a_PCAP.jpg)

2. Starting a Live Capture
A live capture is performed by selecting a network interface and beginning packet collection.
This step shows Wireshark capturing real‑time traffic on the selected interface.

screenshot location
![Starting a Capture](screenshots/2_Starting_a_capture.jpg)

3. Applying Display Filters
Display filters allow analysts to isolate specific protocols or traffic patterns.
Examples include:

http

dns

icmp

tcp.port == 80

ip.addr == <target-ip>

This step demonstrates applying filters to narrow down the packet view.

screenshot location
![Applying Display Filters](screenshots/3_Applying_display_filters.jpg)

Common Filters Used in This Lab
![Common Filters Used in Lab](screenshots/Common_filters_used_in_lab.jpg)


Findings
Wireshark successfully captured and displayed network traffic.

Display filters allowed precise isolation of HTTP, DNS, and ICMP packets.

Packet details revealed source/destination IPs, ports, flags, and protocol behavior.

The PCAP analysis confirmed expected traffic patterns in the lab environment.

Conclusion
This lab demonstrates foundational network analysis skills using Wireshark, including opening PCAP files, performing live captures, and applying display filters. These skills are essential for SOC analysts, penetration testers, and anyone working in network security.

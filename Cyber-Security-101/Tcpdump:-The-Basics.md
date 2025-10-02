# Tcpdump: The Basics
[Cyber Security 101 - Tcpdump: The Basics](https://tryhackme.com/room/tcpdump)

<img width="699" height="353" alt="image" src="https://github.com/user-attachments/assets/3f5961cc-c3f9-4eb4-a300-990f00d31e5e" />


## Key Points
- Tcpdump is a tool to capture traffic, it's kind of similiar to wireshark.
- Some useful commands (Tcpdump):
  1. ip address show (ip a s) would list the available network interfaces.
  2. 'tcpdump w FILE' will capture the current traffic to a .pcap file, which can be open via Wireshark.
  3. 'tcpdump -r FILE' to read packets from a file
  4. 'tcpdump -c COUNT' specify the number of packets to capture.
  5. '-n' argument will will avoid resolving IP addresses and printing friendly domain.
  6. '-v' to produce a slightly more verbose output.
- Capturing DNS traffic can be done by putting a limit to the captured packtes ex. 'sudo tcpdump -i ens5 port 53 -n'. Filtering by protocol can be done by putting our desired protocol ex. 'sudo tcpdump -i ens5 icmp -n'.
- 

## Answers
1. libpcap
2. -n
3. 26 (tcdump -r traffic.pcap icmp -n | wc)
4. 192.168.124.148 (tcpdump -r traffic.pcap arp -n)
5. mirrors.rockylinux.org (tcpdump -r traffic.pcap port 53 -n)
6. 57 (tcpdump -r traffic.pcap 'tcp[tcpflags] == tcp-rst' -n | wc
7. 185.117.80.53 ( tcpdump -r traffic.pcap 'greate 15000' -n
8. 52:54:00:7c:d3:5b (tcpdump -r traffic.pcap arp -e

## Conclusion
Tcpdump is one of the best tool for understanding or analyzing networking protocols. Tcpdump commands can be easy but It can be really complicated too, it's a very powerful tool.

<img width="1329" height="696" alt="image" src="https://github.com/user-attachments/assets/6f997847-ce59-4080-a737-ef40344fc5a7" />


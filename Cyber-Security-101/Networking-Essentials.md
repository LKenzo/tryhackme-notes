# Networking Essentials
[Cybersecurity 101 - Networking Essenstials Note](https://tryhackme.com/room/networkingessentials)

<img width="1428" height="785" alt="image" src="https://github.com/user-attachments/assets/04140d9b-15c2-425a-8b30-6ea9f77b62c1" />

## Key Points
- DHCP assigns IP automatically.
- DHCP relies on UDP (port 67/68).
- Wireshark can capture DHCP packets.
- ARP can find MAC address of another device on the Ethernet.
- Important ICMP commands: `ping` and `traceroute`.
- Few routing protocols:
    1. OSPF (Open Shortest Path First) : A porotocol that allows routers to share information and calculate the most efficient paths for data transmission.
    2. EIGRP (ENchance Interior Gateway Routing Protocol) : Cisco propietary routing protocol. EIGRP, a porotocol that combines aspect of different routing algorithms, it allows routers to share informations (bandwith or delay).
    3. BGP (Border Gateway Protocol) : Primary routing protocol used on the Internet. Allows different networks to exchange routing information and establish paths for data to travel.
    4. RIP (Routing Information Protocol) : Often used in small networks. RIP share router information about the number of hops required to send the package. Each router builds a routing table based on the information (fewest hops).
- NAT provide internet access to many private IP addresses by using one public IP address.

## Questions Answers
1. 4
2. 255.255.255.255
3. 0.0.0.0
4. ff:ff:ff:ff:ff:ff
5. 44:df:65:d8:fe:6c
6. 40
7. TTL
8. EIGRP
9. 212.3.4.5
10. 65 (Limited by the number of TCP port numbers 65535)
11. THM{computer_is_happy}

  ## Conclusion
  This room introduced me to various protocols that we constantly use directly or indirectly. There are various protocols such as ICMP, DHCP, ARP, NAT, and even routing has its own protocols.
  <img width="1854" height="764" alt="image" src="https://github.com/user-attachments/assets/1eb3773c-f8dc-48c0-8417-80b7e051b4e1" />

  

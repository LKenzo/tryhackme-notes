# Nmap: The Basics
[Cyber Security 101 - Nmap: The Basics]
(https://tryhackme.com/room/nmap)

<img width="920" height="509" alt="image" src="https://github.com/user-attachments/assets/456edad5-f516-42c1-bf02-2c986ad49be4" />


## Key Points
- Nmap is a tool that scans other live devices and network services that are running on the network.
- Nmap offers options to scan TCP and UDP by using '-sT' and '-sU'
- You can limit the target ports by using '-p[range]'
- Using '-O' to detect the OS and '-sV' to detect version.
<img width="884" height="459" alt="image" src="https://github.com/user-attachments/assets/7e6b085a-2b5c-40c4-9d96-ef820e22363d" />
- Number of parallel probes can be controlled with '--min-parallelism <numprobes>' and '--max-parallelism <numprobes>'. Useful if network is performing poorly or flawlessly. same as '--min-rate <number>' and '--max-rate <number>'.
- To get more updates about the scan Enable verbose '-v' . There are levels on verbose if you're not satisfied '-v2' and '-v4' or '-vv' and '-vvvv'.
- To debug use '-d', there are levels on debugging, the maximum level is '-d9'.
- 

## Answers
1. 192.168.0.31 (nmap -sL 192.168.0.1/27)
2. 6 (nmap -sT 10.201.127.199)
3. THM{SECRET_PAGE_38B9P} (nmap -sT 10.201.127.199) -> 10.201.127.199:8008
4. lighttpd 1.4.74 (nmap -sV -p 8008 10.201.65.20)
5. -T aggressive
6. -d
7. connect scan (-sT)

## Conclusion
In this room i learned a lot on how to use Nmap to discover live hosts on the network. I learned about port scanning and how to find service version number. 

<img width="1558" height="745" alt="image" src="https://github.com/user-attachments/assets/6b4fc6af-3b56-419a-bb96-f7e5d188a4b0" />


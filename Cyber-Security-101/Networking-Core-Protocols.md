# Networking Core Protocols
[Cybersecurity 101 - Networking Core Protocols Note](https://tryhackme.com/room/networkingcoreprotocols)

<img width="885" height="534" alt="image" src="https://github.com/user-attachments/assets/d64e496d-b116-410d-b17e-36d942075855" />

## Key Points
- DNS is responsible for properly mapping a domain name to an IP address and the otherway around.
-  DNS traffic uses UDP as default and TCP as fallback (port 53).
-  DNS has many types of record four of them are A Record, AAAA Record, CNAME Record, and MX Record.
-  Using nslookup to look up the IP address.
-  WHOIS is an internet protocol that records infromation about registered domain name.
-  HTTP and HTTPS commonly uses TCP ports 80 and 443, less commonly 8080 and 8443.
-  FTP is very efficient for file transfer it's faster than HTTP (TCP 21).
-  SMTP is the protocol used for sending email and POP3 for retrieving email (SMTP: TCP 25 and POP3: TCP 110).
-  IMAP is better for checking email via multiple clients, this is because IMAP doesn't instantly delete email after downloaded (POP3) and IMAP synchornized email acrros the email clients(TCP 143).

## Questions Answers
1. AAAA
2. MX
3. 1993-04-02 (whois x.com)
4. 2000-01-21 (whois twitter.com)
5. THM{TELNET-HTTP} (telnet 10.201.22.54 80)
6. THM{FAST-FTP} (ftp 10.201.22.54)
7. Data
8. .
9. Dovecot
10. THM{TELNET_RETR_EMAIL}
11. FETCH 4 body[]

## Conclusion
In this room I learn more about other fundamental protocols such as DNS, HTTP, FTP, SMTP, POP3, and lastly IMAP. By using telnet command with the proper port like 80 for HTTP and so on, I can learn many things about the protocol and the usage of it.

<img width="1624" height="700" alt="image" src="https://github.com/user-attachments/assets/fa38b6c1-3851-4bc3-85e6-a089fbe3f6f2" />

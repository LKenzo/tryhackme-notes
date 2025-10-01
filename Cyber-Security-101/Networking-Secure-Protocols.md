# Networking Secure Protocols
[Cyber Security 101 - Networking Secure Protocols]
(https://tryhackme.com/room/networkingsecureprotocols)

<img width="663" height="432" alt="image" src="https://github.com/user-attachments/assets/19d75b5d-9345-405c-a5a7-ecfb0c4aab53" />


## Key Points
- TLS is a cryptographic protocol ooperating in transport layer, it allows secure communication over an insecure network.
- HTTP over TLS is called HTTPS (443), it's a much more secured version of HTTP.
- Adding TLS to SMTP, POP3, and IMAP
  SMTP (25) -> SMTPS (465 and 587)
  POP3 (110) -> POP3S (995)
  IMAP (143) -> IMAPS (993)
- SSH (22) is a much secure way to login and administer remote system.
- SFTP (22) uses SSH to allow secure file transfer and FTPS (990) uses TLS.
- VPN is is a secure, encrypted tunnel for internet data to travel through, masking the real IP.

## Answers
1. SSL
2. self-signed certificate
3. 8
4. 10
5. IMAP
6. OpenSSH
7. THM{Protocols_secur3d}
8. VPN
9. THM{B8WM6P}

## Conclusion 
Security is very important, whitout it we can't communicate. In this room i learned 3 secure network traffic TLS, SSH, and VPN. TLS is used to secure protocols, such as HTTP, SMTP, POP3, and IMAP. SSH is used for remote acces, transfering files securely, and establishing secure tunnels. While VPN is used for hiding the real IP or connecting two company branches.

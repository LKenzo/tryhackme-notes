# John The Ripper: The Basics
[Cyber Security 101 - John The Ripper: The Basics](https://tryhackme.com/room/johntheripperbasics)

<img width="1329" height="466" alt="image" src="https://github.com/user-attachments/assets/3192b70f-96d8-4517-a3c3-200671087902" />

## Key Points
- John The Ripper uses dictionary attack. A dictionary attack is where you hash a large number of words using the hashing algorithm, then compare the hashes to the one you're trying to crack.
ex. usage
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt

- Use tool like hash-identifier if John fails. Hash identifier will tell you what different types of hashes the one you enter is likely to be.
ex. usage
python3 hash-id.txt 

Hash: 1A732667F3917C0F4AA98BB13011B9090C6F8065
Output: SHA-1, MySQL5

- NThash is the hash format modern Windows operating system machines use to store user and service password (NTLM is the previous version)

- /etc/shadow is the file on Linux where password hashes are stored.
- user unshadow to locate a file in /etc/shadow

1A732667F3917C0F4AA98BB13011B9090C6F8065 SHA-1, MySQL5
D7F4D3CCEE7ACD3DD7FAD3AC2BE2AAE9C44F4E9B7FB802D73136D4C53920140A SHA-256, Haval-256
c5a60cc6bbba781c601c5402755ae1044bbf45b78d1183cbf2ca1c865b6c792cf3c6b87791344986c8a832a0f9ca8d0b4afd3d9421a149d57075e1b4e93f90bf SHA-512, Whirlpool

## Answers
1. Jumbo John
2. rockyou.com
3. md5
4. biscuit
5. SHA1
6. kangeroo
7. SHA256
8. microphone
9. whirlpool
10. colossal
11. mushroom
12. 1234
13. Jok3r
--------------------------------
14. Password complexity predictability
15. Az"[A-Z]"
16. --rule=THMRules
17. pass123
18. THM{w3ll_d0n3_h4sh_r0y4l}
19. password
20. THM{r4r_4rch1ve5_th15_t1m3}
21. mango

## Conclusion
John the Ripper is huge. I learned that John the Ripper is one of the most important tool to learn in encryption, even the basics is kind of hard for me. But all of that aside it's a very nice room and I learn many things about John the Ripper.

<img width="1149" height="680" alt="image" src="https://github.com/user-attachments/assets/78614f05-9a88-42d6-83dd-e302b615d1c7" />

# Public Key Cryptography Basics
[Cyber Security 101 - Public Key Cryptogrpahy Basics](https://tryhackme.com/room/publickeycrypto)

<img width="1140" height="800" alt="image" src="https://github.com/user-attachments/assets/6e5d7f3c-49b8-4b2d-8b8d-3ecaa3fbd38a" />


## Key Points
- Cryptography provides solutions to satifsy Authentication, Authenticity, Integrity, and Confidentiality.
  1. Authentication: You want to be sure you communicate with the right person, not someone else pretending.
  2. Authenticity: You can verify that the information comes from the claimed source.
  3. Integrity: You must ensure that no one changes the data you exchange.
  4. Confidentiality: You want to prevent an unauthorised party from eavesdropping on your conversations.
- The Analogy of Symmetric Key, first ask your friend for a lock (The friend has the key to unlocked it), then your friend send you that lock. Second After recieving the lock, you can send a message to your friend with that lock. After it was sent, your friend can unlock the lock with his key so he can retrieve the message that you sent.

Secret Code = Symmetric Encryption Cipher and Key
Lock = Public key
Lock's Key = Private key

- RSA is a public-key encryption that enables secure data transmission.
- To create RSA you need two large of prime numbers and multiply both of them. It's easier to multiply two large prime numbers then finding the factors. ex.

Prime number 1: 982451653031
Prime number 2: 169743212279
Their product: 982451653031 × 169743212279 = 166764499494295486767649

- Diffie-Hellman Key Exchange similiar to RSA but uses mod to exchange key without revealing it to the public.
- PGP, it's software that implements encryption for encryping files, performing digital signing, and more. GPG is commonly used in email to protect the confidentiality and confirm its integrity.
- Recommended tools **RsaCtfTool, John The Ripper, and gpgp2john**.

## Answers
1. Lock
2. 29239669 (4391 x 6659)
3. 29228620 (29239669 - 4391 - 6659 + 1)
4. 7 (5^12 mod 29)
5. 9 (5^17 mod 29)
6. 24 (9^12 mod 29)
7. 24 (7^17 mod 29)
8. RSA
9. Certificate
10. Let's Encrypt
11. Pineapple (gpg --import tryhackme.key -> gpg --decrypt message.gpg)

## Conclusion
Cryptography is huge and there are a lot of algorithms of securing communication out there. Cryptography is one of most interesting room here in TryHackMe, I get to learn many things here.

<img width="1346" height="672" alt="image" src="https://github.com/user-attachments/assets/fe95f0be-a598-4498-b1ff-b60fbe5c2091" />

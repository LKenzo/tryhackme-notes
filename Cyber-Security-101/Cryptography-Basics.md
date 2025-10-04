# Cryptographic Basics
[Cybersecurity 101 - Cryptographic Basics](https://tryhackme.com/room/cryptographybasics)

<img width="835" height="453" alt="image" src="https://github.com/user-attachments/assets/d00429a4-1fec-4938-a174-0a9a0829b55f" />


## Key Points
- Cryptography is the reason why we can exhange data securely.
- Cryptography is used to protect confidentiality, integrity, and authenticity.
- PCI DSS ensures a minimum level of security to store, process, and transmit data related to credit cards.
- Caesar Cipher:
It moves the leters, so A->D, B->E, C->F, and so on.
<img width="1031" height="440" alt="image" src="https://github.com/user-attachments/assets/fa50c5cb-f8cc-4765-8c5e-5b64e515ec17" />
From that image we get the cipher text as **WUBKDFNPH**, and the **key = 3** (Because it moves 3 letters).
<img width="1027" height="435" alt="image" src="https://github.com/user-attachments/assets/b5d04102-86f4-4aba-b519-a7f3eaabf4c6" />
For encryption we shift to the right by three, while for decryption we shift to left by three to recover the original plaintext.
<img width="1800" height="660" alt="image" src="https://github.com/user-attachments/assets/3a86c7bd-a94c-447d-9a64-0c1c8c83c2df" />
- Symmetric Encryption uses the same key to encrypt and decrypt the data.
<img width="1840" height="1040" alt="image" src="https://github.com/user-attachments/assets/003269ee-625c-43b0-b3ab-052241224214" />
- Assymetric Encryption uses a pair of keys, one to encrypt and the other to decrypt.
<img width="1840" height="1040" alt="image" src="https://github.com/user-attachments/assets/c148789b-d98e-4019-a989-f9b4ad73d92b" />
Data encrypted with the public key can be decrypted with the private key. Assymetric encryption is based on a particular group of mathematical problems that are easy to compute in one direction but extremely difficult to reverse.
- XOR can be used as a basic symmetric encryption algorithm.
P = Plain text
C = Cipher text
K = Key

C = P ⊕ K
If we want to recover P, we need to know C and K. Let's start,
C = P ⊕ K
C ⊕ K = (P ⊕ K) ⊕ K
C ⊕ K = P ⊕ (K ⊕ K) -> (K ⊕ K) = 0
C ⊕ K = P ⊕ 0
C ⊕ K = P

- Modulo is another mathematical operation we often encounter in cryptography.

## Answers
1. PCI DSS
2. Ciphertext
3. decryption
4. ICANENCRYPT (The text was shifted to left by 15)
5. Nay
6. 2001
7. 0011
8. 3565
9. 0

## Conclusion
In this room I learned about the importance of cryptography in this world, it solves many problems and without it there will be no secure network. I find cryptography to be quite intresting and I can't wait to learn about more in the next room.

<img width="1425" height="755" alt="image" src="https://github.com/user-attachments/assets/d417f6f2-924f-4ccf-9fd5-b5be77cc676a" />

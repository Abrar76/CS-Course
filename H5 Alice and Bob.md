# x) Read and summarize

Schneier explain public‑key cryptography as a two‑key system enabling secure encryption, authentication, and digital signatures, built on hard mathematical problems and used to solve trust and key‑distribution challenges in modern communication. 

Public key cryptography is defined by Schneier as a system where each participant has two mathematically linked keys:

Public key that can be shared openly
Private key that must remain secret

The only essential property is asymmetry where one key encrypts and only the other can decrypt. Schneier emphasizes that this asymmetry enables capabilities impossible with symmetric cryptography alone. Which is one‑way functions and easy to invert only with special information. Schneier emphasizes that in practice it is used to exchange symmetric session keys but not to encrypt large data directly. Digital signatures are one of the most important applications in Schneier’s treatment. It also explain, Security depends on key length, algorithm choice, and proper implementation.

Hybrid Cryptosystems
Public‑key cryptography is computationally expensive. Schneier describes the standard hybrid model:
Use public‑key encryption to protect a random session key.
Use symmetric encryption (fast) for the actual message.
Digital signature → authenticate sender + ensure integrity.

This is the basis of PGP, TLS, SSH, and most modern systems. Vulnerable to man‑in‑the‑middle attacks if public keys aren’t authenticated. 


# a) Pubkey today

A public‑key process is built on asymmetric key pairs: a public key that anyone may use and a private key that only the owner keeps secret. Senders use the recipient’s public key to encrypt or verify, while recipients use their own private key to decrypt or sign, and key‑exchange protocols may add ephemeral keys for short‑lived shared secrets. These keys are mathematically linked but used for opposite operations: encryption vs. decryption or signing vs. verification. Below under is the process detail.

1. Sender encrypts using the recipient’s public key.
In public‑key encryption, anyone can encrypt a message using the recipient’s public key
Only the recipient, who holds the private key, can decrypt the ciphertext.
This stage ensures confidentiality: even if the public key is widely distributed, only the private key holder can read the message.

2. Recipient decrypts using their private key.
The recipient uses their private key to invert the trapdoor one‑way function and recover the plaintext.
The security of the system depends on keeping this private key secret.

3. Sender signs using their private key.
The sender signs a message using their private key. Anyone can verify the signature using the sender’s public key.

4. Receiver verifies using the sender’s public key.
Verification uses the public signature verification key. This confirms the message has not been modified and identifies the sender.

5. Key‑exchange uses both parties’ public keys and private keys.
Protocols like Diffie–Hellman use key pairs differently. Each party generates a public/private key pair and exchanges public keys. Using their private key and the other party’s public key, they compute a shared secret. This shared secret becomes a symmetric key for faster encryption in hybrid systems such as TLS.

6. Ephemeral keys for forward secrecy.
. Long‑term asymmetric keys for identity and signing
. Ephemeral keys for short‑lived sessions, ensuring that compromising a long‑term private key does not reveal past communications.

In public‑key cryptography, public keys are shared openly and used by others to encrypt messages or verify digital signatures, while private keys are kept secret and used to decrypt messages intended for you or to create digital signatures that prove authenticity. Encryption + decryption provide confidentiality, and signing + verification provide authenticity and integrity. In key‑exchange protocols, each party combines their private key with the other party’s public key to derive a shared secret for secure communication.


# b) Encrypt and decrypt a message. Explain how different parties use different keys at different stages of operation.

Encryption transforms plaintext into unreadable ciphertext by using a key, and decryption reverses the process using the appropriate key either by the same key (symmetric) or a mathematically related key pair (asymmetric).

The method and technique of keeping the messages secure is called cryptography. Along with confidentiality, it also offers non-repudiation, authentication, and integrity. Along with the algorithm, plaintext, ciphertext, and keys, a cryptosystem is also given. Algorithms used in cryptography, often known as ciphers, are mathematical operations that are used for encryption and decoding. It is a limited algorithm if the algorithm's security is kept a secret. A key is used for both encryption and decryption in modern cryptography methods. Cryptosystem is an algorithm system with all possible plain text, keys and ciphertexts.

There are actually two primary kinds of encryption. Steganography is the practice of hiding messages with other messages. Transposition encryption keys: Same plaintext, but characters are in a different order.

The security of algorithms depends on how difficult it is to break them; there are various types of breaking. Break total, subtract globally, deduct instances, subtract information. Data complexity, computational complexity, and storage needs can all be used to gauge how complicated an attack could be.

# How Different Parties Use Keys at Each Stage
Asymmetric Example: Sending a confidential message
1.	Bob generates a key pair:
•	Public key (shared)
•	Private key (secret) 
2.	Alice wants to send Bob a message:
•	he encrypts using Bob’s public key.
3.	Bob receives the ciphertext:
4.	He decrypts by using his private key.
Now only Bob can decrypt because only he has the private key.

Symmetric Example: Sending a message with symmetric encryption
1.	Alice and Bob share a secret key (via secure exchange).
2.	Alice encrypts using the shared key.
3.	Bob decrypts using the same key.
When symmetric keys must be shared securely, protocols like Diffie–Hellman allow two parties to derive a shared secret without sending the key directly.
•	Alice and Bob exchange public values.
•	Each uses their private value plus the other’s public value to compute the same shared secret. This shared secret becomes the symmetric key.
Even if an attacker sees the exchanged public values, they cannot compute the private values.

Hybrid Encryption
Modern systems combine both methods:
1.	Asymmetric encryption is used to securely exchange a symmetric key.
2.	Symmetric encryption is used for the actual data (fast and efficient) 
 



# c) Password management. Demonstrate use of a password manager. What kind of attacks take advantage of people not using password managers?

A password manager is an app that stores your passwords, so you don't need to remember them. Once you've logged into the password manager using a 'master' password, it will generate and remember your passwords for all your online accounts. 
A password manager is similar to a top-secret digital key system that protects our keys, simplifies our lives online, and increases security. Creating a Master Password is the first and most important step. The password manager does not keep a copy of this. Then The password manager assists in generating a secure and unique key each time we create a new online account. The password manager safely stores these unique keys. Thus, in order to open the password manager anytime we need to log in to a certain account, we must supply the Master key.
Password managers are safe to use, and that's a fact that not only the vast majority of cyber-security specialists agree with, but we do as well. After all, a password manager uses advanced encryption to protect your credentials, while without it, your passwords might be accessible.

## Use of password manager, 
A password manager helps us to create a strong and unique passwords which reducing risks from attacks like phishing, brute force, credential stuffing, and keylogging. 

Password manager is a secure application that stores all your login credentials in an encrypted vault which is protected by one master password. It aloso help to:
. Generate strong, unique passwords automatically
. Auto‑fill credentials so you don’t type them manually and reducing exposure to keyloggers.
. Securely sync passwords across devices and Apps.
. Warn us about weak or reused passwords.
. It Enable multi‑factor authentication (MFA) for the password manager.

## What kind of attacks take advantage of people not using password managers
. Credential Stuffing: Attackers reuse stolen username/password pairs from breaches, hoping users will reused them elsewhere.

. Password Spraying : Attackers try common passwords like ABC or 123456 across many other accounts while a unique and complex passwords stop this entirely.

. Brute Force & Dictionary Attacks : Weak or predictable passwords are easily guessed through automated tools.

. Phishing : Phishing tricks users into entering passwords on fake sites while password managers auto‑fill only on a legitimate domains which helping us to avoid entering credentials on fraudulent pages.

. Keylogging : Keyloggers record typed passwords while password manager reduce typing which lowering exposure.




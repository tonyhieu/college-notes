---
toc: true
layout: post
description: ICS 6D Chapter 9.6-9.9
categories: [ics6d, reading, winter22-23, markdown]
title: Bases, Fast Exponentiation, and Cryptography
use-math: true
---

## 9.6: Number representation

- Our number system is in the decimal (base 10 system), but other **bases** exist
    - Digits in binary notation (base 2 system) are called **bits**
- Writing a number n in another base b is known as the **base b expansion of n**
- **Hexadecimal or hex** notation is base 16 and uses the first 10 digits as well as A-F for 10-15 to represent a single digit
    - You can easily convert binary to decimal and back by separating a binary number into groups of 4 bits: ![image](https://user-images.githubusercontent.com/54915685/222292480-efba3f20-60af-403a-ae4d-e434f2a5ae30.png)
    - **Bytes**, which consist of 8 bits, can be represented by a 2-digit hex number
- To convert a decimal number to a base b, repeatedly divide that number by the highest power of b as possible and count the number of times you do so
    - Example: ![image](https://user-images.githubusercontent.com/54915685/222292738-330e5e0d-982a-417c-988b-b02d93be1491.png)
- To find the number of digits in a base b required to represent a number, take the log base b of that number and round it up
    - For example, 14 requires 4 digits because log2 of 14 = 3.8 -> 4

## 9.7: Fast exponentiation

- To simply calculate an exponent, you can repeatedly multiply by itself
- A faster method of exponentiation can be used by repeatedly squaring a number and adding the squares together
    - Steps to exponentiate with only squares: ![image](https://user-images.githubusercontent.com/54915685/222293102-f4505227-6fb7-403e-a9b9-66ba8278eb06.png)
    - Algorithm for fast exponentiation: ![image](https://user-images.githubusercontent.com/54915685/222293240-64cfd5e2-6fd1-4a66-ba6d-13284190eb08.png)
- We can also use fast exponentiation in order to calculate modulus operators for exponents: ![image](https://user-images.githubusercontent.com/54915685/222293318-2088fce6-fca2-4e42-af0f-e1da7b8b8225.png)

## 9.8: Introduction to cryptography

- **Cryptography** is the study behind protecting and authenticating data and communication
    - A cryptosystem is a system where a **sender** **encrypts** a message to a **receiver**
    - The message before encryption is known as the **plaintext** and after encryption is known as the **ciphertext**
    - The receiver must use a **secret key** to **decrypt** the ciphertext
- A common practice is to convert a text message to a number by giving each character a corresponding two digit number: ![image](https://user-images.githubusercontent.com/54915685/222294040-27ac1c5b-6fca-4f87-bb5d-b8455c3945fc.png)
- A simple cryptosystem is one where all plaintexts are between 0 to N-1 for some integer N and the receiver + sender have a secret number k inside of this range
    - To encrypt a plaintext m, the sender computes $$ {c = (m + k) \text{ mod } N} $$
    - To decrypt a ciphertext c, the receiver computes $$ {m = (c - k) \text{ mod } N} $$
    - This is an example of **symmetric key cryptography** where both the sender and receive meet in advance to agree on the shared secret key
    - Requirements for a simply encryption scheme: ![image](https://user-images.githubusercontent.com/54915685/222294551-57996319-fd0a-49ff-a1d7-feb59e9bfb1d.png)

## 9.9: The RSA cryptosystem

- **Public key cryptography** is stronger than the previous simple cryptosystem, as simple cryptosystems can easily cracked
    - In a public key cryptosystem, the receiver has both a **public key** that senders use to encrypt messages as well as a **private key** to decrypt them
    - Difficult to figure out the private key
- The preparation of public and private keys makes it difficult to figure out how the system was prepared but easy to prepare it
- Steps to an RSA system:
    1. Select two large prime numbers, p and q
    2. Compute N = pq and Φ = (p-1)(q-1)
    3. Find an integer e such that gcd(Φ, e) = 1 (AKA e is relatively prime to Φ)
    4. Computer the multiplicative inverse d of e mod Φ; in other words, an integer d such that ed mod Φ = 1
    5. The public keys for encryption are N and e
    6. The private key for decryption is d
- To encrypt a message m, compute $$ {c = m^e \text{ mod } N} $$
- To decrypt a ciphertext c, compute $$ {m = c^d \text{ mod } N} $$
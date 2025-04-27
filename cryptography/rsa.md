# Asymmetric Encryption

Asymmetric encryption, also known as **public-key cryptography**, is a type of encryption that uses a pair of keys: a **public key** and a **private key**. These keys are mathematically related, but it is computationally infeasible to derive the private key from the public key.

## Key Concepts:
- **Public Key**: This key is publicly shared and can be distributed freely. It is used to encrypt data.
- **Private Key**: This key is kept secret by the owner and is used to decrypt data encrypted with the corresponding public key.

## How It Works:

1. **Encryption**:
   - Alice wants to send Bob a secure message.
   - Alice uses Bob's **public key** to encrypt the message.
   - The encrypted message is sent over the network.

2. **Decryption**:
   - Bob receives the encrypted message.
   - Bob uses his **private key** to decrypt the message and read it.

## Advantages of Asymmetric Encryption:
- **Confidentiality**: Only the recipient can decrypt the message, ensuring privacy.
- **Authentication**: Since only the private key holder can decrypt the message, it provides a way to authenticate the sender if they use their private key to sign a message.
- **Key Distribution**: Public keys can be freely distributed, so there's no need for a secure channel to exchange keys beforehand.

## Common Algorithms:
- **RSA (Rivest-Shamir-Adleman)**: One of the first widely used public-key encryption algorithms.
- **ECC (Elliptic Curve Cryptography)**: Uses elliptic curves to create keys that are more efficient and provide the same level of security as RSA but with shorter key sizes.
- **DSA (Digital Signature Algorithm)**: Primarily used for digital signatures.

## let's try an example
- let's generate a private key 
- You will not share the private key 
  
  ```bash
  openssl genrsa -out private.pem 2048 
  ```
- let's generate a public key
- send him/her who want to send the message to you ,he will encrypt his message with public key
  ```bash
  openssl rsa -in private.pem -pubout -out  public.pem 
  ```
- let's encrypt the msg.txt to a encryted message cipher.txt
- he will send you the encrypted message to you
  ```bash
  openssl pkeyutl -encrypt -in msg.txt -out cipher.txt -inkey public.pem -pubin
  ```

- let's decrypt the cipher.txt to decode.txt 
- this message cann't decrypt without the private key 
  ```bash
   openssl pkeyutl -decrypt -in cipher.txt -out decode.txt -inkey private.pem
  ```
- thus you never share this key to anyone so nobody will be able to decrypt the message 

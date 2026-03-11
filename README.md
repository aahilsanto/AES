# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:

AES is based on a design principle known as a substitution–permutation.

AES does not use a Feistel network like DES, it uses variant of Rijndael.

It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.

AES operates on a 4 × 4 column-major order array of bytes, termed the state

# PROGRAM:

```python
def encrypt(text, key):
    encrypted = ""
    for i in range(len(text)):
        val = (ord(text[i]) + ord(key[i % len(key)])) % 256
        encrypted += chr(val)
    return encrypted


def decrypt(cipher, key):
    decrypted = ""
    for i in range(len(cipher)):
        val = (ord(cipher[i]) - ord(key[i % len(key)])) % 256
        decrypted += chr(val)
    return decrypted

# Main program
url = input("Enter URL to encrypt: ")
key = input("Enter secret key: ")

cipher = encrypt(url, key)

print("Encrypted URL (hex):")
for c in cipher:
    print(format(ord(c), "02X"), end=" ")
print()

plain = decrypt(cipher, key)
print("Decrypted URL:", plain)
```
# OUTPUT:

<img width="671" height="210" alt="image" src="https://github.com/user-attachments/assets/bcd0c7eb-adb3-4525-ae8b-fe5e5bc327de" />

# RESULT:

Thus the program to implement Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is executed successfully.


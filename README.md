# Encryption/Decryption Project
Encryption/Decryption Project that I coded in my ITSS 4381 course. 

# Summary

This Python script provides a simple implementation of a substitution cipher for encrypting and decrypting messages. It utilizes the `random` and `string` modules to create a shuffled key for substitution.

# How the Code Works

1. **Initialization**: 
   - The code imports the `random` and `string` modules.
   - It creates a string `chars` that contains a combination of space, punctuation, digits, and letters (both uppercase and lowercase) using `string.punctuation`, `string.digits`, and `string.ascii_letters`.
   - It converts the `chars` string into a list.
   - It creates a copy of the `chars` list named `key`.

2. **Key Shuffling**:
   - The code shuffles the `key` list using the `random.shuffle()` function. This shuffling ensures that each character in `chars` is mapped to a random character in `key`, forming the basis of the substitution cipher.

3. **Encryption**:
   - The code prompts the user to input a message to encrypt using `input()`.
   - It initializes an empty string `cipher_text` to store the encrypted message.
   - It iterates through each character in the input message.
   - For each character, it finds the index of that character in the `chars` list.
   - It retrieves the character at the corresponding index in the `key` list and appends it to the `cipher_text`.
   - Finally, it prints the original and encrypted messages.

4. **Decryption**:
   - The code prompts the user to input a message to decrypt.
   - It initializes an empty string `plain_text` to store the decrypted message.
   - It iterates through each character in the input cipher text.
   - For each character, it finds the index of that character in the `key` list.
   - It retrieves the character at the corresponding index in the `chars` list and appends it to the `plain_text`.
   - Finally, it prints the encrypted and decrypted messages.

This code implements a basic substitution cipher, where each character in the original message is replaced by a corresponding character from the shuffled `key`, and vice versa for decryption. However, note that this implementation is not suitable for secure communication as it relies on a simple substitution method that can be easily cracked. It is primarily intended for educational purposes.


## Usage

1. Run the script in a Python environment.
2. Enter a message to encrypt when prompted.
3. The script will display both the original and encrypted messages.
4. For decryption, enter the encrypted message when prompted.
5. The script will then display the decrypted message.

## Code Snippet

```python
import random
import string 

chars = " " + string.punctuation + string.digits + string.ascii_letters
chars = list(chars)
key = chars.copy()

random.shuffle(key)

print(f"chars: {chars}")
print(f"key : {key}")

#ENCRYPT
plain_text = input("Enter a message to encrypt: ")
cipher_text = ""

for letter in plain_text:
    index = chars.index(letter)
    cipher_text += key[index]

print(f"original message: {plain_text}")
print(f"encrypted message: {cipher_text}")

#DECRYPT
cipher_text = input("Enter a message to encrypt: ")
plain_text = ""

for letter in cipher_text:
    index = key.index(letter)
    plain_text += chars[index]

print(f"encrypted message: {cipher_text}")
print(f"original message: {plain_text}")


```
## Output

```python
Enter a message to encrypt: [user-input]
original message: [user-input]
encrypted message: [corresponding encrypted message]

Enter a message to decrypt: [user-input]
encrypted message: [user-input]
original message: [corresponding decrypted message]

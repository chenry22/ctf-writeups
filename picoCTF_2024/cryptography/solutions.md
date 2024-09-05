### Index
- [***Back to Main***](/)
- [interencdec](#interencdec)

### interencdec
- We are provided an ASCII text file which contains an encoded string in Base64 (you can tell by the == at the end of the string)
- Decoding this, we find a new message that is also Base64 encoded! Decoding this second layer in the same way, we get `wpjvJAM{jhlzhy_k3jy9wa3k_86kl32k2}`, which seems to be in the form of some shift cipher (it is in the form of `picoCTF{flag}`, but needs to be shifted some amount). Again using some cryptography resource, we find that shifting the string by 19 decrypts our flag!
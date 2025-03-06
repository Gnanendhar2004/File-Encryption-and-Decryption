# data-leakage-prevention
Fall Semester 2021-22 Project for VIT College

## Modules of the Project

### MainPage:
Main page or welcome page is the first module of the project which gets the input from the 
user whether he/she wants encrypt or decrypt the file.

### ToBeEncryptedOrDecrypted:
Action java file which implements from the user choice to decrypt or encrypt the file.

### FileEncryptor:
Java executable file to encrypt the file.

### FileDecryptor:
Java executable file to decrypt the file.

### FileChooser:
This module initiates the process of selecting any files of user choice for encryption or 
decryption.

### PasswordTakerForEncryption:
A password security to be provided by the file owner before the encryption process.

### PasswordTakerForDecryption:
Using hashing algorithm of SHA-512 for password security authentication to go for the 
decryption process.

### SourceFileNotDeletedDuringEncryption:
Checking module, If the selected file is present or not in the selected location for 
encryption.

### SourceFileNotDeletedDuringDecryption:
Checking module, If the selected file is present or not in the selected location for 
decryption

## Algorithms


### MODIFICATIONS IN VIGENERE CIPHER

The primary weakness of the Vigenère cipher is the repeating nature of its key, so if the 
period of key is greater than plaintext we can increase the security of Vigenere cipher. To 
increase the period of key the length of Vigenere key needs to be enlarged. If we choose a 
long key, it is harder to remember and also its transmission through a secure channel is 
expensive. A novel approach is presented by combing the LFSR key with Vigenere cipher 
key. Paper introduces the cipher system which exploits the advantages of Vigenere cipher 
with LFSR based stream ciphers and mitigates the weaknesses of these individual ciphers. 
This system generates large key from short keyword using LFSR concept. Here plaintext 
is encrypted with large and pseudorandom letter generated key which flatten the letter 
frequencies of cipher text. So, it will more difficult to identify the length of the key. Since 
period of this Cipher is large enough and also the key stream is pseudorandom letters 
leading to decrease the effectiveness of Kasiski and Index of Coincidence (IC) attacks.
Another method for modifying the Vigenere Cipher algorithm, by automatically changing 
the cipher key after each encryption step. In this method the key varies as it is used in the 
encryption process and the successive keys that will be dependent on the initial key value. 
The second step key will be as a result of a function that operated on the first step (initial 
key) and so forth. As the key varies after each successive encryption that eliminating the 
repeating nature of the key as in conventional Vigenere Cipher. The ciphertext will have 
different encryption key pattern so the cryptosystem will be more difficult against the
frequency attack.
Currently there are several good cryptographic algorithms like AES and DES. And these 
algorithms utilize the two factors needed for a cryptographically secure algorithm, 
confusion and diffusion. Confusion means making the correlation between the cipher text 
and plain text as complex as possible. Diffusion is used to mask the statistical properties 
of the data by spreading it throughout the cipher text. Stream ciphers, like Vigenère and 
Caesar require only one round. Vigenère cipher is very good at the confusion aspect of the 
cryptography, but they lack the benefit of diffusion. By adding a few bits of random 
padding to each byte before the message are encrypted using Vigenère, one can add the 
benefit of diffusion. The number of random bits is determined by a one-way function, F(x), 

consisting of a prime p, a generator g less than p and a positive constant less than eight c. 
The message length should be less than p to prevent the possible detection of cycles.
F(x) = (g x + c) mod p,
where x represents the nth character of a message. Each byte has been padded and it is 
concatenated to the last bit of the previously padded bytes. The key needed to perform 
encryption and decryption using this methodology is as follows:
Key: (p, g, c, Vigenère key).
In this crypt-system the natural repetitiveness of a language is obscured and diffused by 
the random padded bits. The characteristics of the enciphered padded text will be different 
from the enciphered text generated using conventional Vigenère cipher. So, the Kasiski 
method for finding the key length is no longer effective when the message is padded with 
random bits. The main drawback of this method is that the size of the encrypted message 
will be increased by around 56%. For areas with low bandwidth or limited storage capacity 
this cipher cannot be used. However, for most communication channels where encryption 
is required, a moderate increase in message size will not have a significant impact. The 
other major drawback is that a good random number generator is required to create an 
effective cipher. If one bit is lost; the remainder of the message will be useless.
For modification of Vigenère cipher, numbers, punctuations, mathematical symbols may 
be used for key in place of characters to make it more difficult for brute force attack. If 
random numbers are used for key that increases the difficulty to decipher the message. In 
conventional Vigenere Cipher the plaintext is considered as a sequence of alphabets 
without any space between them. It may create a problem for receiver to read the message 
by inserting spaces between words. The converted sentence may or may not form a 
meaningful one. Even though it is meaning full the sentence, it may not be the exact plain 
text, because, the receiver needs to guess the exact place to insert space in decrypted 
plaintext. Hence the user will be under pressure to choose the place for inserting space. In 
order to conquer this difficulty an enhanced polyalphabetic cipher with extended vigenere 
table was developed. In extended Vigenere cipher a new symbol is added into the row and 
column of the Vigenere Tableau. The new symbol can be used to represent or to locate the 
blank space in the plaintext. Hence the user can easily encrypt or decrypt the message or 
plaintext without any ambiguity.

The Vigenere table was enhanced by Dennie Van Tassel in his paper and was constructed 
by using 36X36 matrix comprising of 26 alphabets and numbers from 0 to 9. It was named 
as modern Vigenere cipher. Recently, Dr. Udaya has enhanced the Modern Vigenere table 
by constructing 68X68 matrix, consisting of alphabets (1 to 26), numbers (0 to 9) and all 
the symbols present on the keyboard (32). It helps to encrypt and decrypt the combination 
of all kinds of text and the symbols on key board. To fulfill the need in the field of secrecy 
modified the Vigenere table into a 256X256 matrix and named it as a comprehensive 
Vigenere table with 128 ASCII and 128 Extended ASCII characters. If we assume that the 
length of the key is 256 characters and without repetition of any characters, then there will 
be 256! Hence brute force attack is not possible

### SHA-512 Hashing Algorithm
SHA-512 is just one of several algorithms in the Secure Hashing Algorithm (SHA) family. 
In 2001, SHA-512 was published by the National Institute of Standards and Technology 
(NIST) as a U.S. Federal Information Processing Standard (FIPS). Before we look at the 
specifics of how SHA-512 is used today, let’s briefly cover the history of these algorithms.

SHA-512, or Secure Hash Algorithm 512, is a hashing algorithm used to convert text of 
any length into a fixed-size string. Each output produces a SHA-512 length of 512 bits (64 
bytes).
Pseudocode
SHA-512 is identical in structure to SHA-256, but:
• the message is broken into 1024-bit chunks,
• the initial hash values and round constants are extended to 64 bits,
• there are 80 rounds instead of 64,
• the message schedule array has 80 – 64-bit words instead of 64 – 32-bit words,
• to extend the message schedule array w, the loop is from 16 to 79 instead of from 16 
to 63,
• the round constants are based on the first 80 primes 2..409,
• the word size used for calculations is 64 bits long,
• the appended length of the message (before pre-processing), in bits, is a 128-bit bigendian integer, and
• the shift and rotate amounts used are different

Also, SHA-512/t is identical to SHA-512 except that:
• the initial hash values h0 through h7 are given by the SHA-512/t IV generation 
function,
• the output is constructed by truncating the concatenation of h0 through h7 at t bits,
• t equal to 384 is not allowed, instead SHA-384 should be used as specified, and
• t values 224 and 256 are especially mentioned as approved.
The SHA-512/t IV generation function evaluates a modified SHA-512 on the ASCII string 
"SHA-512/t", substituted with the decimal representation of t. The modified SHA-512 is 
the same as SHA-512 except its initial values h0 through h7 have each been XORed with 
the hexadecimal constant 0xa5a5a5a5a5a5a5a
So, for security verification to decrypt the data we using SHA-512 Hashing algorithm here. 
During encryption, when the password is entered, its corresponding hash is created using 
a hash function

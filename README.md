# -Basic-File-Encryption-Decryption
Design a program that can encryt and decryt text files using simple algorithm like Ceasr cipher for the project.
Explanation:

Include necessary headers:

iostream for input/output operations.
string for string manipulation.
openssl/evp.h for encryption/decryption functions.
openssl/err.h for error handling.
Initialize OpenSSL:

OpenSSL_add_all_algorithms(): Adds all available encryption/decryption algorithms to the OpenSSL library.
ERR_load_crypto_strings(): Loads error strings for easier debugging.
Input plaintext:

Get the plaintext message from the user.
Define key and IV:

Replace "my_secret_key" and "my_initialization_vector" with actual 32-byte and 16-byte values, respectively. These should be securely generated and kept secret.
Create EVP_CIPHER_CTX:

EVP_CIPHER_CTX* ctx = EVP_CIPHER_CTX_new();: Creates a context for encryption/decryption operations.
Encryption:

EVP_EncryptInit_ex(): Initializes the encryption context with the chosen cipher (AES-256-CBC), key, and IV.
EVP_EncryptUpdate(): Encrypts the plaintext in multiple blocks.
EVP_EncryptFinal_ex(): Encrypts the last block of plaintext.
Print ciphertext:

Display the ciphertext in hexadecimal format.
Decryption:

EVP_DecryptInit_ex(): Initializes the decryption context with the same cipher, key, and IV.
EVP_DecryptUpdate(): Decrypts the ciphertext in multiple blocks.
EVP_DecryptFinal_ex(): Decrypts the last block of ciphertext.
Print plaintext:

Display the decrypted plaintext.
Clean up:

EVP_CIPHER_CTX_free(): Frees the memory allocated for the encryption/decryption context.
free(): Frees the memory allocated for ciphertext and plaintext.
ERR_free_strings(): Frees the memory allocated for error strings.
HandleErrors() function:
Prints error messages to stderr and aborts the program if any errors occur during the encryption/decryption process.
Remember:

Secure key and IV generation: Use strong random number generators to generate

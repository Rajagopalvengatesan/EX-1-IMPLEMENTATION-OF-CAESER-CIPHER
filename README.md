## Name : RAJA GOPAL V

## Register Number : 212223240134


## Exp:1 IMPLEMENTATION OF CAESER CIPHER 

## AIM: 
To encrypt and decrypt the given message by using Caeser Cipher encryption algorithm. 
  
 ## ALGORITHM: 
1. Calculate the length of the plaintext. 
2. For each character in the plaintext:  
 a. Add the key to the character to get the cipher character.  
 b. If the result exceeds 'Z' for uppercase or 'z' for lowercase, subtract 26 to wrap within the  alphabet.  
3. Display the encrypted text.  
4. For decryption, subtract the key from each character of the ciphertext.  
 a. If the result is less than 'A' for uppercase or 'a' for lowercase, add 26 to wrap within the  alphabet.  
5. Display the decrypted text.  

## PROGRAM: 
```
#include <stdio.h>
#include <string.h>

void encrypt(char text[], int key) {
    int i;
    for (i = 0; text[i] != '\0'; i++) {
        char ch = text[i];
        
        if (ch >= 'A' && ch <= 'Z') {
            ch = ch + key;
            if (ch > 'Z') {
                ch = ch - 26;
            }
        }
        else if (ch >= 'a' && ch <= 'z') {
            ch = ch + key;
            if (ch > 'z') {
                ch = ch - 26;
            }
        }
        text[i] = ch;
    }
}

void decrypt(char text[], int key) {
    int i;
    for (i = 0; text[i] != '\0'; i++) {
        char ch = text[i];
        
        if (ch >= 'A' && ch <= 'Z') {
            ch = ch - key;
            if (ch < 'A') {
                ch = ch + 26;
            }
        }
        else if (ch >= 'a' && ch <= 'z') {
            ch = ch - key;
            if (ch < 'a') {
                ch = ch + 26;
            }
        }
        text[i] = ch;
    }
}

int main() {
    char plaintext[100];
    int key;

    printf("Enter plaintext: ");
    fgets(plaintext, sizeof(plaintext), stdin);

    // remove newline if fgets stores it
    size_t len = strlen(plaintext);
    if (len > 0 && plaintext[len - 1] == '\n') {
        plaintext[len - 1] = '\0';
    }

    printf("Length of plaintext: %zu\n", strlen(plaintext));

    printf("Enter key (1-25): ");
    scanf("%d", &key);

    encrypt(plaintext, key);
    printf("Encrypted text: %s\n", plaintext);

    decrypt(plaintext, key);
    printf("Decrypted text: %s\n", plaintext);

    return 0;
}
```
## OUTPUT: 

![WhatsApp Image 2025-09-01 at 15 16 06_f860b0e9](https://github.com/user-attachments/assets/c85c662e-a316-4237-9fd5-3ef870882a78)


## RESULT: 
The program implementing the Caesar cipher for encryption and decryption has been successfully  executed, and the results have been verified.

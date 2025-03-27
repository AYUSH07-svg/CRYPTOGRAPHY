# CRYPTOGRAPHY
## NAME: AYUSH S
## REG NO: 212224040041
## DATE:27-03-2025
HILL CIPHER
EX. NO: 1(C) AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
#include <stdio.h>
#include <string.h>

int main() {
    unsigned int a[3][3] = {{6, 24, 1}, {13, 16, 10}, {20, 17, 15}};
    unsigned int b[3][3] = {{8, 5, 10}, {21, 8, 21}, {21, 12, 8}};
    int i, j, t = 0;
    unsigned int c[20], d[20];
    char msg[20];

    printf("Enter plain text (max 3 characters): ");
    scanf("%s", msg);

    for (i = 0; i < strlen(msg); i++) {
        c[i] = msg[i] - 65;
        printf("%d ", c[i]);
    }

    for (i = 0; i < 3; i++) {
        t = 0;
        for (j = 0; j < 3; j++) {
            t += a[i][j] * c[j];
        }
        d[i] = t % 26;
    }

    printf("\nEncrypted Cipher Text: ");
    for (i = 0; i < 3; i++) {
        printf("%c ", d[i] + 65);
    }

    for (i = 0; i < 3; i++) {
        t = 0;
        for (j = 0; j < 3; j++) {
            t += b[i][j] * d[j];
        }
        c[i] = t % 26;
    }

    printf("\nDecrypted Cipher Text: ");
    for (i = 0; i < 3; i++) {
        printf("%c ", c[i] + 65);
    }

    return 0;
}
```

## OUTPUT

<img width="455" alt="Screenshot 2025-03-27 085243" src="https://github.com/user-attachments/assets/0c355d3a-6cce-4ee4-8f7b-bc98dc246fba" />

## RESULT
THUS THE PROGRAM IS SUCCESSFULLY IMPLEMENTED.

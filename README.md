# prime-numbers-list-program-in-C
This C program lists all prime numbers between a user-given start and end number using a function to check primality.





#include <stdio.h>
#include <stdbool.h>
bool isPrime(int num) {
    if (num < 2) return false;
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) return false;
    }
    return true;
}
int main() {
    int start, end;

    printf("Enter the start number: ");
    scanf("%d", &start);
    printf("Enter the end number: ");
    scanf("%d", &end);

    if (start > end) {
        printf("Start number must be less than or equal to end number.\n");
        return 1;
    }
    printf("Prime numbers between %d and %d:\n", start, end);
    for (int i = start; i <= end; i++) {
        if (isPrime(i)) {
            printf("%d ", i);
        }
    }
    printf("\n");
    return 0;
}

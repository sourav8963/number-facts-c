#include <stdio.h>
#include <math.h>

// Function to check if the number is prime
int isPrime(int num) {
    if (num <= 1) return 0;
    for (int i = 2; i <= sqrt(num); i++)
        if (num % i == 0) return 0;
    return 1;
}

// Function to check if the number is a palindrome
int isPalindrome(int num) {
    int original = num, reversed = 0;
    while (num > 0) {
        reversed = reversed * 10 + (num % 10);
        num /= 10;
    }
    return original == reversed;
}

// Function to check a perfect square
int isPerfectSquare(int num) {
    int root = sqrt(num);
    return root * root == num;
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);

    printf("\nInteresting facts about %d:\n", num);
    printf("- It is %s.\n", num % 2 == 0 ? "even" : "odd");
    printf("- It is %s prime.\n", isPrime(num) ? "a" : "not a");
    printf("- It is %s perfect square.\n", isPerfectSquare(num) ? "a" : "not a");
    printf("- It is %s palindrome.\n", isPalindrome(num) ? "a" : "not a");

    return 0;
}

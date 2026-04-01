Name:Vaishnavi N. 
USN:SG25CSE166
Department:CSE
Date:31/03/2026

# Assignment:01-L&T

Q. no1:write problem statement
Problem 1:
Simple Interest Calculator
Problem Statement: A bank wants to calculate simple interest for customers. Write a C 
program that takes principal, rate, and time as input and calculates the interest using a function.

solution:
#include <stdio.h>

/* Function prototype to calculate Simple Interest */
float calculateSimpleInterest(float p, float r, float t);

int main() {
    float principal, rate, time, interest;

    /* Accept input from the user */
    printf("Enter Principal: ");
    if (scanf("%f", &principal) != 1) return 1;

    printf("Enter Rate: ");
    if (scanf("%f", &rate) != 1) return 1;

    printf("Enter Time: ");
    if (scanf("%f", &time) != 1) return 1;

    /* Call the user-defined function */
    interest = calculateSimpleInterest(principal, rate, time);

    /* Display the result formatted to 2 decimal places */
    printf("Simple Interest = %.2f\n", interest);

    return 0;
}
/**
 * Function: calculateSimpleInterest
 * --------------------------------
 * Calculates the simple interest using the formula (P * R * T) / 100
 * p: Principal amount
 * r: Rate of interest per annum
 * t: Time in years
 * returns: Calculated simple interest
 */
float calculateSimpleInterest(float p, float r, float t) {
    return (p * r * t) / 100.0;
}

output:
Sample Input
Enter Principal: 1000 
Enter Rate: 5 
Enter Time: 2 
Sample Output
Simple Interest = 100.00 

Q. no2:write problem statement
Problem Statement:
A student management system needs to calculate total and average 
marks of 5 subjects. Write a C program using functions to compute total and percentage.


solution:
#include <stdio.h>

// Function prototypes
int calculate_total(int marks[]);
float calculate_percentage(int total_marks, int num_subjects);

int main() {
    // Array to store marks of 5 subjects
    int marks[5];
    int total;
    float percentage;
    int num_subjects = 5;

    printf("Enter marks of 5 subjects (e.g., 80 70 90 85 75): ");

    // Input marks from the user
    for (int i = 0; i < num_subjects; i++) {
        scanf("%d", &marks[i]);
    }

    // Calculate total marks using a function
    total = calculate_total(marks);

    // Calculate percentage using a function
    // Pass the total and number of subjects to the function
    percentage = calculate_percentage(total, num_subjects);

    // Display the results
    printf("Total = %d\n", total);
    printf("Percentage = %.2f\n", percentage);

    return 0;
}

/**
 * Calculates the total marks from an array of subject marks.
 * 
 * @param marks An array containing the marks for each subject.
 * @return The sum of all marks.
 */
int calculate_total(int marks[]) {
    int sum = 0;
    // Iterate through the array (assuming 5 subjects) and add up the marks
    for (int i = 0; i < 5; i++) {
        sum += marks[i];
    }
    return sum;
}

/**
 * Calculates the percentage based on total marks and number of subjects.
 * 
 * @param total_marks The sum of all subject marks.
 * @param num_subjects The total number of subjects.
 * @return The calculated percentage as a float.
 */
float calculate_percentage(int total_marks, int num_subjects) {
    // Percentage is (Total Marks / Total Possible Marks) * 100
    // Total Possible Marks = num_subjects * Max Marks per subject (assuming 100 for percentage calculation based on prompt output)
    // A simpler way for this problem is (Total Marks / num_subjects) as shown in sample
    return (float)total_marks / num_subjects;
}
output:
Marks: 80 70 90 85 75
Sample Output
Total = 400
Percentage = 80.00

Q. no3: write problem statement
Problem 3: ATM PIN Verification
Problem Statement:
An ATM machine needs to check whether the entered PIN is correct. 
Write a C program that takes a PIN from the user and compares it with a predefined PIN using a 
function.

solution:
#include <stdio.h>

// Function prototype: declares the function before it's used in main
int verifyPin(int enteredPin);

int main() {
    int userPin;

    printf("Enter PIN: ");
    // Takes the PIN as integer input from the user
    scanf("%d", &userPin);

    // Calls the verifyPin function and checks its return value
    if (verifyPin(userPin)) {
        printf("Access Granted\n");
    } else {
        printf("Invalid PIN\n");
    }

    return 0;
}

// Function definition: checks if the entered PIN matches the predefined PIN
int verifyPin(int enteredPin) {
    // Predefined correct PIN
    int correctPin = 1234;

    // Compares the entered PIN with the correct PIN
    if (enteredPin == correctPin) {
        return 1; // Returns 1 (true) if they match
    } else {
        return 0; // Returns 0 (false) otherwise
    }
}
output:
Sample Input:
Enter PIN: 1234
Sample Output:
Access Granted

Q. no4:write problem statement
Problem 6: Library Fine System
Problem Statement: A library system needs to calculate late fine for books returned after the due date.

solution:
#include <stdio.h>

// Function prototype
int calculateFine(int days);

int main() {
    int lateDays;
    int fineAmount;

    // Prompt user for input
    printf("Enter number of late days: ");
    
    // Read the number of late days from the user
    if (scanf("%d", &lateDays) != 1 || lateDays < 0) {
        printf("Invalid input. Please enter a non-negative integer.\n");
        return 1;
    }

    // Call the function to calculate the fine
    fineAmount = calculateFine(lateDays);

    // Display the result
    if (fineAmount > 0) {
        printf("Fine = %d\n", fineAmount);
    } else {
        printf("No Fine\n");
    }

    return 0;
}

// Function definition to calculate the fine
int calculateFine(int days) {
    int fine = 0;

    // Apply the fine rule
    if (days > 5) {
        fine = days * 2; // ₹2 per day for days > 5
    } else {
        fine = 0;       // No fine otherwise (days <= 5)
    }

    return fine;
}
output:
Sample Input Days = 7
Sample Output Fine = 14

Q. no5: write problem statement
em 7: Prime Number Checker
Problem Statement: A teacher wants to identify whether a given number is a prime number. 
Write a C program that takes a number as input and checks whether it is prime using a function.

solution:
#include <stdio.h>

// Function prototype: declares the isPrime function which takes an int and returns an int
int isPrime(int num);

int main() {
    int inputNum;

    // Prompt user for input
    printf("Enter number: ");
    // Read the integer from the user
    scanf("%d", &inputNum);

    // Call the isPrime function and check the returned value
    if (isPrime(inputNum)) {
        printf("Prime\n");
    } else {
        printf("Not Prime\n");
    }

    return 0;
}

/**
 * Checks if a given integer is a prime number.
 * 
 * A prime number is a natural number greater than 1 that has no positive divisors 
 * other than 1 and itself.
 *
 * @param num The integer to check.
 * @return 1 if the number is prime, 0 otherwise.
 */
int isPrime(int num) {
    // Numbers less than or equal to 1 are not prime numbers
    if (num <= 1) {
        return 0;
    }

    // Loop from 2 up to the square root of the number to check for divisors
    // We only need to check up to the square root for efficiency
    for (int i = 2; i * i <= num; i++) {
        // If num is divisible by i (with no remainder), it is not prime
        if (num % i == 0) {
            return 0; // Not prime
        }
    }

    // If the loop completes without finding any divisors, the number is prime
    return 1; // Prime
}
output:
Input Format: Enter an integer number
Output Format: Display whether the number is prime or not
Sample Input: Enter number: 7
Sample Output: Prime

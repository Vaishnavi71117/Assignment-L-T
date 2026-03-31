# Assignment-L-Tc
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

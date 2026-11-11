#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main()
{
    int number, guess, attempts = 0;
    /* Initialize random number generator */
    srand(time(0));
    /* Generate a number between 1 and 100 */
    number = rand() % 100 + 1;
    printf("=================================\n");
    printf("       NUMBER GUESSING GAME      \n");
    printf("=================================\n");
    printf("I have selected a number from 1 to 100.\n");
    printf("Try to guess the number!\n\n");
    do
    {
        printf("Enter your guess: ");
        if (scanf("%d", &guess) != 1)
        {
            printf("Invalid input. Please enter a whole number.\n");
            return 1;
        }
        attempts++;
        if (guess < number)
            printf("Too Low! Try Again.\n\n");
        else if (guess > number)
            printf("Too High! Try Again.\n\n");
        else
        {
            printf("\nCongratulations! You guessed correctly.\n");
            printf("The correct number was %d.\n", number);
            printf("Total attempts: %d\n", attempts);
        }
    } while (guess != number);
    return 0;
}

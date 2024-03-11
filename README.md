# GameScoreLeveling
/*
This program prints levels in a game along with the count of how many players
are at each level.
*/

#include <stdio.h>
#define SIZE 6 // Defines the size of the array

// Prototypes for functions
int pointUpdater(int healthPoints, int numberPlayers[]); // Declares a function prototype for pointUpdater
int arrayContent(int numberPlayers[]); // Declares a function prototype for arrayContent


int main() {
    int numberPlayers[SIZE] = {0}; // Initializes an array to store count of players at each level
    int healthPoints; // Declares a variable to store player health points

    printf("Player points (-1 to quit): "); // Prompts the user to enter player points
    scanf("%d", &healthPoints); // Reads player points from user
    fflush(stdout); // Flushes the output buffer to ensure prompt is displayed w/o error

    // Loop until the sentinel value (-1) is entered
    while (healthPoints != -1) {
        pointUpdater(healthPoints, numberPlayers); // Updates count of players at each level
        printf("Player points (-1 to quit): "); // Prompts the user to enter player points
        scanf("%d", &healthPoints); // Reads input again inside the loop
        fflush(stdout); // Flushes the output buffer to ensure prompt is displayed
    }

    // Display final counts
    arrayContent(numberPlayers); // Calls function to display final counts

    return 0;
}


// Function to update count of players at each level based on health points
int pointUpdater(int healthPoints, int numberPlayers[]) {
    if (healthPoints >= 0 && healthPoints <= 9) // Checks if health points are between 0 and 9
        numberPlayers[0]++; // Increment count of players at level 1
    else if (healthPoints >= 10 && healthPoints <= 19) // Checks if health points are between 10 and 19
        numberPlayers[1]++; // Increments count of players at level 2
    else if (healthPoints >= 20 && healthPoints <= 29) // Checks if health points are between 20 and 29
        numberPlayers[2]++; // Increments count of players at level 3
    else if (healthPoints >= 30 && healthPoints <= 39) // Checks if health points are between 30 and 39
        numberPlayers[3]++; // Increments count of players at level 4
    else if (healthPoints >= 40 && healthPoints <= 49) // Checks if health points are between 40 and 49
        numberPlayers[4]++; // Increments count of players at level 5
    else if (healthPoints >= 50) // Checks if health points are 50 or greater
        numberPlayers[5]++; // Increments count of players at level 6
    return 0;
}


// Function to display final counts of players at each level
int arrayContent(int numberPlayers[]) {
    printf("\nT O T A L S\n"); // Prints header for final counts
    for (int i = 0; i < SIZE; i++) { // Loops through each level
        printf("Level %d   %d\n", i + 1, numberPlayers[i]); // Prints count of players at each level
    }
    return 0;
}

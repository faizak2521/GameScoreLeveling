```
#include <stdio.h>

#define SIZE 6
#define LEVEL_1_MIN_POINTS 0
#define LEVEL_1_MAX_POINTS 9
#define LEVEL_2_MIN_POINTS 10
#define LEVEL_2_MAX_POINTS 19
#define LEVEL_3_MIN_POINTS 20
#define LEVEL_3_MAX_POINTS 29
#define LEVEL_4_MIN_POINTS 30
#define LEVEL_4_MAX_POINTS 39
#define LEVEL_5_MIN_POINTS 40
#define LEVEL_5_MAX_POINTS 49
#define LEVEL_6_MIN_POINTS 50

// Function Declarations
int pointUpdater(int healthPoints, int numberPlayers[]);
int displayPlayerCounts(int numberPlayers[]);

int main() {
    int numberPlayers[SIZE] = {0};
    int healthPoints;

    printf("Player points (-1 to quit): ");
    scanf("%d", &healthPoints);
    fflush(stdout);

    while (healthPoints != -1) {
        pointUpdater(healthPoints, numberPlayers);
        printf("Player points (-1 to quit): ");
        scanf("%d", &healthPoints);
        fflush(stdout);
    }

    displayPlayerCounts(numberPlayers);

    return 0;
}

int pointUpdater(int healthPoints, int numberPlayers[]) {
    if (healthPoints >= LEVEL_1_MIN_POINTS && healthPoints <= LEVEL_1_MAX_POINTS)
        numberPlayers[0]++;
    else if (healthPoints >= LEVEL_2_MIN_POINTS && healthPoints <= LEVEL_2_MAX_POINTS)
        numberPlayers[1]++;
    else if (healthPoints >= LEVEL_3_MIN_POINTS && healthPoints <= LEVEL_3_MAX_POINTS)
        numberPlayers[2]++;
    else if (healthPoints >= LEVEL_4_MIN_POINTS && healthPoints <= LEVEL_4_MAX_POINTS)
        numberPlayers[3]++;
    else if (healthPoints >= LEVEL_5_MIN_POINTS && healthPoints <= LEVEL_5_MAX_POINTS)
        numberPlayers[4]++;
    else if (healthPoints >= LEVEL_6_MIN_POINTS)
        numberPlayers[5]++;
    return 0;
}

int displayPlayerCounts(int numberPlayers[]) {
    printf("\nT O T A L S\n");
    for (int i = 0; i < SIZE; i++) {
        printf("Level %d   %d\n", i + 1, numberPlayers[i]);
    }
    return 0;
}

```

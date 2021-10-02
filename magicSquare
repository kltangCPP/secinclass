#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <unistd.h>


int main() {
    int square[3][3]; // Creates an array that is 3x3
    int numsInSquares[9];
    int count, k = 0;
    int isMagicSquare = 1;
    srand(time(NULL));
    
    // Do while loops until checkSquare says the program found a magic square
    do {
        // For loop that assigns numbers to the places in the array
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                sleep(1);
		        int randNum = rand() % 10; // Generate a random number 
		        int found = 0; //assume the random number hasnt been generated 
		 
		        //make sure the random number hasnt already been generated 
		        for (k = 0; k < 10; k++) { 
			        if(numsInSquares[k] ==randNum) { 
				        found = 1; 
				        break; //once we have located the number we dont need to continue checking 
			        } 
		        } 
		 
		        //we have a new random number 
		        if(found == 0) { 
			        numsInSquares[k] =randNum; 
                    square[i][j] = randNum; // Attach new random number to our square 
		        }     
	        } 
        }
        int sumDiag1, sumDiag2;

        // Find the sum of both diagonals
        for (int i = 0; i < 3; i++) {
            sumDiag1 += square[i][i];
            sumDiag2 += square[i][3-1-i];
        }

        // Check if the two diagonals are unequal
        if(sumDiag1!= sumDiag2)
            isMagicSquare = 0;

        // Find the sum of the rows and columns
        for (int i = 0; i < 3; i++) {
            int rowSum = 0, colSum = 0;   

            for (int j = 0; j < 3; j++){
                rowSum += square[i][j];
                colSum += square[j][i];
            }

            // Check if the sum of the row and column are unequal or if the diagonal sum doesn't match
            if (rowSum != colSum || colSum != sumDiag1)
                isMagicSquare = 0;
        }
        count++; // Increases each time the program generates and tests a set

        printf("Squares generated before finding a successful magic square: %d \n", count); // Let user know how many tries it took
        
        
    } while (isMagicSquare = 0);

    if (isMagicSquare == 1) {
        printf("This is a magic square!");
    }

    // Print each part of the square array
    for (int i = 0; i < 3; i++) {
        printf("[ ");
        for (int j = 0; j < 3; j++)
            printf("%d ", square[i][j]);
        printf(" ]\n");
    }

    return 0;
}

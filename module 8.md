EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

    #include <stdio.h>
    
    int main() {
        int n;
        
    printf("Enter a number: ");
    scanf("%d", &n);

    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0; 
    }


Output:

<img width="1601" height="1001" alt="image" src="https://github.com/user-attachments/assets/91eb2780-3232-490b-bd8e-ab309db124d0" />

Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

    #include <stdio.h>
    int main() {
        char a[50];
        int i, h, c;

    printf("Enter a string (only digits): ");
    scanf("%s", a);

    for (h = 0; h <= 3; h++) {
        c = 0; // reset counter
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] == (h + '0')) 
            { 
                c++;
            }
        }
        printf("%d ", c);
    }
    return 0;
    }


Output:

<img width="1564" height="915" alt="image" src="https://github.com/user-attachments/assets/4ce21d80-c732-4e70-a988-5596cdecd2c7" />


Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    int main() {
        char **s;   
        int n, i;
        printf("Enter number of strings: ");
        scanf("%d", &n);
        s = (char **)malloc(n * sizeof(char *));
        if (s == NULL) {
            printf("Memory allocation failed\n");
            return 1;
        }
        for (i = 0; i < n; i++) {
            s[i] = (char *)malloc(100 * sizeof(char)); 
            if (s[i] == NULL) {
                printf("Memory allocation failed\n");
                return 1;
            }
            printf("Enter string %d: ", i + 1);
            scanf("%s", s[i]);
        }

      printf("\nYou entered:\n");
    for (i = 0; i < n; i++) {
        printf("%s\n", s[i]);
    }
    for (i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);
    return 0;
    }

Output:

<img width="1727" height="1107" alt="image" src="https://github.com/user-attachments/assets/f9384aa1-b516-4be8-8585-4aa973c0cfcd" />


Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
    
    #include <stdio.h>
    
    int main() {
        int n, i, j, min, len;
    printf("Enter n: ");
    scanf("%d", &n);
    len = n * 2 - 1;
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {

            min = i;
            if (j < min) min = j;
            if (len - 1 - i < min) min = len - 1 - i;
            if (len - 1 - j < min) min = len - 1 - j;
            printf("%d ", n - min);
        }
        printf("\n");
    }
    return 0;
    }
    
Output:

<img width="1495" height="1050" alt="image" src="https://github.com/user-attachments/assets/baa1fad6-13d6-4bc1-871c-75cbe6322ed6" />

Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

    #include <stdio.h>
    int square() 
    {
        int num;   
        printf("Enter a number: ");
        scanf("%d", &num);
    
        return num * num;
    }
    int main() 
    {
        int result;
        result = square();
        printf("Square is: %d\n", result);
        return 0;
    }

Output:

<img width="1687" height="1083" alt="image" src="https://github.com/user-attachments/assets/424cf80b-0138-4e3d-ab93-25404e8aeabc" />

Result:
Thus, the program is verified successfully




























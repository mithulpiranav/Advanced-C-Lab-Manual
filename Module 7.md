EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:

    #include <stdio.h>
    struct eligible 
    {
        int age;          
        char n[50];       
    };
    
    int main() 
    {
        
    struct eligible e;


    printf("Enter name: ");
    scanf("%s", e.n);       
    printf("Enter age: ");
    scanf("%d", &e.age);    
    if (e.age <= 6) 
            printf("Vaccine Eligibility: No\n");
    else 
            printf("Vaccine Eligibility: Yes\n");
    
    printf("Details:\n");
    printf("Name: %s\n", e.n);
    printf("Age: %d\n", e.age);
    return 0;
    }


Output:

<img width="797" height="1076" alt="image" src="https://github.com/user-attachments/assets/1e88ea80-6a1a-465e-8af0-0330ed29802c" />


Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

    #include <stdio.h>
    struct numbers {
        float a;
        float b;
    };
    float add(struct numbers n)
    {
        return n.a + n.b;
    }
    
    int main() {
            struct numbers n;
        
    printf("Enter value of a: ");
    scanf("%f", &n.a);
    printf("Enter value of b: ");
    scanf("%f", &n.b);
    float result = add(n);
    printf("Sum = %.2f\n", result);
    return 0;
    }

Output:

<img width="694" height="925" alt="image" src="https://github.com/user-attachments/assets/25f9c72a-3f30-4014-ab77-4d2d518443fd" />


Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
    
    #include <stdio.h>   
    int main()
    {        
        FILE *p;
        char name[50];
    
    printf("Enter file name: ");
    scanf("%s", name);
    
    printf("File with name '%s' has been created successfully (if fopen works).\n", name);
    
    p = fopen(name, "w");
    if (p == NULL)
    {
        printf("Error: Unable to create or open file.\n");
        return 1;  
    }
    
    printf("File opened successfully.\n");
    
    fclose(p);
    
    printf("File closed.\n");
    return 0;  
    }

Output:

<img width="1083" height="1023" alt="image" src="https://github.com/user-attachments/assets/33a9b827-8205-487a-9a25-292a35ab7578" />

Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

    #include <stdio.h>   
    int main()
    {         
        FILE *p;
        char name[50], text[100];
        int num;
        printf("Enter file name: ");
        scanf("%s", name);
        printf("Enter number of strings: ");
        scanf("%d", &num);
        p = fopen(name, "w");
        if (p == NULL) 
        {
            printf("Error: Unable to create or open file.\n");
            return 1;
        }
        printf("File opened successfully.\n");
        for (int i = 0; i < num; i++) {
            printf("Enter string %d: ", i + 1);
            scanf(" %[^\n]", text);  
            fputs(text, p);          
            fputs("\n", p);          
        }
        fclose(p);
        printf("Data added successfully.\n");
        return 0;
    }

Output:

<img width="812" height="994" alt="image" src="https://github.com/user-attachments/assets/bb8efdb2-f69b-40fd-b1d1-72f893e66925" />

Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Subject
    {
        char name[50];
        int marks;
    };
    int main() {
        int n;
        struct Subject *s;
        printf("Enter number of subjects: ");
        scanf("%d", &n);
        s = (struct Subject*) malloc(n * sizeof(struct Subject));
        if (s == NULL) {
            printf("Error: Memory allocation failed!\n");
            return 1; // exit with error
        }
        for (int i = 0; i < n; i++) {
            printf("Enter name of subject %d: ", i + 1);
            scanf("%s", s[i].name);
            printf("Enter marks of subject %d: ", i + 1);
            scanf("%d", &s[i].marks);
        }
        printf("\n--- Subject Details ---\n");
        for (int i = 0; i < n; i++) {
            printf("Subject: %s, Marks: %d\n", s[i].name, s[i].marks);
        }
        free(s);
        return 0;
    }

Output:

<img width="1607" height="972" alt="image" src="https://github.com/user-attachments/assets/f5500e24-6252-48c7-bbd7-0380b6a2b771" />

Result:
Thus, the program is verified successfully

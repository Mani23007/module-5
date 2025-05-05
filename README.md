# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>

int main() {
    float length, breadth, area;
    float *ptrLength, *ptrBreadth;

    // Assign the address of length and breadth to pointers
    ptrLength = &length;
    ptrBreadth = &breadth;

    // Input values
    printf("Enter the length of the rectangle: ");
    scanf("%f", ptrLength);

    printf("Enter the breadth of the rectangle: ");
    scanf("%f", ptrBreadth);

    // Calculate area using pointers
    area = (*ptrLength) * (*ptrBreadth);

    printf("Area of the rectangle = %.2f\n", area);

    return 0;
}
~~~

## OUTPUT:
![image](https://github.com/user-attachments/assets/51fc876b-1e36-417c-8ab0-a081389acf1c)

## RESULT:
Thus the program to find area of rectangle using pointer has been executed successfully.
 
# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>
#include <stdlib.h>  // For malloc and free

int main() {
    char *str;

    // Allocate memory for 8 characters (7 letters + 1 null terminator)
    str = (char *)malloc(8 * sizeof(char));

    // Check if memory was allocated successfully
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1; // Exit with error code
    }

    // Copy the word "WELCOME" into allocated memory
    str[0] = 'W';
    str[1] = 'E';
    str[2] = 'L';
    str[3] = 'C';
    str[4] = 'O';
    str[5] = 'M';
    str[6] = 'E';
    str[7] = '\0'; // Null terminator to end the string

    // Print the string
    printf("%s\n", str);

    // Free the allocated memory
    free(str);

    return 0;
}
~~~


## OUTPUT:
![image](https://github.com/user-attachments/assets/f09b5ec4-4682-4256-94d3-4ae7d916cd5b)

## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.
 
.
# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>

// Define a structure for student
struct Student {
    int rollNumber;
    char name[50];
    float marks;
};

int main() {
    struct Student s;

    // Input student information
    printf("Enter student roll number: ");
    scanf("%d", &s.rollNumber);

    printf("Enter student name: ");
    scanf(" %[^\n]", s.name); // To read full name including spaces

    printf("Enter student marks: ");
    scanf("%f", &s.marks);

    // Display student information
    printf("\n--- Student Information ---\n");
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Name       : %s\n", s.name);
    printf("Marks      : %.2f\n", s.marks);

    return 0;
}
~~~


## OUTPUT:
![image](https://github.com/user-attachments/assets/7bbb233e-9d6f-4d65-b62a-c5aa66fe108c)

## RESULT:

Thus the program to store the student information and display it using structure has been executed successfully.
 
# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>

// Define a structure for Employee
struct Employee {
    int empID;
    char name[50];
    float basicSalary;
    float grossSalary;
};

int main() {
    struct Employee emp[3]; // Array to store 3 employees
    int i;

    // Input employee details
    for (i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d:\n", i + 1);

        printf("Enter Employee ID: ");
        scanf("%d", &emp[i].empID);

        printf("Enter Employee Name: ");
        scanf(" %[^\n]", emp[i].name); // read full name with spaces

        printf("Enter Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);

        // Calculate Gross Salary
        float hra = 0.20 * emp[i].basicSalary;
        float da = 0.80 * emp[i].basicSalary;
        emp[i].grossSalary = emp[i].basicSalary + hra + da;
    }

    // Display employee details
    printf("\n--- Employee Salary Details ---\n");
    for (i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("ID          : %d\n", emp[i].empID);
        printf("Name        : %s\n", emp[i].name);
        printf("Basic Salary: %.2f\n", emp[i].basicSalary);
        printf("Gross Salary: %.2f\n", emp[i].grossSalary);
    }

    return 0;
}
~~~



 ## OUTPUT:
 ![image](https://github.com/user-attachments/assets/f3015a12-9ae3-4770-90a4-05f94c4d987f)
![image](https://github.com/user-attachments/assets/508fc8ce-af27-4554-b777-241867158d8d)
 
## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.
 

# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM:
~~~
#include <stdio.h>

// Define a structure for Student
struct Student {
    char name[50];
    int rollNumber;
    float marks[5];     // Array to store marks in 5 subjects
    float total;
    float average;
};

int main() {
    struct Student s;
    int i;

    // Input student information
    printf("Enter student name: ");
    scanf(" %[^\n]", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.rollNumber);

    // Input marks
    printf("Enter marks for 5 subjects:\n");
    s.total = 0;
    for (i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &s.marks[i]);
        s.total += s.marks[i];
    }

    // Calculate average
    s.average = s.total / 5;

    // Display results
    printf("\n--- Student Result ---\n");
    printf("Name      : %s\n", s.name);
    printf("Roll No   : %d\n", s.rollNumber);
    printf("Total     : %.2f\n", s.total);
    printf("Average   : %.2f\n", s.average);

    return 0;
}
~~~


## OUTPUT:
![image](https://github.com/user-attachments/assets/765f8484-a6e5-4534-8b46-9e4323bc24bf)

## RESULT:

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	



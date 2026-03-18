# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
## 11. Implementation of the concept of pointer to function.
## 12. Implementation of programs using structure and union.
## 13. Implementation of programs for different storage classes.
# Ex.No:26
  Develop a C program using static storage class in function with parameter and without return to display the incremental float values as indicated in the following output.
| Input | Output                                       |
|-------|----------------------------------------------|
| 1     | 101.25&nbsp;&nbsp;201.50&nbsp;&nbsp;301.75&nbsp;&nbsp;402.00&nbsp;&nbsp;502.75 |
# Date : 
# Aim:
To develop a C program using the static storage class in a function with a parameter and without a return value to display the required output.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  a. Declare an integer variable `input` to store the user’s number.  
  b. Inside the function `display(int n)`, declare a static float variable `base` and initialize it to 100.25.
### Step 4:
  Read an integer from the user and store it in `input`.
### Step 5:
  Call the function `display(input)` five times.
### Step 6:
  Inside the `display` function, for each call:  
  a. Calculate the sum of `base` and `n`.  
  b. Display the value.  
  c. Increase the value of `base` by 100.25.
### Step 7:
  Repeat Step 6 for all function calls.
### Step 8:
  Stop
# Program:
~~~
#include <stdio.h>

void display(int n)
{
    static float base = 100.25;
    float sum = base + n;
    printf("%.2f  ", sum);
    base += 100.25;
}

int main()
{
    int input, i;
    printf("Enter a number: ");
    scanf("%d", &input);

    for(i = 0; i < 5; i++)
        display(input);

    return 0;
}
~~~
# Output:
<img width="429" height="139" alt="517846149-6fa02dc3-f975-45fd-b121-e9bb304d408c" src="https://github.com/user-attachments/assets/27fd4568-45a4-44ff-8b9e-797ee7a1b2ba" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:27
  Implement a C program to perform arithmetic operations (addition, subtraction, multiplication, division) on two integers using function pointers. The user should input two numbers and select the desired operation from a menu.
# Date : 
# Aim:
  To implement a C program that uses function pointers to perform arithmetic operations (add, subtract, multiply, divide) on two integers based on user choice.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Declare four functions to perform arithmetic operations:  
  - `add(int a, int b)`  
  - `subtract(int a, int b)`  
  - `multiply(int a, int b)`  
  - `divide(int a, int b)`
### Step 4:
  Declare a function pointer `int (*operation)(int, int)` to point to any of the arithmetic functions.
### Step 5:
  Input two integers from the user (`num1` and `num2`).
### Step 6:
  Display a menu for the user to choose an operation:  
  - Add  
  - Subtract  
  - Multiply  
  - Divide
### Step 7:
  Read the user’s choice.
### Step 8:
  Use a switch statement to assign the function pointer `operation` to the appropriate function based on the user’s choice.  
  - **Step 8.1:** If the choice is 4 (divide), check if the second number is zero. If yes, display an error and terminate.  
  - **Step 8.2:** If the choice is invalid, display an error and terminate.
### Step 9:
  Call the function using the function pointer and store the result in a variable `result`.
### Step 10:
  Display the result.
### Step 11:
  Stop
# Program:
~~~
#include <stdio.h>

int add(int a, int b)
{ 
    return a + b; 
}

int subtract(int a, int b)
{ 
    return a - b;
}

int multiply(int a, int b)
{ 
    return a * b;
}

int divide(int a, int b)
{ 
    return a / b;
}

int main()
{
    int num1, num2, choice, result;
    int (*operation)(int, int);

    printf("Enter two integers: ");
    scanf("%d %d", &num1, &num2);

    printf("1.Add\n2.Subtract\n3.Multiply\n4.Divide\nEnter your choice: ");
    scanf("%d", &choice);

    switch(choice)
    {
        case 1: operation = add; break;
        case 2: operation = subtract; break;
        case 3: operation = multiply; break;
        case 4:
            if(num2 == 0){
                printf("Error: Division by zero");
                return 0;
            }
            operation = divide;
            break;
        default:
            printf("Invalid Choice");
            return 0;
    }

    result = operation(num1, num2);
    printf("Result = %d", result);

    return 0;
}
~~~
# Output:
<img width="303" height="254" alt="517846396-1c53d188-95ef-4419-9fa2-bab4c09c6c34" src="https://github.com/user-attachments/assets/623fec55-ebc0-4688-bd92-a30086a90baa" /><img width="289" height="266" alt="517846460-53e433ff-568f-4ba0-a5e2-35ed528250dd" src="https://github.com/user-attachments/assets/f5732cd3-18b6-4da0-99b7-ff1cb4ccd186" />

<img width="289" height="266" alt="517846460-53e433ff-568f-4ba0-a5e2-35ed528250dd" src="https://github.com/user-attachments/assets/d1e96b02-25d9-4d61-ac73-97d3c1fadc6e" />
<img width="331" height="273" alt="517846494-ee80d692-e925-4985-b4dd-14ea8528e23a" src="https://github.com/user-attachments/assets/cdec5ffe-2fc5-41df-b177-17eaed9f83e0" />
<img width="312" height="266" alt="517846593-62215498-b875-4482-9428-293a36e1b35d" src="https://github.com/user-attachments/assets/f7a424fd-63ab-49f4-89fa-8edf4e467a8f" />
<img width="310" height="268" alt="517846620-9f495169-cf70-40b7-888b-57ab2a031cad" src="https://github.com/user-attachments/assets/9341024f-7fa6-4844-8295-9c4f806b65a9" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:28
  Develop a C program to store details of n employees (employee number, name, and salary) using structures, and display the employee(s) with the highest salary.
# Date : 
# Aim:
  To develop and implement a C program that uses a structure to store employee details (employee number, name, and salary) and determine the employee(s) with the highest salary.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure `employee` with the following members:  
  - `eno` (employee number)  
  - `ename` (employee name)  
  - `salary` (employee salary)
### Step 4:
  Declare an array of structures to store details of multiple employees.
### Step 5:
  Input the number of employees, `n`.
### Step 6:
  For each employee (`i = 0` to `n-1`), do the following:  
  - **Step 6.1:** Input employee number.  
  - **Step 6.2:** Input employee name (allow spaces).  
  - **Step 6.3:** Input employee salary.  
  - **Step 6.4 (Optional):** Print the entered details for verification.
### Step 7:
  Initialize a variable `high` with the salary of the first employee.
### Step 8:
  For each employee (`i = 1` to `n-1`), do the following:  
  - **Step 8.1:** Compare employee salary with `high`.  
  - **Step 8.2:** If the salary is greater than `high`, update `high` with this salary.
### Step 9:
  Print the details of employee(s) whose salary matches `high`:  
  - **Step 9.1:** Loop through all employees.  
  - **Step 9.2:** If employee salary equals `high`, print employee number, name, and salary.
### Step 10:
  Stop
# Program:
~~~
#include <stdio.h>

struct employee
{
    int eno;
    char ename[20];
    float salary;
};

int main()
{
    struct employee emp[20];
    int n, i;
    float high;

    printf("Enter number of employees: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        printf("\nEnter Employee Number: ");
        scanf("%d", &emp[i].eno);
        printf("Enter Employee Name: ");
        scanf("%s", emp[i].ename);
        printf("Enter Salary: ");
        scanf("%f", &emp[i].salary);
    }

    high = emp[0].salary;
    for(i = 1; i < n; i++)
        if(emp[i].salary > high)
            high = emp[i].salary;

    printf("\nEmployee(s) with Highest Salary:\n");
    for(i = 0; i < n; i++)
        if(emp[i].salary == high)
            printf("%d  %s  %.2f\n", emp[i].eno, emp[i].ename, emp[i].salary);

    return 0;
}
~~~
# Output:
<img width="376" height="520" alt="517847045-5c97cd99-a56b-4313-9a43-fa3f1d47b6f3" src="https://github.com/user-attachments/assets/e7504c8e-80a3-4caf-8ff5-de591e60177b" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:29
  Create the C program to calculate the present age of a person by passing structure as a reference.
# Date : 
# Aim:
  To create a C program that uses a structure to store the current date and birth date, and to calculate the person’s present age in years, months, and days by passing the structure as a reference.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure named `date` with members to store:  
  - Current date (`c_date`, `c_month`, `c_year`)  
  - Birth date (`b_date`, `b_month`, `b_year`)  
  - Calculated age (`cal_date`, `cal_month`, `cal_year`)
### Step 4:
  Initialize a structure variable with the current date and birth date values.
### Step 5:
  Pass the structure variable to a function `findAge()` by reference.
### Step 6:
  Inside `findAge()`:  
  - a. Declare an integer array `month[]` to store the number of days in each month.  
  - b. If the birth date is greater than the current date:  
     - Add the number of days of the previous month to the current date.  
     - Decrease the current month by 1.  
  - c. If the birth month is greater than the current month:  
     - Decrease the current year by 1.  
     - Add 12 to the current month.  
  - d. Calculate the age in days, months, and years by subtracting the corresponding birth values from the current values.
### Step 7:
  Return the structure pointer containing the calculated age.
### Step 8:
  Display the calculated age (years, months, and days) in the `main` function.
### Step 9:
  Stop
# Program:
~~~
#include <stdio.h>

struct date
{
    int c_date, c_month, c_year;
    int b_date, b_month, b_year;
    int age_date, age_month, age_year;
};

void findAge(struct date *p)
{
    int month[] = {31,28,31,30,31,30,31,31,30,31,30,31};

    if(p->b_date > p->c_date)
    {
        p->c_date += month[p->c_month - 2];
        p->c_month--;
    }

    if(p->b_month > p->c_month)
    {
        p->c_month += 12;
        p->c_year--;
    }

    p->age_date = p->c_date - p->b_date;
    p->age_month = p->c_month - p->b_month;
    p->age_year = p->c_year - p->b_year;
}

int main()
{
    struct date person;

    printf("Enter Current Date (DD MM YYYY): ");
    scanf("%d %d %d", &person.c_date, &person.c_month, &person.c_year);

    printf("Enter Birth Date (DD MM YYYY): ");
    scanf("%d %d %d", &person.b_date, &person.b_month, &person.b_year);

    findAge(&person);

    printf("\nAge = %d Years %d Months %d Days", 
           person.age_year, person.age_month, person.age_date);

    return 0;
}
~~~
# Output:
<img width="499" height="190" alt="517848189-eb37d59f-b5e9-431b-ad61-1d07cbdeca50" src="https://github.com/user-attachments/assets/10018698-deab-456b-a7de-efdae11aefb4" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:30
  Build a C program to demonstrate the use of a pointer to a union. Store an integer value in a union, access it using a union pointer, and display it as both an integer and a character.
# Date : 
# Aim:
  To build a program in C that uses a pointer to a union to store an integer value and display it in both integer and character format.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a union `abc` with the following members:  
  - `int a`  
  - `char b`
### Step 4:
  Declare a union variable `var` of type `abc`.
### Step 5:
  Declare a pointer `ptr` of type `union abc*`.
### Step 6:
  Assign the address of `var` to `ptr`.
### Step 7:
  Store an integer value (e.g., 90) in `var.a`.
### Step 8:
  Access and print the value of `a` using the pointer `ptr` in integer format.
### Step 9:
  Access and print the same value using the pointer `ptr` in character format.
### Step 10:
  Stop
# Program:
~~~
#include <stdio.h>

union abc
{
    int a;
    char b;
};

int main()
{
    union abc var;
    union abc *ptr;

    ptr = &var;

    var.a = 90;

    printf("Integer: %d\n", ptr->a);
    printf("Character: %c\n", ptr->b);

    return 0;
}
~~~
# Output:
<img width="177" height="133" alt="517848300-20b5eb40-bd79-443b-aae5-b4a396a0ca53" src="https://github.com/user-attachments/assets/1c06857a-8909-4947-b522-337dc6d5a394" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.



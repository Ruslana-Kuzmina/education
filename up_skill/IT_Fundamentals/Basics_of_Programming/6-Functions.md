# Functions

## Function Prototypes. Basics of Functional Programming

A function is a block of code with a given name comprising a set of steps to resolve
a single specific task.

The division of a program into functions allows you to focus on exactly the part
of the code that you want to change.

Suppose you want to write a program, and you need to perform the same task in that
program more than once. In this case, you have two options:

- to use the same set of code written in a sequence each time you want to perform
  a task
- to create a function to perform the specified task and simply call it every time
  you need to perform it

It is recommended to follow the principle **"do not repeat yourself" (DRY)** which
presupposes software development aimed at reducing the repetition of software patterns,
replacing them with abstractions to avoid redundancy. When the DRY principle is
applied successfully, the modification of any single element of a system does not
require a change in other logically unrelated elements.

### Functions in C

C program has at least one main function and can have any number of additional
functions. The `main()` function is the starting point of the program.

Often, functions are divided into two types:

- Library Functions
  - The code for a library function is already present in the header file which
    we include at the beginning of a program
  - To use a library function, you should enter its name and use it with the correct
    syntax
  - For example, `printf()`;, `scanf()`; in C; `System.out.println()`; in Java

- User-defined Functions
  - The code for a user-defined function is written by a programmer who designs
    this particular code
  - To call a user-defined function when we need the function to perform an operation
    in our program, we also need to enter a name and use specific syntax
  - A user-defined function is always written by a programmer, but later it can
    be a part of the library since the programmer can create libraries for the project

The declaration of a user-defined function is carried out in two forms:

- In the form of a **description** (declaration) when a programmer declares a
  function prototype, which informs the compiler that its full definition (code
  block or its implementation) will be given below.
- In the form of a **definition** when a programmer declares its full code block
  or its implementation.

So, any user-defined function must be declared and defined.

A function signature defines the rules for using the function. Typically, a **signature**
is a function description that includes the return type, the function name, and
the list of formal parameters with their types. The declaration of a function is
as follows:

`return_type function_name (data_type parameters);`

Let us consider an example of raising a number to some power. The number and the
power are integers, and the result value is also an integer. A programmer will
pass the numbers `int num`, `int power` to a function named `raise_number` that will
return the power value of type int after calculating it.

`int raise_number(int num, int power)`

int - return value type
raise_number - function name
int num, int power - function parameters

Function **semantics** determines how a function is implemented. Typically, it is
the body of a function. After a prototype declaration, functions can be placed in
any order in the source file, while the source program can be located in several
files. The compiler will throw an error if you refer to a function that is declared
and/or implemented below.

The C Standard Library offers many in-built math functions to solve our problem,
including the header file `<math.h>`. The definition of our function can be:

```C
int raise_number(int num, int power)
{
  int res_amount=0; // declaring local variable
  res_amount = pow(num,power);// we can use library function
  return res_amount; // returning the powered value
}
```

In a simple scenario in order to call a function, you need to specify its name,
followed by the list of arguments passed to it in parentheses and separated by
commas. The number and type of passed arguments into a function must exactly match
the number and type of parameters required for a function. When a function is "called",
the program "leaves" the current section of code and starts executing the first
line inside our function. Thus, after all the instructions inside the function
are executed from top to bottom, the program will leave the function and return
to where it left off (in main()). At the same time, the data calculated and RETURNED
by the function will be used further instead of the function in the original line
of code.

```C
#include <stdio.h>
#include <math.h>

int raise_number(int num, int power)  { // function declaration
    // function definition
    int result;
    result = pow(num, power);
    result = result * 2;
    return result;
}

int main() {
    int num = 5;
    int power = 2;
    int result;

    result = raise_number(num, power);
    // result = pow(num, power);
    // result = result * 2;
    printf("%d to the power of %d equals %d\n", num, power, result);

    result = raise_number(power, num);
    // result = pow(power, num);
    // result = result * 2;
    printf("%d to the power of %d equals %d", power, num, result);
    return 0;
}
```

Result

5 to the power of 2 equals 50
2 to the power of 5 equals 64

```C
#include <stdio.h>
#include <math.h>

void raise_number(int num, int power)// Function declaration and definition
{
    int result;
    result = pow(num,power);
    printf("%d to the power of %d equals %d.", num, power, result);
}

int main()
{
    int num=0;
    int power=0;
    printf("Enter a number \n");
    scanf("%d", &num);
    printf("Enter a power \n");
    scanf("%d", &power);

    raise_number(num,power); //Using a user-defined function
    return 0;
}
```

If we enter 2 and 4, the result will be:

Enter a number 2
Enter a power 4
2 to the power of 4 equals 16.

There are a few approaches on how to write simple, understandable, and easy-to-test
functions:

- Avoid Big Black Box Functions
  Functions should be small, very small. It is better to avoid bloated functions
  that have a lot of tasks and write a few small functions. Bloated functions with
  hidden meanings are difficult to understand, modify, and especially, to test.

- Aviod Big, Complicated Functions
  Functions should be simple: each application implements a set of requirements
  that are best broken down into small executable components (scopes, classes,
  functions, code blocks) that perform well-defined operations. Each component
  is made up of other smaller components. Thus, you need to decompose a function
  into smaller steps, which should all be at the same, previous, level of abstraction.
  This is important because the function becomes simple and implies "the execution
  of one task, and this execution should be of high quality." Simple functions are
  obvious, which means they are easy to read and modify.

- Avoid Confusing Function Names
  Function names should be compact and clearly indicate what a function does, without
  having to dig into implementation details. For example, since a function is an
  action, its name must contain at least one verb. It is good to use camel case
  format that starts with a small letter: `addItem()`, `getFirstName()`.

#### Methods in Java

In general, the method declaration is almost the same as in C programming. An access
**modifier** was added before the method. A modifier defines the access type of a
method, i.e. it shows the scope of a method in the program. In Java, there are 4
types of access specifiers:

- **Default** (declared/defined without using any modifier): a method accessible
  within the same class and the package within which its class is defined
- **Public**: a method accessible in all classes in your application
- **Protected**: a method accessible within the class in which it is defined and
  in its subclass(es) as well
- **Private**: a method accessible only within the class in which it is defined

Packages, classes and objects, subclass(es), and exceptions will be discussed later.

A method must be called in order to use its functionality. Let us demonstrate the
description and method call in Java within one class.

#### Python

Its syntax is as follows:

```Python
def function_name(function_parameters):
    some code
    return statement
```

Python does not have access modifiers but it emulates this behavior using names
which start with underscores:

_var is protected.
__var is private.

The heading starts with the keyword `def` and the name of a function, followed by
parentheses with arguments if any, and a colon. The indented block of code performs
some sort of an operation. Return is optional as in C or Java programming language
and is used if a caller is required to get any return value from the definition.

```Python
def raise_number():
    num = int(input("Enter a number: "))
    power = int(input("Enter a power: "))
    print(num, "to the power of", power, "equals:", num ** power)

raise_number()
```

The result:

Enter a number: 5
Enter a power: 6
5 to the power of 6 equals: 15625

A function in Python can take an arbitrary number of arguments, or take none of
them. A function can also take a variable number of positional arguments. In this
case, the name is preceded by *.

And for a program to work correctly, it is important for us to find errors associated
with the transfer of data of the wrong type as early as possible. There are various
annotations that define this mechanism. For example, in Python, you can either
specify the types of parameters and return values in functions or not. We can
annotate the arguments and return values in the following way:

```Python
def repeater(s: str, num: int) -> str:
    return s * num
```

s: str - The annotation for an argument is specified with a colon after its name.
-<
`def function_name () -> type`

The annotation which defines the type of the value returned by the function is
indicated after its name using symbols ->.

The Python runtime does not enforce function and variable type annotations. They
can be used by third-party tools such as type checkers, IDEs, etc.

To sum up the topic, the following main features of functions in programming can
be distinguished:

Simplicity - It is easy to understand, define, and apply. It basically increases
the readability of code by splitting the code into smaller chunks.

Control - Transferring control from one part of a program to another one becomes
easier.

Reusability - The same function can be reused for different values.

Error detection - Debugging a large program that is broken into small chunks makes
functions easier.

Less redundancy - Reducing code redundancy will make your program more efficient
and faster.

Time saving - Using functions can save a lot of time as this will allow faster
development and easier testing of a program.

## Passing Parameters. Local and Global Variables

### Local and Global Variables

There are three main sections of a program where variables are declared:

- inside a function (or a block)
- in the function header (the description of parameters)
- outside a function

In programming, the scope is determined by the location of the variable declaration
in the program source file and can be:

- Local (Internal)
  - Variables are declared inside a function (block) and described in a function
    header.
  - The scope of local data is from the place of declaration to the end of the
    function (block) in which they are declared, including all nested blocks, and
    is not available in another section. This allows us to reuse variable names
    (such as in the example in topic 1).
  - The lifetime of a variable can be temporary - during the execution of a function
    (block).
  - A local variable does not provide data sharing and shared data must be retransmitted.
  - When the value of a local variable is modified in one function, the changes
    are not visible in another function. Therefore, the use of local variables
    prevents us from "accidentally" changing information that is important for
    another part of our program.
  - It is stored on the stack unless specified otherwise.

- Global (External)
  - Variables are described outside a function.
  - The scope of global data is from where it is declared to the end of the file
    in which it is declared.
  - The lifetime of a variable can be constant - during the execution of a program.
  - A global variable provides data sharing.
  - When the value of a global variable is modified in one function, changes are
    visible in the rest of the program.
  - It is stored on a fixed location chosen by a compiler or an interpreter.
  - A global variable is useful when multiple functions access the same data.

#### Passing Parameters

As we already know, a parameter is a symbolic name for a set of arguments that go
into a function. There are two basic ways to pass parameters to C:

- Pass **by value**
- Pass **by reference**

In this case, we need to understand the difference between actual parameters and
formal parameters.

**Actual parameters** are used in a function call.

For example, in the following call of the function

`int result = raise_number(num, power);`

the num and power are actual values.

- The value of an actual parameter is copied to a formal parameter.
- The values may be variable (global or local), or constant.

**Formal parameters** are used in a function definition.

For example, in the following declaration

`int raise_number(int num, int power);`

the num and power are formal values.

- They are used to get the value of the result of a function call.
- The values are simply local variables.

Some space in memory is allocated for a variable and when passing by reference,
this address is transferred; and when passing by value, only what is stored at
this address is passed.

|Pass by Reference                             | Pass by Value                                                  |
|----------------------------------------------|----------------------------------------------------------------|
|The address of a variable is passed to the    |When calling a function, parameters are usually passed by value |
|function as a parameter.                      |or using variable names, and are changed in the function itself,|
|                                              |after which the result should be returned.                      |
|The value of an actual parameter can be       |The value of an actual parameter cannot be modified by a formal |
|modified by a formal parameter.               |parameter.                                                      |
|The same memory is used for both actual and   |Different memory is used for both actual and formal parameters  |
|formal parameters since only an address is    |since the value of an actual parameter is copied to a formal    |
|used by both parameters, and the operation    |parameter.                                                      |
|performed on formal parameters affects the    |                                                                |
|value of actual parameters.                   |                                                                |

In fact, Java is strictly called by value. But even if, as a parameter, we use
the reference to the object of a class, it is also passed to the methods by value.
This means that when the method returns, the passed reference still refers to the
same object as before. The values of the object's fields can be changed in the
method if they have an appropriate access level. You will learn more about this
by studying classes and objects.

All parameters (arguments) in the Python language are passed by reference. It means
if you change what a parameter refers to within a function, the change also reflects
back in a function call.

As mentioned previously, in JavaScript, all primitive types are passed by value,
while objects (everything else) are passed by reference.

#### C program when we pass by reference

For the next example, think about pointers. A pointer is a variable that stores
the address of a memory area. A pointer, like a variable, has a type. Pointer
declaration syntax is:

`<type> * <name>;`

During execution, a program resides in the computer's memory; the memory also
contains the program variables. As each house has its own address, each computer
memory cell has its own address. As with house addresses, memory locations are
unique: there are no two locations in memory with the same address. Computer memory
is like a hardware array in which a memory location is an element, and an address
is the index of that element in the array.

The two main operators for working with pointers are:

- the `&` operator that allows you to obtain the address (memory location)
  in which the operand is stored
- the dereference operator `*` that allows you to access the value of the operand
  whose address is stored in the pointer

## Functions for Working with Strings

A **string** is a sequence of ASCII or UNICODE characters. In most high-level
programming languages, strings are represented as a separate type within the
language type system. Since the C language by its origin is a system programming
language, there is no string data type in it as such, and ordinary arrays (sets)
of characters are used as strings in C.

### Working with Strings in C

Declaring a string in C has the same syntax as declaring a single character array
a numbered set of elements of the char type. The length of a string must be an
integer and is specified with one character to store the terminating zero.
Therefore, the maximum number of significant characters in a string is one less
than its length.

For example, a string can contain a maximum of 49 characters if it is declared
like this

`char str [50];`

String initialization in C is done when it is declared using the following syntax:

`char str [length] = "some string";`

or

`char str [] = "some string";`

A string of characters should be enclosed in double quotes and is called a literal
string. The examples of declaring strings with initialization are provided below:

`char name [50] = "Mary", surname [50] = "Lee ";`

Since C strings are arrays of characters, you can refer to any character in a string
by its index. All library functions for working with strings can be divided into
three groups:

- Input and output of strings
- Conversion of strings
- Processing strings.

The `string.h`, `stdlib.h` libraries contain functions for various actions on strings.

For example, you can use formatted input and output functions `(printf()` and
`scanf()` or `gets()` and `puts()`) to input and output string information. We
discussed this in detail in Submodule 2.

Let us consider an example where you have a string, display it, determine its
actual length, print only the first word of the string, replace a word in the string.

```C
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "All the world's a stage, and all the men and women merely players";
    int size = strlen(str); //determining string's length
    printf("Old line: \n");

    //displaying a string
    for(int i = 0; i < size; i++)
        printf("%c", str[i]);
    printf("\nThe actual length of the string is: %d \n", size);

    //print the first word
    char sep [10]=" ";
    char* words= strtok (str,sep);
    printf("The first word is: %s \n", words);

    //counting the number of words in the string
    char mas[10][10];
    int word_count = 0;
    for (int i = 0; words != '\0'; i++)
    {
        strcpy(mas[i], words);
        words = strtok(NULL, ", ");
        word_count++;
    }

    //replacing a word in the string
    for(int i=0;i < word_count;i++)
    {
        if(strcmp(mas[i],"players")==0)
            strcpy(mas[i],"ACTORS");
    }

    //displaying a new string
    printf("\nNew line: \n");
    for(int i=0; i < word_count; i++)
        printf("%s ", mas[i]);

    return (0);
}
```

The result:

Old line:
All the world's a stage, and all the men and women merely players
The actual length of the string is: 65
The first word is: All

New line:
All the world’s a stage and all the men and women merely ACTORS

To define the length of the string, we used the function `strlen()`. Then, set the
separator "space" and using the function `strtok()`, select and display the first
word. If there is a need to split the entire string into words, then you need to
use a loop and set a condition until `firstWord not NULL`:

```C
while(firstWord! = NULL)
{
   printf ("%s\n", firstWord);
}
```

### Working with Strings in Python

Python, like C and Java, has built-in functions that allow us to easily modify and
manipulate strings.

When a large string is given in a program, Python triple quotes come to the rescue,
the use of which enables strings to span multiple lines of code, including the
literal NEWLINE, TAB, and any other special characters. The triple quote syntax
consists of three consecutive single or double quotes. You can also use the string
properties to enter long lines:

- Consecutive strings are concatenated.
- Until we close the parenthesis, the expression will not end. So, we can write this:

```Python
str = ("first line \n"
       "second line")
```

Let us consider an example where you have a string, display it, determine its actual
length, and convert the lowercase letters in the word "world" to the corresponding
uppercase letters, replace a word in the string.

```Python
str = ("Some people want to change the world! \n"
       "They think it's their own. \n"
       "They seem to be so cute and bold, \n"
       "They're pleased to be well known. ")
size = len(str);
print("\nOld string:\n", str)
print("The actual length of the string is:", size)
word_to_upper_case = "world"
if (str.find(word_to_upper_case) != -1):
    print (word_to_upper_case.upper())
else:
    print ("String doesn't contain the word 'world'")
str = str.replace("Some people","We")
print("\nNew string:\n", str)
```

The result:

Old string:
 Some people want to change the world!
They think it's their own.
They seem to be so cute and bold,
They're pleased to be well known.
The actual length of the string is: 136
WORLD!

New string:
We want to change the world!
They think it's their own.
They seem to be so cute and bold,
They're pleased to be well known.

## Recursions

**Recursion** is one of the powerful tools for writing algorithms. Recursion comes
directly from mathematics where there are many examples of expressions written in
terms of themselves. You can learn more about this in Basic Math for IT Module,
Submodule "Recursive Functions".

In your life, you have probably seen endless recursion entering a fitting room
with two mirrors on opposite walls. In programming, a recursive function is a
function that is directly or indirectly called within the same function (within
itself), and it should be a finite version of recursion.

The ability to call directly or indirectly allows you to distinguish:

- An **indirectly** recursive function if it contains a call to another function
  that contains a direct or indirect call to the first (its) function. In this case,
  according to the text of the definition of a function, its recursiveness (indirect)
  may not be visible.
- If a function uses a call to the same function, then there is a **direct** recursion,
  i.e. the function is recursive by the definition.

When writing a recursive function, we are creating an infinite loop, i.e. the
function calls itself ... and can never stop. Therefore, in recursive functions,
you must use the following rules:

- At each call to a function, transfer the changed data
- After the completion of the next call to a recursive function, some result must
  be returned to the calling function for further use
- At some step, the further call of a recursive function must be terminated. A
  recursive process should step by step simplify the problem so that a non-recursive
  solution appears for it. Therefore, there are always two cases in a recursive
  function: recursive and base cases

Consider the major pros and cons of recursion:

- Pros of recursion:
  - The implemented code is rather compact and simplifies a more complex program.
  - Fewer variables are usually used in program code.
  - Complex code and complex nesting of loops are avoided.

- Cons of recursion:
  - When performing recursion, more memory is usually used for formal variables
    due to the work with the stack of all function calls. Thus, recursion can
    cause memory overflow.
  - It sometimes runs slower when performing an iterative process where the same
    value is evaluated over and over again.

Recursive algorithms are effective in the problems where recursion is used in the
very definition of the data being processed. For example, the Fibonacci sequence
is defined as:
Fn = Fn-1 + Fn-2

C

Here is a simple example of a series of Fibonacci numbers. The program below
involves calling a recursive function defined as `countFib (int n)` that takes input
from a user, executes a for loop to generate each element, which is passed to
countFib(), and returns a Fibonacci series. Be sure to set the base case with an
if statement, checking for number = 1 or 2 to print the first two values. It should
be noted that in the example below, 0 is omitted and the series starts with the
number 1.

```C
#include <stdio.h>

int countFib (int n)
{
    if(n==0)
        return 0;
    if(n==1||n==2)
        return 1;
    else
        return (countFib(n-1) + countFib(n-2));
}
int main ()
{
    int n=0;
    printf("Enter number of N terms: \n");
    scanf("%d", &n);
    if(n==0)
    {
        printf("Fibonacci number is %d", countFib(0));
    }else{
        printf("Calculated Fibonacci number(s): ");
        for (int k=1; k <= n; k++)
        {
            printf("%d, ", countFib(k));
        }
    }
    return 0;
}
```

If we enter , the result will be:

Enter number of N terms: 7
Calculated Fibonacci number(s): 1, 1, 2, 3, 5, 8, 13,

Note that this code is ineffective. This can be seen, for example, in the counting
tree shown in the figure below. fib (7) and fib (6) are called 1 time, fib (5) –
2 times, fib (4) – 3 times, etc. In general, the number of calls to functions will
double at each step which, even at small numbers (such as 60), will cause a very
large number of calls, and even modern computers will find it difficult to do this
task.

Now consider recursion on a more efficient example of finding the greatest common
divisor (DCD). The program takes two positive integers as input from a user and
calculates GCD using recursion.

```C
#include <stdio.h>

int calculateGCD(int num1, int num2);
int main() {
    int num1 = 0;
    int num2 = 0;
    printf("Enter two positive integers: ");
    scanf("%d %d", &num1, &num2);
    printf("The greatest common divisor of %d and %d is %d.", num1, num2,
    calculateGCD(num1, num2));
    return 0;
}

int calculateGCD(int num1, int num2) {
    if (num2 != 0)
        return calculateGCD(num2, num1 % num2);
    else
        return num1;
}
```

The result:

Enter two positive integers: 121 561
The greatest common divisor of 121 and 561 is 11.

Python

Consider recursion on a more efficient example of finding the greatest common
divisor (DCD). The program takes two positive integers as input from a user and
calculates GCD using recursion.

```Python
def calculate_GCD(num1, num2):
    if (num2 == 0):
        return num1
    else:
        return calculate_GCD(num2, (num1 % num2))

num1 = int(input('Enter the first positive integer value: '))
num2 = int(input('Enter the second positive integer value: '))

print('The greatest common divisor of %d and %d is %d.' %(num1, num2, calculate_GCD
(num1, num2)))
```

The result:

Enter the first positive integer value: 121
Enter the second positive integer value: 957
The greatest common divisor of 121 and 957 is 11.

Test:

C

There are 3 teams that take part in the darts competition. Each team comprises
4 participants. Each participant has 3 attempts. The number of points that each
participant gets for one throw is entered from a keyboard. The maximum number of
points for 1 attempt is 60. Display the winner (i.e. the number of the participant
with the biggest number of points and his/her result) from each team. The participant
of which team showed the best result?

```C
#include <stdio.h>
#include <time.h>   //srand
#include <stdlib.h>//rand()

void input(int x[4][3], int n1,int m1);   //array input function
void output(int x[4][3], int n1, int m1); //array output function
int win(int x[4][3], int n1, int m1);     //winner determination function

int main()
{
    srand(time(NULL));  // The srand() function allows you to run a program multiple
    // times with different sequences of pseudo-random numbers.
    int x[4][3],y[4][3], z[4][3];
    const int n=4;
    const int m=3;

    printf("First team results\n");
  input(x, n, m);
  output(x, n, m);
  int first_win=win(x, n, m);
  printf("%d.\n",first_win);
  printf("\n");

  printf("Second team results\n");
  input(y, n, m);
  output(y, n, m);
  int second_win =win(y, n, m);
  printf("%d.\n",second_win);
  printf("\n");

  printf("Third team results\n");
  input(z, n, m);
  output(z, n, m);
  int third_win=win(z, n, m);
  printf("%d.\n",third_win);

  int max,num;

  if (first_win > second_win && first_win > third_win)
      max=first_win;
  else if (second_win > third_win)
      max=second_win;
  else max=third_win;

  if(max==first_win)
      num=1;
  else if(max==second_win)
     num=2;
  else num=3;
  printf("\nThe best result was shown by player of the team %d with a score
  of %d.\n",num, max);
  return 0;
}

void input(int x[4][3], int n1, int m1)
{
    int i,j;
  for (i=0;i<n1;i++)
    for (j=0;j<m1;j++)
      x[i][j]=rand()%61; // Entering random numbers in the range from 0 to 60
}

void output(int x[4][3], int n1, int m1)
{
    int i,j;
  printf("\n");
  for (i=0;i<n1;i++)
  {
    for (j=0;j<m1;j++)
      printf("%d ", x[i][j]);
    printf("\n");
  }
}

int win(int x[4][3], int n1, int m1)
{
    int i,j;
    int sum;
    int a[4];
    for (i=0;i<n1;i++)
    {
        sum=0;
        for (j=0;j<m1;j++)
        {
            sum+=x[i][j];
            a[i]=sum;
        }
        printf("Total score of %d player = %d\n", i+1, sum);
    }

    int imax_a=0;
    int max_a=a[0];
    for(i=0;i<n1;i++)
    {
        if(a[i]>max_a)
        {
            max_a=a[i];
            imax_a=i;
        }
    }
    printf("The winner is player %d with the score of ",imax_a+1);
    return max_a;
}
```

Python

```Python
team_count = 3
players_count = 4
team_results = []

max_team_number = winner_number = max_result = 0
for team_number in range(1, team_count+1):
    team_result = []
    max_for_player = max_player_number = 0

    for player_number in range(1, players_count + 1):
        player_score = input("Enter {} team {} player result: ".format(
            team_number,
            player_number,
        )).split()
        player_sum = sum([int(score) for score in player_score])
        if player_sum > max_for_player:
            max_for_player, max_player_number = player_sum, player_number

    print("Team {}. The winner is the player {} with the score of {}".format(
        team_number,
        max_player_number,
        max_for_player,
    ))

    if max_for_player > max_result:
        max_team_number, winner_number = team_number, max_player_number
        max_result = max_for_player

print("The best result was shown by player {} of the team {} with the score of {}".format(
    winner_number,
    max_team_number,
    max_result,
))
```

Result:

Enter 1 team 1 player result: 12 15 20
Enter 1 team 2 player result: 45 46 8
Enter 1 team 3 player result: 4 6 7
Enter 1 team 4 player result: 4 6 7
Team 1. The winner is the player 2 with the score of 99
Enter 2 team 1 player result: 6 45 5
Enter 2 team 2 player result: 4 60 60
Enter 2 team 3 player result: 4 6 7
Enter 2 team 4 player result: 6 8 7
Team 2. The winner is the player 2 with the score of 124
Enter 3 team 1 player result: 1 4 5
Enter 3 team 2 player result: 50 50 50
Enter 3 team 3 player result: 45 45 45
Enter 3 team 4 player result: 30 30 30
Team 3. The winner is the player 2 with the score of 150
The best result was shown by player 2 of the team 3 with the score of 150
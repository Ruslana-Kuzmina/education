# Introduction to Programming

- Each computer has a built-in instruction set and it knows how to execute it by
  design.
  - [x] True
  - [ ] False

- A computer executes instructions using its own intelligence.
  - [x] True
  - [ ] False

- Read the question below and select all correct answers. Then, click "Submit."

  - [x] A programming language is a set of rules that provides a way of telling
        a computer what operations to perform.
  - [ ] English is the main tool for developing executable models for a class
        of problem domains.
  - [x] A programming language provides a linguistic framework for describing
        computations.

- Computers help humans solve problems by automatically executing a sequence of
  instructions given to them and storing their results.
  - [x] True
  - [ ] False

- A(n) ___________ is a set of instructions, written by a coder, that enable computers
  to become useful.

  - [ ] Algorithm
  - [x] Computer program
  - [ ] System

- Which of the following is an interpreted programming language?
  - [x] Perl
  - [x] JavaScript
  - [ ] C++
  - [ ] Fortran
  - [ ] Pascal

## Data Types

- What will be displayed on your screen after running the following code?

```c
#include <stdio.h>

int main()
{
    printf( "Hello my dear friend!" )
    return 0;
}
```

- [ ] Hello my dear friend!
- [x] nothing since the code contains a syntax error
- [ ] "Hello my dear friend!"
- [ ] Hello my dear friend! Hello my dear friend!
- [ ] nothing since the code contains an algorithm error

Because he text (code) of the function is written in `{}`, i.e. a set of instructions
it executes, each of which ends with a ;

- How do you insert COMMENTS in Java code?
  - [ ] # This is a comment.
  - [x] // This is a comment.
  - [ ] /* This is a comment.

- In C, the size of an int variable and a long int variable is the same.
  - [x] True
  - [ ] False

- What will be displayed on your screen after running the following Java code?

```Java
class Main {
   public static void main(String args[]) {
         int a;
         System.out.println(a);
    }
}
```

- [ ] 0
- [x] nothing since the code contains a compile error
- [ ] 4
- [ ] nothing since the code contains a syntax error

- ________ is treated as a real number by default.

  - [ ] Float
  - [x] Double
  - [ ] Long
  - [ ] Long double

- Which of the following is a valid declaration in C?
  - [x] short int a;
  - [x] short a;
  - [x] unsigned short a;
  - [x] unsigned short int x;
  - [ ] unsigned short int int a;

- Which of the following is NOT a legal variable name in C?
  - [ ] int var_1;
  - [ ] int firstVar;
  - [ ] int first_var;
  - [x] int first-var;
  - [x] int 1var;

- How do you create a variable var with the numeric value 10 in C?
  - [ ] var = 10
  - [ ] char var = 10;
  - [x] int var = 10;
  - [x] int var=10;

### Operators, Expressions

- Choose the correct examples of variable assignment.
  - [x] x = 5
  - [ ] 5 = x + y
  - [ ] 5*2 = i
  - [x] x = 5*2
  - [x] x = y = z = 0
  - [x] x=x+4
  - [ ] x+1=y+2
  - [ ] x+4=x;

In the beginning we need to put function like x or y.

- What will be displayed as a result if an expression is (double)(5/3+6+8)?

  - [ ] 15
  - [ ] 15.667
  - [x] 15.00

We put this function in Java System.out.println((double)(5/3+6+8))

- Enter the correct operator to multiply 7 by 3, and print the result in Python:
  print(7__3). Be sure to enter only the operator into the field below.

  - [x] *

- Use the correct comparison operator to check if 7 is not equal to 3 in Python:
  if 7__3: print("7 and 3 is not equal"). Be sure to enter only the operator into
  the field below.

  - [x] !=

- __________ is used to compare the values of two operands.

  - [x] A relational operator

- What will be displayed on your screen after running the following C code?

```C
#include <stdio.h>

int main()
{
    int a = (4, 6, 8);
    printf("%d", a);
    return 0;
}
```

- [ ] 0
- [x] 8
- [ ] 4
- [ ] 6
- [ ] Compile time error

When using the assignment operator, the expression is evaluated from left to right.
And since the parenthesis operator has a higher precedence than the assignment
operator, because of the program execution, the last number from the parentheses
will be displayed, in this case, 8.

- Which one or more of the following operators are logical in C ?

  - [x] !
  - [ ] ^
  - [ ] &
  - [x] &&
  - [ ] |

- Which operator is used to get the remainder after the division?

  - [ ] //
  - [x] %
  - [ ] /
  - [ ] ^
  - [ ] *

- What is the answer if the following expression in C is evaluated?

`10 + 33 % 5 * 7 / 3 % 4 + 3`

- [ ] 16

## Basic Statement of Programming

- ________ statements allow programs to take into account the conditions and execute
  specific program instructions based on the taken decision.

  - [x] selection
  - [ ] iteraction

- In C or Java, in order to stop the loop if i is 6, you use:

```C
for(int i = 2; i < 12;i++){
    if(i == 6){
        _______;
    }
}
```

- [ ] case
- [x] break 
- [ ] goto
- [ ] continue
- [ ] stop

## Algorithm Design and Modern Software Process Models

- An iterative process of system development in which requirements are converted
  to a working system that is continually revised through risk analysis is
  called _______.

  - [ ] Waterfall Modeling
  - [ ] Kanban Modelling
  - [x] Spiral Modelling
  - [ ] Iterative Modelling

- What does the symbol below represent in a flowchart of a program in computer
  programming? rectangle

  - [ ] Decision
  - [ ] Start or end
  - [ ] Flow line
  - [x] Process

## Functions

- Which of the following statements is correct? Select all that correct ones in
  order to complete the phrase "We should use functions in programming …"

  - [x] to avoid duplicating some blocks of code.
  - [ ] to make a program more complex by increasing the number of lines of code.
  - [x] to break down a program into smaller parts.
  - [x] to make a program more readable and easier to modify.

- What is return used for?

  - [ ] This is an unconditional control transfer operator that completes the execution.
  - [x] This is an unconditional control transfer operator that returns the result
        of the function execution to the call point.
  - [ ] This is a function that ensures the transfer of the result to the call point.
  - [ ] This is a function that ends the execution of a function.

- What is the return type of the function with the following prototype?
  `double getFunc(char x, float v, int t);`

  - [ ] char
  - [x] double
  - [ ] float
  - [ ] int
  - [ ] void

- Which of the following is a valid function call to call the below function?

```C
void getValue(int num, char ch)
{
   printf("There is %d and %c.", num, ch);
}
```

- [ ] getValue num ch;
- [x] getValue(5, 'F');
- [ ] getValue();
- [ ] void getValue (num, ch);

## Structured Types

- Fill in the blank in the following block of code so that each element in the
  array is assigned a value of its index, incremented by 2.

```Java
int[] array = new int[15];
for ( int index=0; index < array.length; index++ )
{
     _______________________
}
```

- [ ] array[index+2] = index;
- [x] array[index] = index+2;
- [ ] array[index] = 2+array[ index -1];
- [ ] array[index] = 2*index;

- What is the length of the following array:
  `char[] word = { 'q','u','e','s','t','i','o','n' };`

  - [x] 8

- Arrays can be passed as parameters to a function either by value or by reference.

  - [ ] True
  - [x] False

Arrays can be passed as parameters to a function by reference. 

- Which of the following statements about Queue Data Structure is correct?

  - [x] A queue is a first-in, first-out (FIFO) data structure.
  - [ ] New nodes can only be added to the top of the stack.
  - [ ] A queue allows a node to be added or removed from the front (from the
        beginning).
  - [x] A queue uses two ends of the structure.

## Sorting Methods

- The given array is `array = {3,4,5,2,1}`. What is the actual number of swaps in
  Bubble Sort?

  - [x] 7

- Arrange the lines of the code in the correct order to perform selection sort.
  Exemple Selection sort in C

- Which sorting algorithm makes one swap per pass (possibly swapping an element
  with itself)?

  - [ ] Bubble Sort
  - [x] Selection Sort
  - [ ] Insertion Sort

- Which of the following is true about different sorting algorithms?

  - [x] Insertion Sort is the best algorithm to sort data as it arrives, one piece
        at a time; perhaps, from a network.
  - [ ] Quick Sort is a stable sorting algorithm in its typical implementation.
  - [ ] If a swap operation is very costly, the Merge Sort algorithm should be
        preferred so that the number of swap operations is minimized in general.
  - [x] The Selection Sort algorithm searches through the remaining elements of
        the list for the best element to exchange with the current element, and
        after the completion of the pass, if the required element is found, one
        swap will be made.

## Files

- What is the last action that must be performed on a file in programming?

  - [ ] Update
  - [x] Close
  - [ ] End
  - [ ] Write
  - [ ] Read

- What syntax should be used to write a file in C using binary mode?
  `FILE *newF;`

  - [ ] newF = fopen("new.txt","wr")
  - [x] newF = fopen("new.txt","wb")
  - [ ] newF = fopen("new.txt","a")
  - [ ] newF = fopen("new.txt","b")

- Which C functions are used to read or write a file in Text Mode?

  - [ ] printf(), scanf()
  - [x] fprintf(), fscanf()
  - [ ] read(), write()
  - [ ] input(), output()

- When fopen() is not able to open a file, what does it return in C?

  - [x] NULL
  - [ ] EOF
  - [ ] Runtime Error
  - [ ] −1

## Object-Oriented in Programming

- Which of the following is not a part of OOP?

  - [ ] polymorphism
  - [x] multitasking support
  - [ ] type checking
  - [ ] hiding information
  - [ ] creating derived classes

- Encapsulation indicates that the internal description of an object is fully
  accessible to external code in Java.

  - [ ] True
  - [x] False

- Which of the following is the mechanism of "hiding" data and the methods of a
  class from the "outside world" by making them private in Java?

  - [ ] Inheritance
  - [x] Encapsulation
  - [ ] Abstraction
  - [ ] Polymorphism

- Read the question below and select all correct answers. Then, click "Submit."
  Which of the following statements is correct (in Java)?

  - [x] A default constructor, which is not defined by a programmer, always
        initializes the values as zero for numeric values, and null for string
        values.
  - [ ] A default constructor cannot be called explicitly.
  - [ ] There are 4 types of constructors in general, namely, default constructors,
        parameterized constructors, static constructors, and copy constructors.
  - [x] Constructors are special functions, whose return type is not defined and
        is not even void.

- Read the question below and select all correct answers. Then, click "Submit."
  assessment.
  Complete the following Java code to run the following program

```Java
______ Quiz {
  int count;
  Quiz(int count) {
    this.count=count;
  }
}
class QuizMain {
  public static void main (String[] args) {
        Quiz score = new ______(100);
        System.out.println("You get " + _____.count + " points!");
  }
}
```

- [x] class
- [ ] Static
- [x] Quiz
- [ ] obj
- [x] score
- [ ] count
- [ ] this




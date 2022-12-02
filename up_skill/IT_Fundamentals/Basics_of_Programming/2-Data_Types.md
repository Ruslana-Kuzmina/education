# Data Types

## Symbols and Words

As you know, the program consists of a sequence of instructions coded in strict
accordance with the rules that make up the syntax of the language.

The following basic errors can be made when creating programs:

- Algorithm - are the result of a discrepancy between the constructed algorithm
  and the course of obtaining the result of the task

- Semantic - when there is a misinterpretation of the meaning (semantics) of the
  operators of the selected programming language

- Logical - are divided into algorithm errors and semantic errors

- Syntax - due to a violation of the rules of program writing

The alphabet of any language is a set of **symbols** – those indivisible signs
necessary for writing all texts in the given language:

- Each of the set of values defined by one byte (from 0 to 255) is assigned a symbol
  on the computer character generator table.
- According to the IBM encoding,
  - characters with codes from 0 to 127, which form the first half of the character
    generator table, are built according to the ASCII standard and are the same for
    all computers;
  - the second half of the characters (codes 128 – 255) may differ and they are usually
    used to locate the characters of the national alphabet;
  - codes 176 – 223 are reserved for pseudo-graphic characters;
  - codes 240 – 255 - for special characters.

The standard alphabet of programming languages we are considering comprises:

- Uppercase and lowercase letters of the Latin alphabet and underscore (code 95)
- Arabic numerals from 0 to 9
- special characters, whose meaning and rules of use will be considered in the text
- whitespace (separator) characters: space, tab, line feed, carriage return, new
  page and new line

**Tokens** (or elementary constructions) of the language are formed from the symbols
of the alphabet (the minimum significant units of the text in the program) and are
the so-called building blocks or the basic components.

The following basic errors can be made when creating programs:

- Key (reserved) world

- Identifiers
  In a simple language, identifiers are user-defined words to name variables, classes,
  functions, arrays, structures, labels, etc. The punctuation like ! @ $ % & * and
  keywords cannot be used as variable names (or identifiers) as they are part of
  the programming language syntax.

- Operators
  An operator is a special symbol that is used to perform a mathematical or logical
  operation. There are three types of operators: unary, binary, and ternary.

- Constants
  A constant is a value which does not change during program execution.

- Strings
  A string is always an array of several characters (size of a string) having null
  character '\0' at the end of the string. This null character denotes the end of
  the string. Strings are often enclosed in double quotes, while characters are
  enclosed in single quotes.

- Delimiters
  - brackets (, ), {, }, [, ],<, >
  - a period
  - a comma
  - a semicolon
  - an asterisk - used to create a pointer variable in C/C++
  - **whitespace** - some characters which are frequently used but they are invisible
    in your program and these characters are spaces, tabs (\t), new lines(\n))

For example, a newline character (\n) sets the active position to the beginning
of the next line, a carriage return (\r) moves the active position to the beginning
of the current line.

It should be noted that these escape sequence characters do not necessarily work
with all display devices (whitespace). For example, the form feed (\f) and vertical
tab (\v) characters produce odd symbols on a PC screen instead of any cursor movement,
but they work as described if sent to a printer instead of to the screen.

A **lexeme** is a sequence of characters in the source program that matches the pattern
for a token and is identified by the lexical analyzer as an instance of that token.
Some authors term this a "token", using "token" interchangeably to represent
the string being tokenized, and the token data structure resulting from putting
this string through the tokenization process.

Another basic element of a programming language – a **comment** – is not a token.
Any characters allowed on the given computer can be used inside a comment, since
the compiler ignores them, and these comments are used to make the programs
user-friendly and easy-to-understand.

In any language, comments are limited to the pairs of characters /* and */, and
in C ++/Java/Js, a variant of the comment was introduced that begins with the characters
// and ends with a newline character. In Python, the # character is used to start
a comment and it continues until the end of the line.

## The Structure of a Simple Program

- document section
- definition section
- main function
- preprocessor / link section
- global declaration section
- user defined function section
- main function declaration section

Basic Structure of C Program

```C
#include <stdio.h>

int main(){
    printf("Welcome to the basics of programming!");
    return 0;
}
```

```Java
public class FirstProgram {
   public static void main(String []args) {
      /* println() function to write Welcome to the basics of programming! */
      System.out.println("Welcome to the basics of programming!");
   }
}
```

Let's take a closer look at our example. In Java, all code elements are contained
in classes denoted by the `class` keyword. In our example, the `public` keyword
is an access modifier which represents visibility and means it is visible to all.

If we declare any method by using the `static` keyword, it is known as the static
method and there is no need to create an object to invoke this method. It saves memory.

The program starts with `main()`, which is executed by the JVM. `String[] args`
is used for the command line argument.

`System.out.println()` is used to display a specified phrase on the screen. Here,
`System` is a class, out is the object of `PrintStream class`, `println()` is the
method of `PrintStream class`.

Python

`#print function to write some text`

print ("Welcome to the basics of programming!")

```JavaScript
console.log("Welcome to the basics of programming!")
```

## Basic Data Types

We deal with different types of data such as strings, characters, whole numbers
(integers), decimal numbers (floating-point numbers), etc.

The data type defines:

- internal representation of data in random-access memory (RAM)
- a set of values (range) that data of this type can receive
- a set of operations that are allowed on such data.

Python Data Types:

- Numeric
  - Complex number
  - Integer
  - Float

- Dictionary

- Boolean

- Set

- Sequence type
  - Strings
  - List
  - Tuple

Having standard data types, Python does not make use of any keywords to specify
a particular data type. However, this programming language is intelligent enough
to understand a given data type automatically.

Numbers: int, float, complex
String: str
Sequence: list, tuple, range
Mapping: dict
Set Types: set, frozenset
Boolean: bool
Binary Types: bytes, bytearray, memoryview

Here, Number specifies all types of numbers including decimal numbers and String
represents a sequence of characters with a length of 1 or more characters. For now,
let us proceed with these two data types and skip List, Tuple, and Dictionary, which
are advanced data types in Python.

## Variables

A **variable** is a storage unit which allocates some space in memory to hold a value
and can take different values at different times during program execution. Before
using a variable in any program, it has to be **declared** to allocate the amount
of memory for the variable in accordance with its type; in this case, it can be
initialized, i.e. set its initial value.

In addition to the constants specified in the source text, all program objects must
be explicitly declared in the following format:

`<Attributes> <List of object IDs>`

where the elements of the Object ID List are separated by commas, and Attributes
are separated by separators, for example:

int i, j, k;
float a, b;

Program data can have the following attributes:

- Memory class
  A characteristic of the way the objects are located in memory (extern, static,
  and dynamic); defines the scope and lifetime of the variable (by default – auto).

- Type
  The type of future values of the declared objects (by default, the int type is
  set).

Memory class and type are optional attributes and if one of them is missing (but
not both at the same time), the default attributes are set.

Consider the example with two numbers again. Suppose you want to store two values
2 and 3 in your program and, at a later stage, you want to use these two values.
To accomplish this task, you need to:

- Create variables with appropriate types to reserve two memory locations with the
  specified names
- Store your values in those variables
- Retrieve and use the stored values from the variables

Different programming languages have different ways of creating variables inside
a program.

### Rules to Construct a Valid Variable Name

There are certain rules for defining a valid identifier in programming languages.
These rules must be followed; otherwise, we get a compile-time or a runtime error.
Below are the basic rules for naming variables in Python? C++:

- Case sensitive
  Identifiers are case-sensitive. That means age and Age are two different identifiers.

- Latin Characters
  The only allowed characters for identifiers are all alphanumeric characters ([A-Z],
  [a-z], [0-9]), ('$'(a dollar sign) in C/C++ and Java) and '_' (underscore). For
  example, @ge is not a valid identifier as it contains '@' special character.

- A number is not yhe first
  Identifiers should not start with digits ([0-9]). For example, 23age is not a
  valid Java identifier while age23 is.

- No space
  No space characters are allowed. If the variable is described by several words,
  the underscore character ( _ ) should be used between the words. For example,
  my age is a not a valid Java identifier while my_age or myAge is.

- Lenght
  An identifier can be of any length.

Although these are strict rules for writing identifiers, there are also some naming
conventions which are not mandatory but rather good practices to follow:

Class names start with an uppercase letter in Java. All other identifiers start
with a lowercase letter.
While int a = 23; is valid, writing int age = 23; would make more sense, and it
would be easier to figure out what it does even when you look at your code after
a long time.

C

```c
#include <stdio.h>

int main(){
   int one;//declaration
   int two;//declaration

   one = 2;//assignment
   two = 3;//assignment

   printf("The first value = %d\n", one);
   printf("The second value = %d\n", two);
}
```

Result:

```c
The first value = 2
The second value = 3
```

```c
#include <stdio.h>

int main(){
   int one=2, two=3;//declaration and assignment

   printf("The first value = %d and the second value = %d.\n", one, two);
}
```

Result:

```c
The first value = 2 and the second value = 3.
```

Java

```Java
public class FirstProgram {
   public static void main(String []args) {
   int one; //declaration
   int two; //declaration

   one = 2; //assignment
   two = 3; //assignment

   System.out.println("The first value = " + one);
   System.out.println("The second value = "+ two);
   }
}
```

Result:

```Java
The first value = 2
The second value = 3
```

Python

The following is the equivalent program written in Python. This program will create
two variables a and b, and, at the same time, assign 2 and 3 in those variables.
As we discussed, Python does not want you to specify the data type at the time of
variable creation and there is no need to create variables in advance.

```python
a = 2
b = 3
print("Value of a =", a)
print("Value of b =", b)
print("Value of a =", a,"and value of b =", b)
```

When the above program is executed, it produces the following result

```python
Value of a = 2
Value of b = 3
Value of a = 2 and value of b = 3
```

## Input and Output

Operating systems have standard system streams (pipes) that are automatically opened
at the beginning of program execution:

**stdin** — standard data input stream (stream number 0) is reserved for reading
user commands or input.
**stdout** — standard data output stream (stream number 1) for programs is reserved
for outputting data, usually (although not necessarily) a text.
**stderr** — standard error output stream (stream number 2) is reserved for outputting
diagnostic and debug messages in a text form. If a program is unable to do everything
as it should, it writes to this thread.

Different programming languages have different ways of accessing these streams.

In programming, in order to organize communication between a user and a computer,
there are functions for entering information from external sources (for example,
files, a keyboard, a network, output from another program, etc.) and giving the
result as output (in many cases it happens on the monitor of a screen). For now,
we will assume that input and output are basic commands. Without input, programs
would do the same thing, unless they generated random values themselves. The output
allows you to see, use, and pass on the result of the program.

C

С language has a standard library stdio.h or a standard input-output library that
has methods for input and output.

In C, to input information, the following functions are most frequently used:

`gets()` — a function designed to enter phrases consisting of words separated by
spaces.
`getch()` — a function designed to enter characters, it responds to button presses
and does not require Enter button to be pressed. This function is often used in
case you need to view some work results when displaying them on the monitor screen.
Therefore, you can use it to navigate the menu, for example.
`scanf()` — a function designed for formatted input of source information from
the keyboard.

Consider the difference between the `scanf()` methods we recorded: in the first case,
we enter a string, and in the second, we work with numeric data. As you can see,
the form is different.

The format of the function:

`scanf("%X", &list_of_XType_variables);`

`%X` - We specify format modifiers, the number and order of which must match the
number and order of the input objects, and the data type will be converted in
accordance with the modifiers.
`&` - The & symbol is specified before list_of_XType_variables, which denotes the
"take address" operation and is not used for string variables. This identifier tells
the compiler to change the real value of this variable stored at this memory address.
It is not used for string variables.
`list_of_XType_variables` - We must indicate the addresses of the variables, separated
by commas.
`%d` (%i) — a decimal integer
`%c` — one character
`%s` — a character string that is entered only up to the first space
`%f` — a floating point number, decimal notation
`%h` — a short integer.

If you try to run the above example without seeing the code comments, you will not
be able to figure out what the program wants from you. And even if you guess the
types of data you need to enter, you will not see anything in the output. To output
information to the monitor screen (display) in C language, the following function
is most frequently used:

`printf()`

```c
#include <stdio.h>

int main(){
    char city [20];
    scanf("%s", city);
    printf("%s \n", city); //Output city
    int population;
    scanf("%d", &population);
    printf("%d people\n", population); //Output population
    return 0;
}
```

The result:

```c
Minsk
2000000 people
```

`printf(control_String, list_of_Output_Objects);`

`control_String` - Contains some explanatory text (comments), enclosed in quotation
marks, which is displayed unchanged on the screen. It may also contain a list of
format modifiers (the % character as for scanf() functions) that tells the compiler
how to display objects and special characters (for example \n).
`list_of_Output_Objects` - It specifies the identifiers of printable objects,
separated by commas: variables, constants, or expressions that are evaluated
before being printed. The number and order of the formats must match the number
and order of the objects displayed on the screen.

Besides those format modifiers which are specified for `scanf()` function, the
following modifiers can be also used in control_String:

`%g` — used instead of %f, %e to exclude insignificant zeros
`%o` — an unsigned octal number
`%x` — an unsigned hexadecimal number.

The `printf()` function outputs data in accordance with the specified formats,
so the format can be used to convert the types of output objects.

```c
#include <stdio.h>

int main(){
    char city [20];
    printf("Enter the city where you live: ");
    scanf("%s", city);
    printf("%s \n", city);
    printf("Enter the population of your city (in millions): ");
    float population;
    scanf("%f", &population);
    printf("%f million people\n", population);
    return 0;
}
```

Result:

```c
Enter the city where you live: Minsk
Enter the population of your city (in millions): 2.000000 million people
```

You can see that the displayed number is very long. It can be formatted.

In the format modifiers of the `printf()` function, after the `%` character, you
can specify a number that sets the minimum width of the output field, for example,
%5d - for integers, %4.2f - for real ones - two digits after the decimal point for
a field with the width of 4 characters. If the specified positions are not sufficient
to display the integer part of the number, then an automatic expansion occurs.
If a minus sign is specified after the %, then the displayed value will be printed
from the left position of the output field of the specified width, for example, %-10d.

```c
printf("%.3f million people\n", population);
```

you will see the formatted output:

```c
2.000 million people
```

`puts()` - A function that displays a string of characters on the display screen,
automatically adding a newline character (\n) to it. The analog of this function
would be:

```c
printf("%s \n", line ID);
```

Java

To interact with the console, Java uses the System class, and its functionality
actually provides console input and output. We will discuss class, object, and
public later.

The in object is defined in the System class to receive input from the console.
However, it is not very convenient to work directly through the System.in object,
therefore, as a rule, the Scanner class is used, which, in turn, uses System.in.

Since the Scanner class is in the java.util package, we first import it using the
import java.util.Scanner package. To create the Scanner object itself, a System.in
object is passed to its constructor. After that, we can receive the input values.

```java
Scanner input = new Scanner(System.in); //create an object of Scanner
int age = input.nextInt(); //take input from the user
```

The Scanner class has a number of other methods that allow you to get user-entered
values for each primitive type:

`next()`; reads the entered line up to the first space
`nextLine()`; reads the entire entered line
`nextInt()`; reads the entered int
`nextDouble()`; reads the entered double
`nextBoolean()`; reads the Boolean value
`nextByte()`; reads the entered byte
`nextFloat()`; reads the entered float
`nextShort()`; reads the entered short number

To create an output stream, an out object is defined in the System class. This
object defines the `println()`, `print()`, and `printf()` methods:

`System.out.println()`; allows you to print a certain value to the console and
then move the console cursor to the next line
`System.out.print()`; allows you to print a certain value to the console
`System.out.printf()`; allows you to print a certain formatted value to the console.
As well as in C for printf(), we can use a number of specifiers for other data types
(for example, %f, %d, %s, %c).

Python

Python provides many built-in input and output functions that are easily available
to us. The `input()` function is responsible for entering data into a program from
the keyboard in Python. If you have entered something, it may immediately appear
on the screen:

```python
input('What is your name?')
Enter:

Mary
Result:

Mary
```

If the input function passes the input to the program and assigns it to a variable,
then the interpreter does not immediately output the string: `answer = input()`.
The string is stored in the variable answer, and if desired, we can print its value
to the screen using the output function at the time we need it.

By default, the `input()` function accepts user input as a string. To get input
as a number, you need to convert the string to the appropriate type with the `int()`,
`float()`, or `complex()` conversion functions along with the input function.

As we saw earlier, the `print()` function is used to display data on the screen.

The actual syntax of the `print()` function is:

```python
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```

- objects: the value(s) to be printed
- sep:     a separator between the values (the default is a space character)
- end:     printed after all values (it defaults into a new line)
- file:    the object where the values are printed (default value is sys.stdout (screen))
- flush:   (Optional) A Boolean expression, which specifies if the output is
           flushed (True) or buffered (False — by default). Default: False.

For example:

```python
print('%d %s cost $%.2f' %(10, 'candies', 3.5))
```

The result will be:

`10 candies cost $3.50`

Python also provides methods for formatting output information (for example, `str.format()`).
When displaying information, curly braces `{}` are used as placeholders. Using
`%`, we can also format strings just like `printf()` is used in the C programming
language.

When entering data from a keyboard, there should be a display of explanations
on the screen – what to enter, i.e. a dialogue should be organized. For control
purposes, immediately after input, output the initial data to the display (at
least during debugging).
A user may enter incorrect data, for example, make a mistake with the type. Before
running the program, prepare test cases containing the input data and the expected
results. Separately, you need to check the reaction of the program to obviously
incorrect initial data. For such situations, it is necessary to provide the display
of messages, for example, "Error! There is no solution."

```Python
name = input('Enter your name')
age = int(input('Enter your age'))
print('Your name is %s. You are %s years old.' %(name, age))
print('In 2 years you will be', age+2, end='!')
```

The result:

```python
Enter your name: Mary
Enter your age: 14
Your name is Mary. You are 14 years old.
In 2 years you will be 16!
```
# Operators and Expressions

## Arithmetic and Assignment Operators

result = a + b

= and + operators
a and b operands

**Operators** are symbols that help us perform certain calculations on one, two,
or more operands. An operand can be a constant, a variable, or a function result.
A specific action based on an operator is called an **expression**.

According to the number of operands participating in operations, there are three
types of operators:

- **unary** operators that operate with a single operand
- **binary** operators that operate with two operands
- **ternary** (conditional) operators that operate with three operands

An **assignment operator** is used to copy a constant, literal, variable expression
result, or a function result to a variable that is a left-side operand and has
the following notation:

`Operand_1 = Operand_2`

In programming languages, the following shorthand notation for the assignment
operation is often used, where `#` is any arithmetic operation (operation on the
bit representation of the operands):

`Operand_1 # = Operand_2`

instead of the notation:

`Operand_1= Operand_1 # Operand_2;`

For example, if we want to increase some type value x by 3, we can write
x = x + 3; or x += 3;. Both are correct.

In programming languages, there are **lvalue** and **rvalue** expressions, which
are rather fundamental theoretical concepts of the language. Coming across them
while programming, it might not immediately be clear what exactly they mean. In
particular, when compilation errors occur, these terms are often mentioned in the
description of these errors and it may not be instantly clear where the error was
made. For example, the following C code:

a = b;
a - lvalue
b - rvalue

C

Division - is used to divide two operands and gives the quotient as the answer
`a / b`
5/3=1

Modulo - is used to divide two integer operands and gives the remainder after
the division
`a % b`
5%3=2

Increment - is used for incrementing the value by 1

Pre-Increment - value is incremented first and then the result is computed
++a

Post-Increment - value is first used for computing the result and then incremented
a++

Decrement - is used for decrementing the value by 1

Exemples in C:

```C
#include <stdio.h>

int main()
{
    int a=9,b=4;
    printf("Addition = %d + %d = %d \n" , a, b, a+b);
    printf("Subtraction = %d - %d = %d\n", a, b, a-b);
    printf("Multiplication = %d*%d = %d\n", a, b, a*b);
    printf("Division = %d/%d = %d\n", a, b, a/b);
    printf("Remainder = %d/%d = %d\n\n", a, b, a%b);

    printf("Unary minus = %d\n",-b);
    printf("Post-Increment a++ = %d ", a++); // we display 'a' and then a = a+1 (9+1=10);
    printf("and Pre-Increment ++a = %d\n", ++a); //a=a+1 (10+1=11) and then display
    it

    printf("Post-Decrement b-- = %d ", b--); // we display 'b' and then b = b-1 (4-1=3);
    printf("and Pre-Decrement --b = %d\n", --b); //b=b-1 (3-1=2) and then display
    it
    return 0;
}
```

The result:

```C
Addition = 9 + 4 = 13
Subtraction = 9 - 4 = 5
Multiplication = 9*4 = 36
Division = 9/4 = 2
Remainder = 9/4 = 1

Unary minus = -4
Post-Increment a++ = 9 and Pre-Increment ++a = 11
Post-Decrement b-- = 4 and Pre-Decrement --b = 2
```

```C
#include <stdio.h>

int main()
{
    float a=9.0,b=4.0;
    printf("Addition = %.2f + %.2f = %.2f \n" , a, b, a+b);
    printf("Subtraction = %.2f - %.2f = %.2f\n", a, b, a-b);
    printf("Multiplication = %.2f*%.2f = %.2f\n", a, b, a*b);
    printf("Division = %.2f/%.2f = %.2f\n\n", a, b, a/b);

    printf("Unary minus = %.2f\n",-b);
    printf("Post-Increment a++ = %.1f ", a++); // we display 'a' and then a = a+1
    (9.0+1=10.0);
    printf("and Pre-Increment ++a = %.1f\n", ++a); //a=a+1 (10.0+1=11.0) and then
    display it

    printf("Post-Decrement b-- = %.1f ", b--); // we display 'b' and then b = b-1
    (4.0-1=3.0);
    printf("and Pre-Decrement --b = %.1f\n", --b); //b=b-1 (3.0-1=2.0) and then
    display it
    return 0;
}
```

The result:

```C
Addition = 9.00 + 4.00 = 13.00
Subtraction = 9.00 - 4.00 = 5.00
Multiplication = 9.00*4.00 = 36.00
Division = 9.00/4.00 = 2.25

Unary minus = -4.00
Post-Increment a++ = 9.0 and Pre-Increment ++a = 11.0
Post-Decrement b-- = 4.0 and Pre-Decrement --b = 2.0
```

```C
#include <stdio.h>

int main()
{
    int a=5;
    float b=2.0;
    printf("Addition = %d + %.1f = %.1f \n" , a, b, a+b);
    printf("Subtraction = %d - %.1f = %.1f\n", a, b, a-b);
    printf("Multiplication = %d*%.1f = %.1f\n", a, b, a*b);
    printf("Division = %d/%.1f = %.1f\n\n", a, b, a/b);

    return 0;
}
```

The result:

```C
Addition = 5 + 2.0 = 7.0
Subtraction = 5 - 2.0 = 3.0
Multiplication = 5*2.0 = 10.0
Division = 5/2.0 = 2.5
```

If we use one float type operand and one integer type operand, the resulting value
will be float type according to the type conversion rules that will be discussed
later.

Python

Division - is used to divide two operands and gives the quotient as the answer
(The result always has type float.)
a / b

Float or Integer Division - is used to divide two operands and gives as the answer
the quotient rounded to the next smallest whole number
a // b

Modulo - is used to divide two integer operands and gives the remainder after the
division
a % b

Exponent - is used for exponentiation and equals pow()
a ** b

```Python
a=9
b=7
print("a + b =", a + b)
print("a - b =", a - b)
print("a * b =", a * b)
print("a^2 = ", a ** 2)
print("a / b =", a / b)
print(" floor a / b =", a // b)
print(" remainder a / b =", a % b)
print("Unary minus =",-b)
print("Unary plus =",+b)
```

The result:

```Python
a + b  = 16
a - b = 2
a * b = 63
a^2 =  81
a / b = 1.2857142857142858
floor a / b = 1
remainder a / b = 2
Unary minus = -7
Unary plus = 7
```

## Typing and Type Conversion

Programming languages are usually divided into two big camps based on typing:

- Intyped (Typeless)
  All entities are considered simply sequences of bits of varying length. For example,
  an assembly language, Forth. It cannot be further divided into any other types.
  The main advantages are the efficiency of the resulting code and the transparency
  of instructions. With the knowledge of the language, there is usually no doubt
  that this or that code exists. Among the disadvantages, the absence of checks
  stands out, without which subtle errors can occur. These are mainly low-level
  languages that work with bits at the level of hardware, registers, and memory
  cells, so you cannot do without them. However, it would be inconvenient to use
  them for industrial development of business applications, where it is important
  to model objects, phenomena, processes.

- Typed
  The programming language specification allows only those automatic type conversions
  that do not lose information (i.e., strictly require dialing rules). For such
  programming languages, it is important in principle to use different data types
  as add-ons over their bit representation. After all, you can use operators only
  in relation to typed data. For example, C, Python, Scala, PHP.

Typed languages are divided into several overlapping categories:

- Strong vs. Weak Typing
- Static vs. Dynamic Typing
- Explicit vs. Implisit Typing

All these categories intersect, for example, C has static weak explicit typing,
and Python has dynamic strong implicit typing.



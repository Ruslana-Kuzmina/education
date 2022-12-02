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

|Programming Language|Static vs. Dynamic|Strong vs. Weak|Explicit vs. Implicit|
|--------------------|------------------|---------------|---------------------|
|JavaScript          |Dynamic           |Weak           |Implicit             |
|Ruby                |Dynamic           |Strong         |Implicit             |
|Python              |Dynamic           |Strong         |Implicit             |
|Java                |Static            |Strong         |Explicit             |
|PHP                 |Dynamic           |Weak           |Implicit             |
|C                   |Static            |Weak           |Explicit             |
|C++                 |Static            |Weak           |Explicit and implicit|

## Relational and Logical Operators

**Relational operators** are used to compare values of the first operand with the
second one. Operands can be any arithmetic expressions and pointers. Arithmetic
operands are converted according to the same rules as for arithmetic operations.
If the relation is true, then the value of a relational expression is '1', and if
the relation is false, then the value of the expression is '0'.

The general view of relations operations is:

`«Operand_1 Operation sign Operand_2»`

### Relational Operators

|Description             |Expression| Relation  | Value of the Expression|
|------------------------|----------|-----------|------------------------|
|less than               |a < b     |false      |0                       |
|less than or equal to   |a <= b    |false      |0                       |
|equal to                |a == b    |false      |0                       |
|not equal to            |a != b    |true       |1                       |
|greater than            |a > b     |true       |1                       |
|greater than or equal to|a >= b    |true       |1                       |

The assignment operator (=) and equality operator (==) are entirely different.
You can confuse between the two and use one in the place of the other one, and
make a logical error if you use '=' in an expression instead of '=='. If you are
not Mary but you use '=' in the program, you will become Mary.

#### Logical Operators

|Name                 |Description                                        |C/Jav/JavScript Operation|
|---------------------|---------------------------------------------------|-----|-------------------|
|Logical NOT operator |is used for inverting a Boolean value              |  !  |     !cond         |
|Logical AND          |gives the net result true if all of the conditions |     |                   |
|                     |are true; otherwise, the result is false           | &&  | (a>0)&&(b>0)      |
|Logical OR           |gives the net result false if all of the conditions|     |                   |
|                     |are false; otherwise, the result is true           |  || |(a>0) || (b>0)     |

Python

|Name                |Description                                        |Operator    |Operation     |
|-----------------   |---------------------------------------------------|------------|--------------|
|Logical NOT operator|is used for inverting a Boolean value              |    not     |(a>0 and b>0) |
|Logical AND         |gives the net result true if all of the conditions |            |a>0) and (b>0)|
|                    |are true; otherwise, the result is false           |    and     |(a and b)     |
|Logical OR          |gives the net result false if all of the conditions|            |a>0) or (b>0) |
|                    |are false; otherwise, the result is true           |     or     |(a or b)      |

The relational operators are generally used in **if...else statements** and
**loops**, the details of which will be discussed in Submodule 5. In our next
programming examples, we will use an if-statement to illustrate the use of relational
and logical operators. If the given expression is true "(non-zero)", then the next
statement is executed; otherwise, the next statement is skipped.

C

```C
#include <stdio.h>

int main() {
   int a = 9;
   int b = 4;

   if ( a < b ) {
        printf("This will never print because it is false.\n" );
   }
   if ( a <= b ) {
        printf("This will never print because it is false.\n" );
   }
   if ( a == 4 ) {
        printf("This will never print because it is false.\n" );
   }
   if ( b == 4 ) {
        printf("The expression (b == 4) is true.\n" );
   }
   if ( a != b ) {
        printf("The expression (a != b) is true.\n" );
   }
   if ( a > b ) {
        printf("The expression (a > b) is true.\n" );
   }
   if ( a >= b ) {
        printf("The expression (a >= b) is true.\n" );
   }
   if ( 1 && 0 ) {
      printf("This will never print because condition is false.\n" );
   }
   if ( (a != b) && (a > b) ) {
      printf("This will be printed because both conditions are true.\n" );
   }
   if ( (a != b) || (a < b) || ( a == 4 ) ) {
      printf("This will be printed because one of the conditions is true.\n" );
   }
   if ( !(a && b) ) {
      printf("This will never be printed because the condition is false.\n" );
   }
}
```

The result:

```C
The expression (b == 4) is true.
The expression (a != b) is true.
The expression (a > b) is true.
The expression (a >= b) is true.
This will be printed because both conditions are true.
This will be printed because one of the conditions is true.
```

```C
#include <stdio.h>
int main()
{
    int a = 3, b = 4;
    printf("\n%d", a == b);
    printf("\n%d", a != b);
    printf("\n%d", a > b);
    printf("\n%d", a < b);
    printf("\n%d", a >= b);
    printf("\n%d", a <= b);
    return 0;
}
```

The result:

0
1
0
1
0
1

Python
Let us take two variables a = 41 and b = 11, and form simple relational expressions
with them.

```Python

a=41
b=11
result = a==b
print("a==b =", result)
result = a!=b
print("a!=b =", result)
result = a>b
print("a>b =", result)
result = a<b
print("a<b =", result)
result = a<=41
print("a<=41 =", result)
result = a>=42
print("a>=42 =", result)
```

The result:

a==b = False
a!=b = True
a>b = True
a<b = False
a<=41 = True
a>=42 = False

##### Bitwise Logical and Other Operators

C, Java, Python, and JavaScript have the ability to support the manipulation of
data at the bit level. Bitwise operators are used for operations on individual
bits. They only operate on integers that can be also written in the binary format.

Assume a = 41 and b = 11. In the binary format, their values will be 0010 1001
and 0000 1011, respectively. The following table lists the bitwise operators
supported by С, Java, Python, or JavaScript language with an example of each of
those.

|Name       |Description                                    | Expression      | Value of the Expression|
|---------- |-----------------------------------------------|-----------------|------------------------|
|NOT        |Inverts all the bits; in other words, it has   |                 |                        |
|           |the effect of 'flipping' bits.                 |        (~a)     |1101 0110 which is -42  |
|AND        |The result consists of the bits that exist in  |                 |                        |
|           |both operands.                                 |       (a & b)   |0000 1001 which is 9    |
|OR         |If one of the bits is 1 and it exists in       |                 |                        |
|           |either operand, OR operator will copy the bit  |                 |                        |
|           |to the result.                                 |       (a | b)   |0010 1011 which is 43   |
|XOR        |If one of the bits is 1 and it exists in only  |                 |                        |
|           |one of two operands, XOR operator will copy    |                 |                        |
|           |the bit to the result.                         |       (a ^ b)   |0010 0010 which is 34   |
|Left Shift |Shifts the left operand to the left by pushing |                 |                        |
|Operator   |zeros from the right as many times as          |                 |                        |
|           |indicated by the right operand, and lets the   |                 |                        |
|           |leftmost zero bits fall off.                   |        a << 3   |1 0100 1000 which is 328|
|Right Shift|Shifts the left operand to the right by copying|                 |                        |
|Operator   |the leftmost bit from the left as many times as|                 |                        |
|           |indicated by the right operand, and lets the   |                 |                        |
|           |rightmost bits fall off.                       |       a >> 3    |0000 0101 which is 5    |

C

```C
#include <stdio.h>

int main()
{
    int a = 41; // or int a = 0b101001;
    int b = 11; // or int b = 0b001011;

    printf("%d\n",~a);
    printf("%d\n",a&b);
    printf("%d\n",a|b);
    printf("%d\n",a^b);
    printf("%d\n",a<<3);
    printf("%d\n",a>>3);
    return 0;
}
```

The result:

-42
9
43
34
328
5

Python

```Python
a=41
b=11
result = ~a
print("~a =", result)
result = a&b
print("a&b =", result)
result = a|b
print("a|b =", result)
result = a^b
print("a^b =", result)
result = a<<3
print("a<<3 =", result)
result = a>>3
print("a>>3 =", result)
```

The result:

~a = -42
a&b = 9
a|b = 43
a^b = 34
a<<3 = 328
a>>3 = 5

###### Misc Operators

Ternary (conditional) operator (?:), which is an alternative for an if-else condition,
is written as follows:

`Expression ? ResultExpression1 : ResultExpression2`

The value of Expression is evaluated first. If it is true, then the value of
ResultExpression1 is executed, which becomes the result. If Expression is false,
then ResultExpression2 is executed and it becomes the result.

An analogue of the ternary conditional operation in mathematical logic and Boolean
algebra is a conditional disjunction, which is written in the form [p, q, r] and
implements the algorithm: "If p, then q, otherwise r", which can be rewritten
as "q or r, depending on whether p or not p ".

Misc Operators in C

There are some operators which fall under this category. They include:

- **sizeof**, which returns the size of the memory occupied by the particular data
  type of the operand.
- **comma (,)**, which is used to separate different expressions in situations where
  only one compound expression is used. These expressions are evaluated from left
  to right, and the type and value of the rightmost expression is the type and value
  of the compound expression.
- **pointer (*)**, this operation of addressing (dereferencing) allows you to access
  the value of the operand whose address is stored in the pointer.
- **pointer (&)**, which allows you to obtain the address (memory location) in which
  the operand is stored.

C

```C
#include <stdio.h>

int main()
{
    int age = 15, *pointer;
    pointer=&age; //Here the pointer stores the memory address of variable age
    printf("The value of variable age is: %d\n",*pointer);
    int expression1 = 10, expression2 = 30, expression3;
    expression3 = ( expression1 > expression2 ) ? expression1 : expression2;//
    Use of ?: operator
    printf("The Output of the ternary statement is: %d\n", expression3);
    int a , b , c, sum;
    sum = (a=1,b=2,c=3,a+b+c);
    printf("a + b + c = %d\n",sum);
    return 0;
}
```

The result:

The value of variable age is: 15
The Output of the ternary statement is: 30
a + b + c = 6

###### Operators Precedence

- Operator Precedence
  A property of an operator that affects the order in which its result is evaluated
  in relation to other operators. An operation is evaluated only after all operations
  with higher priority have been evaluated over its operands. We can use a bracket
  () operator to explicitly specify the order in which operators are applied as
  they have the highest precedence.

- Associativity
  A property of an operation which means the order of evaluation in a series of
  operations with the same priority. Thus, if it is necessary to perform multiplication
  and division, the C compiler will perform first the operation that follows first
  when reading the expression from left to right.



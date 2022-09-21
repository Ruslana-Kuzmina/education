# Basic Statements in Programming

## Selection Statements

But sometimes the program needs to make a choice whether to execute this or that
part of the code.

To solve this problem in programming, there are selection statements or as they
are also called, **conditional** or branching statements. Each path in the example
is a new branch. A branch condition has its value either **true** or **false**.

The simplest of these, i.e. the conditional statement, has a short **if** and a
full **if…else** form.

- short
  if (condition_expression) statement;

- full
  if (condition_expression)
  statement_1;
  else
  statement_2;

A **statement** is a simple or a compound (block) operator of a programming language.
A logical expression calculated before checking or attitude can be used as an
element of a condition_expression. In C, Java, and JavaScript the enclosure of a
condition_expression
in brackets is required. It is recommended to enclose a C, Java, and JavaScript
if block in curly braces when the body of an if statement comprises a single statement.
However, curly braces are mandatory when the body of an if statement comprises
multiple statements.

An if statement allows programs to take into account the conditions and execute
specific program instructions based on the taken decision. In a programming language,
an if statement works exactly in the same way as in colloquial speech. If the
requirements of a condition are met, then you need to perform one action (or a
set of actions); otherwise, perform a different action (or a different set of actions).

C and Java support almost the same set of data types, though Java supports additional
data types as well.

C

```C
#include <stdio.h>

int main()
{
    int a = 3;
    int b = 5;
    if (a == b)
    {
        printf("a and b are equal\n");
    }
    else
    {
        printf("a and b are not equal\n");
    }
    return 0;
}
```

The result:

a and b are not equal

Let us write the same example for comparison using a ternary operator:

```C
#include <stdio.h>

int main()
{
    int a = 3;
    int b = 5;
    printf((a == b) ? "equal" : "not equal");
    return 0;
}
```

The result:

not equal

Python

```Python
a = 3
b = 5
if a == b:
  print("a and b are equal")
else:
  print("a and b are not equal")
```

The result:

a and b are not equal

**Attention**: we need to make a space when we text print!!!!

Python does not make use of curly braces for a conditional body; instead, it simply
identifies the body of the block using indentation of the statements.
In Python, you can pass any variable or the result of any expression as a condition,
and it will be interpreted as True or False. False is represented by zero numbers,
empty strings, and collections (lists, dictionaries, tuples, sets). Therefore,
for example, in Python, a code comparison to 0 is always written as if a:, not
if a! = 0:.

In the example above, first, the condition in if will be checked and since it is
false (3 and 5 are not equal), the statement in else will be executed. It may
happen that the if and else statements are not enough. For example, if you have
5 dollars, you can buy a candy; if you have 10 dollars, you can buy a bar of
chocolate; and if you have more than 15 dollars, you can buy a cake. A different
else if statement in C, Java, and JavaScript and elif statement in Python can
be used to accomplish this task.

C

For example, if you have 5 dollars, you can buy a candy, if you have 10 dollars,
you can buy chocolate, and if you have more than 15 dollars, then a cake. Another
else if statement can be used to accomplish this task.

```C
#include <stdio.h>

int main() {
    int money;
    printf("How much money do you have?");
    scanf("%d", &money);
    if(money<5){
        printf("You cannot buy any sweets.\n");
    }
    else if((money>=5) && (money<10)){
        printf("You can buy a candy.\n");
    }
    else if((money>=10) && (money<15)){
        printf("You can buy 2 candies or one bar of chocolate.\n");
    }
    else if((money>=15) && (money<20)){
        printf("You can buy a cake, or one candy and one bar of chocolate, or
        three candies.\n");
    }
    else
        printf("You can buy any sweets you want.\n");
    return 0;
}
```

The result:

How much money do you have? 10
You can buy 2 candies or one bar of chocolate.

Let us formulate the previous example differently: Mary wants to buy a candy, or
a bar of chocolate, or a cake, and we need to find out how much money is needed.

To do this, a programming language has a different way of controlling and deciding
on the execution of statements, i.e. **switch ... case**. It differs from **if…else**
in that it is used when we are given multiple options (cases) and we want to perform
a separate task for each option. The syntax of the statement in C, Java, and JavaScript
is as follows:

```C
switch (Expression) {
    case Constant1: Statement list 1;
    case Constant2: Statement List 2;
    ...
    case ConstantN: List of N statements;
    default: List of operators N + 1 - optional branch;
}
```

The execution of an operator begins with evaluating an **expression**, the value
of which must be of an integer or a character type. This value is compared to the
values of the **constants** and is used to select the branch to execute. That is,
constants actually act as labels. If the expression value matches one of the listed
constants, then control is transferred to the corresponding branch. After that, if
the exit from the **switch** in this branch is not explicitly specified, all other
branches are executed sequentially. The **break** control statement exits the switch
statement if one and only one branch is to be executed. If the value of the expression
does not match any of the selection constants, the transition to the **default**
label or, in its absence, to the operator following the **switch** statement, occurs.

It is important to remember that:

- All constants must have different values; however, they must also be of the same
  type.
- Several labels can follow in a row, and then the transition to the specified
  branch will occur when at least one of them matches.
- The order of the branches is not regulated.

C with *break*

```C
#include <stdio.h>

int main()
{
    char choice;
    printf("What do you prefer?\n");
    printf("1 a candy\n");
    printf("2 chocolate\n");
    printf("3 a cake \n");
    printf("Enter your choice:\n");
    scanf(" %c", &choice);
    switch(choice)
   {
        case '1':
            printf("You need 5 dollars.\n");
            break;
        case '2':
            printf("You need 10 dollars.\n");
            break;
        case '3':
            printf("You need 15 dollars.\n");
            break;
        default:
            printf("Invalid choice\n");
            break;
    }
    return 0;
}
```

The result (we choose 1):

What do you prefer?
1 a candy
2 chocolate
3 a cake
Enter your choice:
1
You need 5 dollars.

## Iteration Statements

A **loop** is one of the fundamental concepts in programming. A loop repeats a code
block over and over again until it meets the requirement to stop the cycle. Any
loop consists of loop code, i.e. those statements that are executed several times,
initial settings, the modification of the loop parameter and checking the condition
for continuing loop execution.

One pass through a loop is called a **step** or an **iteration**. The condition
for continuing the loop is checked at each iteration, either before the execution
of loop code (with a precondition), or after the execution (with a postcondition).

C, Java and JavaScript (iteration statement or loop):

- while
- do-while
- for

Python (loops):

- for in
- while

While loop

A **while loop** is used to repeat some lines of code for an **unknown** number
of times until a condition is met. For example, we have chosen the number 21 and
want to ask a user to guess it. We don't know how many times the user can enter
the wrong number, so we keep asking until the number is guessed, that is, "until
the number is 21". The syntax of a while loop is as follows:

```C
while(condition) {
 statement(s) // body of the loop
 }
 ```

 The execution of the body of a while loop continues for as long as the condition
 is true. This is the main difference between while and if constructs. The body
 of an if branching statement is executed only if the condition is true and only
 once, whereas the body of a while loop can be executed many times.

 A Do ... While loop

 The second loop is called a **do… while loop**. But this is not used in Python.
 The syntax of any do… while loop is as follows:

```C
do{
    statement(s)// body of the loop
} while(condition);
```

Use a **do… while** loop instead of a regular **while loop** only if the body of
a loop must be executed at least once. Since the condition is located only at the
end of a do… while loop, a computer has no way to check if this condition is true
until the body of the loop is executed for the first time.
Because do … while loops check the condition after the block is executed, the control
structure is also often known as a **post-test loop**.

Make sure that when you execute expressions from the body of while and do ... while
loops, certain changes take place in the loop condition. Otherwise, the created
loop will repeat for an infinite number of times, since a computer will check the
truth of the same condition every time the loop is passed. This will lead to the
creation of an **infinite loop**, which may be one of the possible reasons for
a computer "freezing", including thrashing, deadlock, and access violations.
You can avoid infinite loops by making sure that while executing a while or a
do…while loop, something changes in its condition in such a way that over time the
condition becomes false - and the program execution continues by executing the
program instructions following the loop.

### A For Loop

If we (or a computer) know exactly how many times to execute a piece of code (like
shuffling a deck of cards), we use a for loop. Some examples:

- Calculate an average salary for 3 months.
- Print even numbers from 1 to 101.
- Count the number of vowels and consonants in a sentence (we pre-enter a sentence
  and we can know its length using the length function).

The syntax of a for loop is as follows :

```C
for (initialization; condition test; counter update or step)
{
  statement(s)// code block to be executed
}
```

The for-statement has the following capabilities:

- it can create an infinite loop: *for ( ; ; )* ... (in C and Java programming
  languages)
- you can count using symbols, not just numbers: *for (ch = 'a'; ch <= 'z'; ch ++)*
- you can check the fulfillment of some arbitrary condition: *for (i = 1; i * i*
  *1 * i <= 216; i ++)*

The most common mistakes when creating loops are the use of uninitialized variables
in the loop code and an incorrect record of the loop exit condition. To avoid mistakes,
you need:

- to check whether all the variables on the right side of the assignment operators
  in the loop code have been assigned initial values before (and also, whether other
  operators can be executed)
- to check if at least one variable included in the loop exit condition changes
  in a loop
- to provide an emergency exit from a loop upon reaching a certain number of iterations
- to check if a loop includes more than one operator, and if it does, enclose them
  in curly braces

Examples
Let's help Mary find out how many candies she can buy if 1 candy costs $2 and she
has some amount of money. We can solve the problem in 2 ways: by gradually decreasing
the available amount, but in this case, we can get a negative amount at the last
iteration. The second way presupposes that we add up a total cost when adding each
new candy and compare it with the available amount. Which of the loops to use? In
this case, both would work. The main thing is to correctly set the condition for
a loop.

C

```C
#include<stdio.h>

int main() {
    int money;
    int cost = 2;
    int count = 0;
    printf("How much money does Mary have: ");
    scanf("%d", &money);
    while(money >= cost)
    {
        money = money - cost;
        count = count + 1;
    };
    printf("mary can buy %d candies\n", count);
    return 0;
}
```

The result:

How much money does Mary have?
9
Mary can buy 4 candy(es).

Python

```Python
money = 15
cost = 2
count = 0
while money >= cost:
   count = count + 1
   money = money - cost
print(count, "candies")
```

In programming, **nested loops** are often used when a loop is placed inside another
loop. Each time an outer loop repeats, an inner loop repeats too. Nested while and
do…while loops exist but are not widely used.

Let us write a simple example of a multiplication table for 2 and 3.

C

```C
#include <stdio.h>
int main()
{
    int i;
    int j;

    for(i = 2;i<=3;i++)
    {/*outer loop*/
        printf("Table of %d\n",i);
        for(j = 1;j<=10;j++)
        {/*inner loop*/
            printf("%d*%d = %d\n",i,j,i*j);
        }
    }
    return 0;
}
```

The result:

Table of 2
2*1 = 2
2*2 = 4
2*3 = 6
2*4 = 8
2*5 = 10
2*6 = 12
2*7 = 14
2*8 = 16
2*9 = 18
2*10 = 20
Table of 3
3*1 = 3
3*2 = 6
3*3 = 9
3*4 = 12
3*5 = 15
3*6 = 18
3*7 = 21
3*8 = 24
3*9 = 27
3*10 = 30

Python

```Python
for i in range(2, 4):
  for j in range(1,11):
    print(i,"*", j,"=", i * j)
  else:
    print("The end of the multiplication by", i)
  print()
```

The result:

2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
2 * 10 = 20
The end of the multiplication by 2

3 * 1 = 3
3 * 2 = 6
3 * 3 = 9
3 * 4 = 12
3 * 5 = 15
3 * 6 = 18
3 * 7 = 21
3 * 8 = 24
3 * 9 = 27
3 * 10 = 30
The end of the multiplication by 3

In Python, you can use the **else** keyword in a **for** loop, which specifies a
block of code to be executed when the loop succeeds.

## Loop Control Statements

### Break Control

In some cases, the condition in a loop is always evaluated as a true one and creates
an infinite loop. When such a loop is created intentionally, there is usually
another control structure (such as a break statement) that allows termination of
the loop. A **break statement** is also used when, while executing a loop, it becomes
necessary to skip a part of the loop or to leave the loop as soon as a certain
condition becomes true. This is known as **jumping out of the loop**.

#### Continue Statements

A continue statement can be used in all types of loops (but not in a switch statement).
The presence of a continue operator causes a skip of the "remaining" part of the
iteration and the transition to the beginning of the next one, i.e. early completion
of the current step and transition to the next step.

In **while** and **do... while** loops, this means going directly to the test part.
In a for loop, control is passed to the correction step, i.e. the third modification
of statements (Statement 3). A continue statement is often used to exclude some loop
iterations without significantly increasing the nesting level of the program. Otherwise,
we would have to write a few additional conditions for the loop, or even split it
into several loops.

##### Goto Unconditional Jump Statements

Some programming languages provide a **goto** operator, the general view of which
is:

`goto Label;`

It is intended to transfer control to the operator marked with a specific label.
A label is an identifier, formatted according to all the rules for identifying
variables with a colon after it; for example, an empty operator marked with the
m1 label:

`m1: ;`

The scope of a label is the function where it is defined. If necessary, you can use
the block.

Loops and switches can be nested within each other, and the most typical justified
case of using a goto statement is executing an interrupt (organizing an exit) in
a nested structure. For example, in case of gross uncorrectable errors, it is
necessary to exit two (or more) nested structures (where you cannot use a break
statement directly – since it breaks only the innermost loop):

```C
for (...)
    for (...) {
       ...
       if (Error) goto label;
    }
...
label: operators to eliminate the error;
```

One more justified case presupposes organizing transitions from several places
in a function to one place; for example, when before function termination, it is
necessary to do the same operation.

There are some disadvantages of using goto related to the fact that they are weak
in tracing the program flow. It's difficult for the programmers to alter any program
content; moreover, locating the precise destination of a goto statement is tedious.

Task

Based on the year of birth that you have entered, display the name of the corresponding
animal according to the Chinese horoscope. The name of the animal is chosen depending
on the remainder of dividing the year by 12 according to the following scheme:

0 - Monkey
1 - Rooster
2 - Dog
3 - Pig
4 - Rat
5 - Ox
6 - Tiger
7 - Rabbit
8 - Dragon
9 - Snake
10 - Horse
11 - Goat

C

```C
#include <stdio.h>

int main()
{
    int year, k, n = 1;

    printf("Enter the year (positive value and less than 10000)\n");
    scanf("%d",&year);
    while(n)
    {
        if (year<= 0||year>10000)
        {
            printf("Enter the correct value\n");
            scanf("%d",&year);
        }
        else n=0;
    }

    k = year%12;
    switch (k) {
        case 11:
            printf("%d - The year of the Goat\n",year); break;
        case 10:
            printf("%d - The year of the Horse\n",year); break;
        case 9:
            printf("%d - The year of the Snake\n",year); break;
        case 8:
            printf("%d - The year of the Dragon\n",year); break;
        case 7:
            printf("%d - The year of the Rabbit\n",year); break;
        case 6:
            printf("%d - The year of the Tiger\n",year); break;
        case 5:
            printf("%d - The year of the Ox\n",year); break;
        case 4:
            printf("%d - The year of the Rat\n",year); break;
        case 3:
            printf("%d - The year of the Pig\n",year); break;
        case 2:
            printf("%d - The year of the Dog\n",year); break;
        case 1:
            printf("%d - The year of the Rooster\n",year); break;
        case 0:
            printf("%d - The year of the Monkey\n",year); break;
    }
  return 0;
}
```

Python

```Python
year = int(input("Enter the year (positive value and less than 10000): "))
while not 0 <= year < 10000:
    print("Enter the correct value")
    year = int(input("Enter the year (positive value and less than 10000): "))

k = year % 12
if k == 0:
    year_animal = "Monkey"
elif k == 1:
    year_animal = "Rooster"
elif k == 2:
    year_animal = "Dog"
elif k == 3:
    year_animal = "Pig"
elif k == 4:
    year_animal = "Rat"
elif k == 5:
    year_animal = "Ox"
elif k == 6:
    year_animal = "Tiger"
elif k == 7:
    year_animal = "Rabbit"
elif k == 8:
    year_animal = "Dragon"
elif k == 9:
    year_animal = "Snake"
elif k == 10:
    year_animal = "Horse"
elif k == 11:
    year_animal = "Goat"

print("{} - The year of the {}.".format(year, year_animal))
```

```Python
chinese_years = {
    0: "Monkey",
    1: "Rooster",
    2: "Dog",
    3: "Pig",
    4: "Rat",
    5: "Ox",
    6: "Tiger",
    7: "Rabbit",
    8: "Dragon",
    9: "Snake",
    10: "Horse",
    11: "Goat",
}

year = int(input("Enter the year (positive value and less than 10000): "))
while not 0 <= year < 10000:
    print("Enter the correct value")
    year = int(input("Enter the year (positive value and less than 10000): "))

k = year % 12
print("{} - The year of the {}.".format(year, chinese_years[k]))
```

Task 2

A car drove N miles in 0.5 hours. Did the driver violate the traffic rules if the
speed limit was 45 mph?

C

```C
#include <stdio.h>

int main()
{
    float miles, v, hours = 0.5;

    printf("Enter the number of miles\n");
    scanf("%f", &miles);
    int n=1;
    while(n) //checking for correct numeric input
    {
        if (miles<= 0)
        {
            printf("Enter the correct value\n");
            printf("Enter the number of miles\n");
            scanf("%f",&miles);
        }
        else n=0;
    }

    v = miles/hours;
    if (v > 45)
        printf("The driver violated the traffic rules.\n");
    else
        printf("The driver didn't violate the traffic rules.\n");
  return 0;
}
```

Python

```Python
hours = 0.5
distance = int(input("Enter the number of miles: "))
while not 0 <= distance:    #checking for correct numeric input
    print("Enter the correct value")
    distance = int(input("Enter the number of miles: "))

if distance/hours > 45:
    print("The driver violated the traffic rules")
else:
    print("The driver didn't violate the traffic rules")
```

Task 3

Calculate the total amount you will pay if the purchase costs $N and the following
discounts are provided: if the purchase costs less than $100 – a 5% discount, if
the purchase costs from $100 to $200 – a 10% discount, and, finally, if the purchase
costs $200 and more – a 15% discount.

C

```C
#include <stdio.h>

int main()
{
    float pr,result = 0;

    printf("Enter the cost of the purchase \n");
    scanf("%f", &pr);
    if (pr > 0 && pr < 100)
    {
        result = pr-0.05*pr;
        printf("Your discount is 5 percent, the amount to be paid is $%.2f.\n",result);
    }
    else if (pr >= 100 && pr < 200)
    {
        result = pr-0.1*pr;
        printf("Your discount is 10 percent, the amount to be paid is $%.2f.\n",result);
    }
    else if(pr >= 200)
    {
        result = pr-0.15*pr;
        printf("Your discount is 15 percent, the amount to be paid is $%.2f.\n",result);
    }
    else printf("The cost of the purchase should be a positive number.\n");
  return 0;
}
```

Python

```Python
purchase_price = int(input("Enter the purchase price: "))
discount = 0
if purchase_price < 100:
    discount = 5
    purchase_price *= 0.95
elif purchase_price > 200:
    discount = 15
    purchase_price *= 0.85
else:
    discount = 10
    purchase_price *= 0.9
print("Your discount is {}%, the amount to be paid is ${:.2f}.".format(
    discount,
    purchase_price,
))
```